# [TIL] RAID
> 여러 개의 하드디스크 관리 방법
<br>

## 💿 RAID
### 1️⃣ RAID(Redundant Array of Independent Disks)란 무엇인가?
- '복수 배열 독립 디스크'라고 하며, **여러 개의 HDD나 SSD를 하나의 논리적인 단위로 결합**해 **데이터 저장의 신뢰성을 높이고 성능을 향상**시키는 기술
- 여러 물리 드라이브 (디스크)에 데이터를 분산 또는 복제하여, 빠르고 안정적인 하나의 물리 드라이브처럼 작동하도록 만드는 기술

<br>

### 2️⃣ RAID의 목적
- 데이터 보호 및 이중화 (Data Protection and Redundancy)
  - 드라이브 (디스크) 장애 발생 시, 데이터 손실을 방지 및 최소화
  - Mirroring / Parity라는 중복 정보를 생성하여, 이를 통해 데이터를 복구
    
- 성능 향상 (Performance Improvement)
  - 여러 드라이브에 데이터를 분산 저장하거나 동시에 Read / Write 함으로써, 입출력 속도 향상
    
- 용량 확장 (Increased Capacity)
  - 여러 드라이브의 저장 공간을 합쳐, 더 큰 하나의 논리적 Volume 생성 가능
    
- 고가용성 및 안정성 (High availability & Reliability)
  - 시스템 다운타임을 최소화하고 중요 서비스를 지속할 수 있도록 함
  
<br>

### 3️⃣ RAID의 종류
<details>
  <summary>
    <h4>1. RAID 0 (Striping)</h4>
  </summary>

  <img width="50%" height="50%" src="https://github.com/user-attachments/assets/e6cf2024-4ec3-4787-99cd-ced74801c58d" />
  
  - 동작 방식: 데이터를 여러 드라이브에 분산하여 저장
    
  - 최소 필요 드라이브 갯수: 2개
    
  - 최대 용량: 드라이브 용량 (GB / TB) * 총 드라이브 갯수 (n)
    
  - 장점
    - 가장 우수한 Read / Write 성능 제공 (-> Read / Write 트랜잭션 속도가 빠름)
    - 전체 용량 사용 가능
    - 간단한 구성과 저렴한 초기비용
    
  - 단점
    - 이중화나 내결함성 기능 없음
    - 디스크 하나라도 깨지면 (Fault), 모든 데이터 손실 위험
</details>

<details>
  <summary>
    <h4>2. RAID 1 (Mirroring)</h4>
  </summary>

  <img width="50%" height="50%" src="https://github.com/user-attachments/assets/ccf62745-2d26-485d-9148-3d981e557af1" />

  - 동작 방식: 동일한 데이터를 복제하여 양쪽에 저장
    
  - 최소 필요 드라이브 갯수: 2개
    
  - 최대 용량: 드라이브 용량 * (총 드라이브 갯수 / 2)
    
  - 장점
    - 높은 수준의 데이터 안정성과 이중화 제공
    - 미러링을 통해 데이터 손실 방지
    
  - 단점
    - 전체 물리적 용량의 절반만 사용 가능
    - Write (쓰기) 성능은 단일 드라이브와 동일하거나 느림
    - 상대적으로 높은 비용
</details>

<details>
  <summary>
    <h4>3. RAID 5 (Striping with parity across drives)</h4>
  </summary>

  <img width="50%" height="50%" src="https://github.com/user-attachments/assets/34249bd7-17ba-490f-8b0e-976ebad08f34" />

  - 동작 방식: 데이터 블록과 해당 블록에 대한 패리티를 계산하여 배열 내의 드라이브에 분산 저장 (분산 패리티)
    
  - 최소 필요 드라이브 갯수: 3개
    
  - 최대 용량: 드라이브 용량 * (총 드라이브 갯수 - 1)
    
  - 장점
    - 성능, 용량 효율성, 데이터 이중화 간에 좋은 균형 제공
    - 패리티 정보를 저장하는 데, 약 1개의 드라이브 공간 사용
    - 데이터가 분산 저장되어 병렬 읽기가 가능해 읽기 성능이 우수 (-> RAID 0-based)
    
  - 단점
    - Write 작업 시, 패리티 계산이 들어가 쓰기 성능이 다소 저하
    - 데이터 재구축 (Rebuild) 시간이 오래 걸릴 수도 있음
    - 리빌딩 과정 동안 성능이 저하되고, 추가적인 장애에 취약
    - 동시에 2개의 디스크 장애 시, 데이터 손실
