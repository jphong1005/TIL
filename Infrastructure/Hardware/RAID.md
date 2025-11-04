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
  
  - 동작 방식: Striping
  - 최소 필요 드라이브 갯수: 2개
  - 최대 용량: 드라이브 용량 (GB/TB) * 총 드라이브 갯수
  - 장점
    - 가장 우수한 Read / Write 성능 제공 (Read / Write 트랜잭션 속도가 빠름)
    - 전체 용량 사용 가능
    - 간단한 구성과 저렴한 초기비용
  - 단점
    - 이중화나 내결함성 기능 없음
    - 디스크 하나라도 깨지면 (Fault), 모든 데이터 손실 위험
</details>
