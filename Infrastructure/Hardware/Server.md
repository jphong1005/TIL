# [TIL] Server / Hardware Basic
> Server와 Hardware에 대한 기초 지식
<br>

## 🖥️ Server
### 1️⃣ 서버(Server)란 무엇인가?
네트워크 상에서 **데이터·자원·서비스를 제공하는 시스템**으로, 다른 컴퓨터(Client)의 요청에 따라 **정보를 응답하는 컴퓨터 또는 프로그램**

<br>

### 2️⃣ 서버의 타입
Server는 물리적 형태에 따라 크게 _Rack Server_, _Tower Server_, _Blade Server_, _Micro Server_ 등으로 나뉨
|<img width="100%" height="100%" src="https://www.fujitsu.com/global/imagesgig5/DK80089_tcm100-7104209_tcm100-5309118-32.png"/>|<img width="100%" height="100%" src="https://www.fujitsu.com/global/imagesgig5/292031_tcm100-6611255_tcm100-5309118-32.png"/>|<img width="100%" height="100%" src="https://www.fujitsu.com/kr/Images/107468_tcm119-40715.png"/>|<img width="100%" height="100%" src="https://jp.fujitsu.com/platform/server/primergy/product-navi/image/mx130s2-201111.jpg"/>|
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