</details>

<details>
  <summary>
    <h4>4. RAID 6 (Striping with dual parity across drives)</h4>
  </summary>

  <img width="50%" height="50%" src="https://github.com/user-attachments/assets/219be4f0-f028-4f45-916f-9e1aad8062a8" />

  - 동작 방식: RAID 5와 유사한 방식으로 동작하나, 2개의 독립적인 패리티 블록을 생성하여 분산 저장
    
  - 최소 필요 드라이브 갯수: 4개
    
  - 최대 용량: 드라이브 용량 * (총 드라이브 갯수 - 2)
    
  - 장점
    - RAID 5보다 향상된 내결함성 제공
    - 2개의 디스크가 Fault 되어도 데이터를 보호
    - 대용량 스토리지 및 고가용성 요구 시스템에 적합
    
  - 단점
    - 2개의 패리티 계산으로 인해 RAID 5보다 쓰기 성능 저하
    - 리빌딩 시간이 RAID 5보다 더 길다
    - 2개의 드라이브가 패리티를 차지하기 때문에 용량 효율성이 낮음
    - RAID 5보다 초기 비용이 높음
</details>

<details>
  <summary>
    <h4>5. RAID 1+0 (RAID 10, Mirroring + Striping)</h4>
  </summary>

  <img width="50%" height="50%" src="https://github.com/user-attachments/assets/c0ad8644-c83b-45d6-9f7c-232fe7caa3ea" />
  
  - 동작 방식: RAID 1 (Mirroring)을 먼저 구성한 후, RAID 0 (Striping)을 적용
    
  - 최소 필요 드라이브 갯수: 4개 (-> 2*n개 즉, 짝수개만 가능)
    
  - 최대 용량: RAID 1의 용량 * (RAID 1의 갯수)
    
  - 장점
    - Striping을 통해 높은 Read / Write 트랜잭션 성능 제공
    - Mirroring을 통해 높은 수준의 이중화 및 내결함성 제공
    - 리빌딩 시간이 비교적 빠름
    - 리빌딩 중 시스템에 가해지는 부하가 적고 추가 장애 낮음
    
  - 단점
    - 전체 용량의 절반만 사용 가능해 효율성이 낮음
    - 드라이브 갯수가 많아 구축 비용이 높음
    - RAID 5 / RAID 6보다 확장성이 제한적
</details>

<div class="RAID TableView">
  <h4>RAID 정리</h4>
  <table>
    <thead>
      <tr>
        <td></td>
        <td>RAID 0</td>
        <td>RAID 1</td>
        <td>RAID 5</td>
        <td>RAID 6</td>
        <td>RAID 1+0</td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>최소 드라이브 갯수</td>
        <td>2개</td>
        <td>2개</td>
        <td>3개</td>
        <td>4개</td>
        <td>4개</td>
      </tr>
      <tr>
        <td>내결함성</td>
        <td>없음</td>
        <td>1개</td>
        <td>1개</td>
        <td>2개</td>
        <td>Mirror 세트 당 1개</td>
      </tr>
      <tr>
        <td>용량 효율성</td>
        <td>100%</td>
        <td>50%</td>
        <td>(N-1)/N%</td>
        <td>(N-2)/N%</td>
        <td>50%</td>
      </tr>
      <tr>
        <td>읽기 성능</td>
        <td>매우 우수</td>
        <td>양호~우수</td>
        <td>매우 우수</td>
        <td>매우 우수</td>
        <td>우수</td>
      </tr>
      <tr>
        <td>쓰기 성능</td>
        <td>매우 우수</td>
        <td>보통</td>
        <td>보통 (패널티)</td>
        <td>낮음 (패널티)</td>
        <td>우수</td>
      </tr>
      <tr>
        <td>리빌딩 속도</td>
        <td>없음</td>
        <td>빠름</td>
        <td>보통~느림</td>
        <td>느림</td>
        <td>빠름</td>
      </tr>
      <tr>
        <td>비용</td>
        <td>낮음</td>
        <td>높음</td>
        <td>중간</td>
        <td>중간~높음</td>
        <td>매우 높음</td>
      </tr>
      <tr>
        <td>사용 사례</td>
        <td>임시 데이터 처리, 고속 작업용 등</td>
        <td>OS 드라이브, 중요한 DB 등</td>
        <td>파일 서버, NAS 등</td>
        <td>아카이브 등</td>
        <td>고성능 DB 서버, 고성능 가상화 서버 (VM) 등</td>
      </tr>
    </tbody>
  </table>
