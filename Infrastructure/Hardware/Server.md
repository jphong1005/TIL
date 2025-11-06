# [TIL] Server / Hardware Basic
> Server와 Hardware에 대한 기초 지식
<br>

## 🖥️ Server
### 1️⃣ 서버(Server)란 무엇인가?
네트워크 상에서 **데이터·자원·서비스를 제공하는 시스템**으로, 다른 컴퓨터(Client)의 요청에 따라 **정보를 응답하는 컴퓨터 또는 프로그램**

<br>

### 2️⃣ 서버의 타입
Server는 물리적 형태에 따라 크게 _Rack Server_, _Tower Server_, _Blade Server_, _Micro Server_ 등으로 나뉨
|<img width="100%" height="100%" src="https://www.fujitsu.com/global/imagesgig5/DK80089_tcm100-7104209_tcm100-5309118-32.png" />|<img width="100%" height="100%" src="https://www.fujitsu.com/global/imagesgig5/292031_tcm100-6611255_tcm100-5309118-32.png" />|<img width="100%" height="100%" src="https://www.fujitsu.com/kr/Images/107468_tcm119-40715.png" />|<img width="100%" height="100%" src="https://jp.fujitsu.com/platform/server/primergy/product-navi/image/mx130s2-201111.jpg" />|
|:---:|:---:|:---:|:---:|
|Rack Server|Tower Server|Blade Server|Micro Server|