</div>

<details>
  <summary>
    <h4>기타 RAID</h4>
  </summary>

  - <h4>RAID 2</h4>
    - 오류 수정을 위한 해밍 코드 Bit 레벨 Striping
    - 데이터를 Bit 단위로 Striping하고 별도의 드라이브에 해밍 코드라는 오류 수정 코드 (ECC, Error-Correcting Code) 저장
    - 현대의 드라이브는 자체적으로 정교한 ECC 기능이 내장되어 있어 RAID 2의 ECC 기능은 더 이상 불필요
    
  - <h4>RAID 3</h4>
    - 전용 Parity 드라이브를 활용한 Byte 레벨 Striping
    - 데이터는 Byte 단위로 Striping 되며, 단일 전용 드라이브에 Parity 정보가 저장됨
    - 이 방식은 드라이브의 스핀들을 동기화해야 하며, 대규모 순차적인 데이터 전송 (e.g. 초기 비디오 편집)에는 효율적
    - 작은 크기의 임의 I/O 작업에서는 전용 Parity 드라이브가 병목 지점이 되어 성능이 크게 저하
    
  - <h4>RAID 4</h4>
    - 전용 Parity 디스크를 활용한 Block 레벨 Striping
    - RAID 3와 유사하지만, 데이터 Striping을 Block Level로 변경하여 임의 Read 성능 개선
    - Write 작업 시에는 여전히 Parity 드라이브에 Parity 업데이트가 집중되어 병목 현상 발생
</details>

<br>

### 4️⃣ H/W RAID vs S/W RAID
<div class="H/W RAID v S/W RAID">
  <table>
    <thead>
      <tr>
        <td></td>
        <td>H/W RAID </td>
        <td>S/W RAID </td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>정의</td>
        <td>전용 컨트롤러 카드/칩 사용</td>
        <td>OS 기능 사용 (= OS-based)</td>
      </tr>
      <tr>
        <td>성능</td>
        <td>우수 (CPU 부하 적음, 전용 프로세서)</td>
        <td>CPU 성능에 따라 다름</td>
      </tr>
      <tr>
        <td>비용</td>
        <td>높음 (RAID Controller 구매)</td>
        <td>낮음</td>
      </tr>
      <tr>
        <td>안정성</td>
        <td>높음 (OS와는 독립적, BBU 등)</td>
        <td>OS에 의존적, 고급 기능 부족</td>
      </tr>
      <tr>
        <td>주요 장점</td>
        <td>성능, 안정성, 고급 기능 (BBU, 캐시)<br><br> BBU: Cache를 안전하게 보호하기 위한 배터리<br>RAID Controller에는 Cache Battery가 연결되어 있음</td>
        <td>비용 효율, 설정 용이, 유연성</td>
      </tr>
      <tr>
        <td>주요 단점</td>
        <td>비용, Vendor 종속 가능성</td>
        <td>CPU 자원 사용, 성능 저하 가능성, 고급 기능 부족</td>
      </tr>
      <tr>
        <td>관리</td>
        <td>컨트롤러 유틸리티, 펌웨어 관리</td>
        <td>OS 내 도구 사용</td>
      </tr>
      <tr>
        <td>확장성</td>
        <td>컨트롤러 지원 범위 내</td>
        <td>OS 및 드라이버 지원 범위 내</td>
      </tr>
      <tr>
        <td>RAID 5, RAID 6 적합성</td>
        <td>Parity 계산 효율적</td>
        <td>Write 부하 시, 성능 저하 가능</td>
      </tr>
    </tbody>
  </table>
</div>

<br>

### 5️⃣ RAID 구성 주의사항
#### Drive 선택
- 안정성과 최적의 성능을 위해서는 RAID에 포함되는 모든 드라이브의 사양을 맞추는 것이 중요
  
- 동일한 용량, 동일한 속도 (HDD의 RPM 또는 SSD의 IOPS) + 가급적 동일 제조사의 동일한 모델로 맞추는것 권장
  
- 드라이브의 용량이 서로 다르면 이론상으로는 RAID를 구성할 수는 있지만, 가장 작은 용량의 드라이브가 기준이 됨
  - HDD의 RPM, 전송 속도 (e.g. Gbps) 등
  
- 속도나 응답 시간 또한 성능이 가장 느린 드라이브에 맞춰지거나 특정 드라이브에 과부하가 걸려 수명 단축 위험