<details>
  <summary>
    <h4>1. Rack Server란?</h4>
  </summary>

  <h5>[개요]</h5>
  
  - Rail Kit을 이용하여 서버 랙 (Server Rack)에 장착하는 서버
  - 데이터센터 또는 IDC (Internet Data Center)에서 가장 많이 사용하는 표준형 서버
    
  <h5>[특징]</h5>
  
  - 표준 단위 크기(U)를 사용
    - 표준 크기 단위: 1U (1.75"), 2U, 4U 등
  - 공간의 효율이 높고, 냉각 및 케이블 관리 용이
  - 유지보수가 쉬움
  - 소음이 크고, 전용 냉각 환경 필요

  <h5>[사용 예시]</h5>

  - 대기업, IDC, 클라우드 서비스 운영, 웹/DB 서버 등
</details>

<details>
  <summary>
    <h4>2. Tower Server란?</h4>
  </summary>

  <h5>[개요]</h5>
  
  - 일반 데스크탑 PC처럼 세워서 사용하는 형태의 서버
    
  <h5>[특징]</h5>
  
  - 구조가 단순하며, 소음이 적고 유지보수가 용이
  - 확장성이 좋아서 HDD나 메모리를 쉽게 추가 가능
  - 공간의 효율성이 낮아, 여러 대를 설치하면 자리 차지가 많음

  <h5>[사용 예시]</h5>

  - 중소기업 사무실의 파일 서버, 프린트 서버, 백업 서버 등
  - 개인용 홈 서버 구축에도 많이 사용
</details>

<details>
  <summary>
    <h4>3. Blade Server란?</h4>
  </summary>

  <h5>[개요]</h5>
  
  - 하나의 섀시 (Chassis)에 얇은 '블레이드 (Blade)' 모듈 형태의 서버를 여러개 꽂아서 사용하는 서버
  - 각 블레이드는 독립적인 서버지만, 전원·냉각·네트워크를 공유
    
  <h5>[특징]</h5>
  
  - 공간 절약을 극대화 (= 고밀도 집적 가능)
  - 전력 효율이 높음, 중앙 집중식 관리 용이
  - 비싼 초기비용과 발열량이 많아 냉각 시스템이 필수

  <h5>[사용 예시]</h5>

  - 대규모 데이터센터, 클라우드 인프라, 연구기관의 고성능 연산 서버 등
</details>

<details>
  <summary>
    <h4>4. Micro Server란?</h4>
  </summary>

  <h5>[개요]</h5>
  
  - 블레이드보다 더 소형화된 저전력, 다중 노드 서버
  - 하나의 섀시에 수십 개의 작은 서버인 노드가 들어가 있음
    
  <h5>[특징]</h5>
  
  - 에너지 효율 우수, 공간 효율 극대화
  - 가벼운 워크로드 (e.g. 웹 호스팅, 캐시서버 등)에 적합
  - 고성능 처리에는 부적합

  <h5>[사용 예시]</h5>

  - 클라우드 엣지 서버, 소규모 웹 서비스, IoT 게이트웨이 등
</details>

<br>

### 3️⃣ 서버 IPMI (Intelligent Platform Management Interface)
<div class="Server IPMI">
  <table>
    <thead>
      <tr>
        <td></td>
        <td>IBM (Lenovo)</td>
        <td>HP (Proliant)</td>
        <td>DELL</td>
        <td>Fujitsu</td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Port Name</td>
        <td>IMM</td>
        <td>ILO</td>
        <td>iDRAC</td>
        <td>iRMC</td>
      </tr>
      <tr>
        <td>Installation CD / DVD</td>
        <td>ServerGuide</td>
        <td>SmartStart</td>
        <td>LifeCycle</td>
        <td>ServerView</td>
      </tr>
      <tr>
        <td>Management Tool</td>
        <td>System Manager <br>(RAID는 MegaRAID)</td>
        <td>System Management</td>
        <td>OMSA <br>(Open Manage Server Administrator)</td>
        <td>ServerView Suit</td>
      </tr>
      <tr>
        <td>Default IP</td>
        <td>192.168.70.125</td>
        <td>DHCP</td>
        <td>192.168.0.120</td>
        <td>DHCP <br>(192.168.1.1)</td>
      </tr>
      <tr>
        <td>ID /PW</td>
        <td>USERID / PASSW0RD</td>
        <td>administrator / (check top cover)</td>
        <td>root / calvin <br>root / (check top cover)</td>
        <td>admin / admin <br>admin / (check top cover)</td>
      </tr>
      <tr>
        <td>Notes</td>
        <td>Windows는 169.254.95.118로도 access 가능</td>
        <td>Tftpd로 DHCP IP 할당</td>
        <td>최신 서버인 경우, top cover 확인</td>
        <td>DHCP가 default <br>(M7 이후부터 top cover 확인)</td>
      </tr>
    </tbody>
  </table>
</div>

<br>

## ⚙️ Hardware
### 1️⃣ Mainboard
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/b7fb752c-594e-489e-8b7d-9fba7262a39d" />

  - Mainboard는 'Motherboard'라고 하며, 전자적 장치에서 주회로가 내장된 보드
  - 각종 케이블이나 배선을 통합하여 연결하는 회로와 I/O 포트가 설치되어 있는 전자기판
  - CPU나 RAM과 같은 시스템이 작동하기 위한 주요 부품 장착과 주변 장치를 연결할 수 있는 인터페이스를 제공하는 인쇄회로기판

<br>

### 2️⃣ CPU (Central Processing Unit): 사람의 두뇌
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/9eea8549-3210-47f1-94e8-232040ce10ec" />

- 시스템 통제, 프로그램의 연산을 실행하고 처리하는 가장 핵심적인 제어장치
- Output으로부터 정보를 입력받아 기억하고 프로그램의 명령어를 해석하여 연산을 통해 외부로 출력하는 역할
- 다른 부품과 정보를 교환하면서 시스템 전체를 제어하는 장치
- 서버의 CPU는 일반 PC의 CPU보다 Core 수가 많아, Multi-threading 능력이 뛰어나고 장시간 가동에 최적화
  - Socket 갯수 = CPU 갯수
  - Core 수 = CPU의 주요 계산 부분
  - Thread 수 = 하나의 Core에서 처리할 수 있는 수

> [!NOTE]
> Core: CPU 안에서 실제로 연산과 명령 처리를 수행하는 독립적인 처리 장치 (즉, 작업을 실제로 하는 손)
> 
> Thread: Core가 실행할 수 있는 작업 단위 (즉, 작업을 수행하는 손가락)

<br>

### 3️⃣ RAM (Random Access Memory)
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/4c70bb65-9c54-4de4-af1f-7f4c7cd44161" />

- Power가 공급되지 않으면, 데이터가 지워지는 휘발성 기억장치
- CPU는 연산을 하고, 동작에 필요한 (임시)데이터가 RAM에 저장
- RAM이 많으면 한 번에 많은 작업 가능

#### RAM의 종류
|종류|설명|
|:---:|---|
|ECC 메모리<br>(Error-Correcting Code Memory)|· 데이터 오류를 자동으로 감지하고 수정하는 기능을 포함한 메모리|
|RDIMM & LRDIMM<br>(Registered DIMM & Load-Reduced DIMM)|· 대량의 메모리를 사용할 때, 신호 간섭을 줄여 안정성을 높임<br><br>* 안정성: 작은 변화나 교란이 있어도 정상적인 상태를 유지하려는 성질|

> [!NOTE]
> DIMM (Dual Inline Memory Module): RAM을 장착하는 표준회로기판

<br>

### 4️⃣ Disk Drive
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/21999142-0cb5-48a1-81fd-9721876cde6a" />

- 비휘발성이며, 순차접근이 가능한 보조기억장치
- 일반적으로 2.5"와 3.5" 크기로 나뉨

#### Drive의 종류
|종류|설명|
|:---:|---|
|HDD<br>(Hard Disk Drive)|· 회전하는 자기 디스크 (Platters)로 데이터를 저장<br>· 가격이 저렴<br>· 대용량을 제공하지만 속도가 느림|
|SSD<br>(Solid State Drive)|· 플래시 메모리 (Flash Memory) 사용으로 HDD보다 속도가 빠름<br>· NVMe 프로토콜을 사용하여 고성능 사양 구성 가능<br>· 가격이 비쌈|

#### Drive 연결방식
|종류|설명|
|:---:|---|
|SATA<br>(Serial ATA)|· 최대 전송속도: 6Gbps<br>· HDD, SSD 모두 지원<br>· 저렴한 가격<br>· 일반 PC 또는 NAS 용도로 사용<br>· 단일 포인트 연결: 1개의 장치를 직접 연결|
|SAS<br>(Serial Attached SCSI)|· 최대 전송속도: 6Gbps (SAS 2.1), 12Gbps (SAS 3.0), 24Gbps (SAS 4.0)<br>· 고속 데이터 전송, SATA보다 2~4배 빠름<br>· 다중 연결 가능: 하나의 포트에 복수의 디스크 연결 가능<br>· 데이터 무결성 및 내구성 강화<br><br>* 무결성: 데이터가 정확하게 유지되는 정도|
|NVMe<br>(Non-Volatile Memory Express)|· 최대 전송속도: 32Gbps (PCIe 3.0), 64Gbps (PCIe 4.0), 128Gbps (PCIe 5.0)<br>· PCIe 인터페이스를 사용하여 고속으로 사용 가능<br>· 병렬처리 최적화: 다중 처리에 강함|

> [!NOTE]
> ATA (Advanced Technology Attachment): 하드디스크 (HDD)와 메인보드를 연결하는 표준 인터페이스 (일종의 규격 이름)
>
> SCSI (Small Computer System Interface): 컴퓨터와 주변 장치 (HDD, CD/DVD 등)를 연결하기 위한 표준 인터페이스
>
> * Gbps: Gbit/s와 같은 표현으로, 1초당 n*10억 bit의 데이터 전송을 의미

<br>

### 5️⃣ Riser Card
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/61f3eae9-e249-47aa-beca-46a0a7aa3b07" />

- 시스템보드 상의 하나의 단자를 통해 복수의 신호라인을 선택해 PCI 단자를 통해 분산시키는 인쇄회로기판
  - 즉, 메인보드의 확장 슬롯 (e.g. PCI Express 슬롯)에 직접 꽂기 어려운 확장 카드를 옆으로 눕혀 연결할 수 있게 해주는 보조카드 (일종의 어댑터)<br><br>* Peripheral: 주변장치, Component: 부품, Interconnect: 상호연결, Express: 고속

> [!NOTE]
> PCIe (PCI Express, Peripheral Component Interconnect Express): 메인보드와 확장 카드 (GPU, NIC 등)를 연결하는 고속 직렬 인터페이스 표준

<br>

### 6️⃣ NIC (Network Interface Card)
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/43328089-903d-4441-b53c-1d215d75106f" />

- 서버가 네트워크에 연결되어 데이터를 송·수신 하게 해주는 부품
- UTP 케이블 (LAN 케이블)로 연결 가능
  - CAT5e: 통신 속도 (최대 전송 속도) = 1Gbps, 전송 대역 (최대 주파수) = 100MHz
  - CAT6: 통신 속도 = 1Gbps, 전송 대역 = 250MHz
  - CAT6A: 통신 속도 = 10Gbps, 전송 대역 = 500MHz
  - CAT7: 통신 속도 = 10Gbps, 전송 대역 = 100MHz
  - CAT8: 통신 속도 = 25/40Gbps, 전송 대역 = 2000MHz
- FC 케이블 (광섬유 케이블, Fiber Optic Cable)로도 연결 가능하며, 네트워크 표시가 있음
- 다중화 지원 (Dual, Quad Port)
  - 네트워크 장애 발생 시, 서비스 중단이 없도록 하기 위함

<br>

### 7️⃣ HBA (Host Bus Adapter 또는 Host Adapter Card)
|<img width="100%" height="100%" src="https://github.com/user-attachments/assets/4d08e424-3604-4990-9bb3-1227ebadca8f" />|<img width="100%" height="100%" src="https://github.com/user-attachments/assets/b00ab5aa-ba4c-44ce-b42a-4a030cb8579e" />|
|:---:|:---:|
|FC HBA|SAS HBA|

<details>
  <summary>
    <h4>1. FC HBA</h4>
  </summary>
  
  - SAN 환경에서 서버를 기타 네트워크와 스토리지 장치에 연결
    - FC HBA 카드는 FC (Fibre Channel, 광채널) 기반 SAN (Storage Area Network)의 장치 간 연결 및 데이터 전송을 가능하게 함
    - _"서버 or PC에 장착된 FC HBA 카드" <---> "SAN 스위치 or 스토리지" 간에 광 케이블을 사용하여 직결_
  - 고속 데이터 전송이 가능, Latency (지연 시간)이 낮고 안정성이 높음
  
  |세대 (Gen)|속도 (Gbps)|
  |:---:|---|
  |1세대|1Gbps|
  |2세대|2Gbps|
  |3세대|4Gbps|
  |4세대|8Gbps|
  |5세대|16Gbps|
  |6세대|32Gbps|
  |7세대|64Gbps|
  ||2배수 (2 times)로 증가|
</details>

<details>
  <summary>
    <h4>2. SAS HBA</h4>
  </summary>
  
  - DAS 환경에서 서버와 스토리지를 직접 연결
  - 대역폭: 6Gbps (SAS 2.1), 12Gbps (SAS 3.0), 24Gbps (SAS 4.0) 존재의
</details>

<br>

### 8️⃣ SFP (Small Form-Factor Pluggable), SFP+
|<img width="100%" height="100%" src="https://github.com/user-attachments/assets/e39b2363-f8cd-4ded-97d1-5e9596e039cb" />|<img width="100%" height="100%" src="https://github.com/user-attachments/assets/e753b685-5eeb-411a-b7a6-b42c3b99e691" />|<img width="100%" height="100%" src="https://github.com/user-attachments/assets/0e1bee6c-e730-41d6-b0ef-eabb4c372d83" />|
|:---:|:---:|:---:|
|Gbic|NIC Mini Gbic (SFP, SFP+)|HBA Mini Gbic (SFP, SFP+)|

- 광신호를 디지털 신호로 바꿔주는 Transceiver
- NIC 전용 및 HBA 전용으로 구별되어 있으며, 둘은 서로 호환되지 않음

> [!NOTE]
> Gbic (Gigabit Interface Converter): 크기가 크고, 1Gbps급 광 트랜시버

<details>
  <summary>
    <h4>1. Mini Gbic</h4>
  </summary>
  
  - 기존의 Gbic을 더 작은 크기로 설계한 것
  - Mini Gbic은 별칭 (Alias)으로, 표준 명칭은 SFP
    - SFP의 최대 속도: 1Gbps
  - SFP+: SFP의 향상된 버전
    - SFP+의 최대 속도: 10Gbps
</details>

<details>
  <summary>
    <h4>2. NIC 전용 SFP+와 HBA 전용 SFP+의 구분법</h4>
  </summary>
  
  - NIC 전용 SFP+ (단위: Gbps): 10G -> 25G -> 40G -> 50G -> ... (뒤로 갈수록 모듈의 종류가 더 향상된 모듈)
  - HBA 전용 SFP+ (단위: GFC): 1G -> 2G -> 4G -> 8G -> 16G -> 32G -> ...
</details>

<br>

### 9️⃣ Disk array Controller (RAID Controller) & Cache Battery
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/b2d5aad0-cbe8-40b5-819c-285482f7ff5f" />

<details>
  <summary>
    <h4>1. RAID Controller</h4>
  </summary>
  
  - 물리적 디스크 드라이브를 관리하고 논리적 유닛 수 (LUN)로 표현하는 장치
  - Input 인터페이스는 디스크와 통신, Output 인터페이스는 HBA와 통신
  - Controller에 따라 제공하는 RAID Level이 다름
</details>

<details>
  <summary>
    <h4>2. Cache Battery</h4>
  </summary>
  
  - 강제 전원 Off, 정전 등 비정상적인 전력 차단 상황에서 아직 디스크에 기록 (Write)되지 않고 RAID Controller의 캐시 메모리에 적재된 데이터들을 디스크에 기록되도록 전력을 공급
  - Vendor마다 명칭이 다름
    - HPE: Smart Storage Battery
    - Fujitsu: BBU (Battery Backup Unit)
</details>

<br>

### 1️⃣0️⃣ PSU (Power Supply Unit)
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/eba82965-be36-421f-89a2-de1022568768" />

- 구동에 필요한 전력을 서버에 공급해주는 전원 공급장치
- 서버 안정성을 위해 이중화 필수

<br>

### 1️⃣1️⃣ CMOS Battery
<img width="50%" height="50%" src="https://github.com/user-attachments/assets/f9f6b24f-ea84-460f-b676-f2f420fb162c" />

- 전력 차단 시, 시스템보드에 담긴 정보 손실을 막기 위해 전력을 공급
- 배터리가 소모되면 boot가 원활하지 않거나 날짜/시간에 오차 발생 가능성
