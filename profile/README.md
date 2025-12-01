### UNIBUS – 실시간 통학버스 위치 제공 서비스

<div align="center">
  <h1>🚌 UNIBUS – 인천대학교 실시간 통학버스 위치 제공 앱서비스</h1>
  <p>🚍 GPS·ETA 기반으로 인천대생의 이동을 하나로 잇는 캠퍼스 모빌리티 플랫폼 🚍</p>
</div>

<br/>

<div align="center">
  <img src="https://github.com/user-attachments/assets/65f6186a-03e2-436e-9d32-cf8492cd69d8" alt="Main" width="100%"/>
</div>

<br/>

<div align="center">
  <a /**href="https://"**/">홈페이지</a>
    |  
  <a /**href="https://"**/>Swagger</a>
    |  
  <a /**href="https://"**>Notion</a>
</div>

---

## ✍️ 프로젝트 개요

- **프로젝트명:** UNIBUS (유니버스)
- **프로젝트 기간:** 2025.09 ~ 2025.12
- **프로젝트 형태:** 인천대학교 모바일 프로그래밍 / IoT 융합 프로젝트
- **목표:** 통학버스의 **실시간 위치 추적과 도착 예측(ETA)** 을 제공하는 캠퍼스 맞춤형 앱서비스 구축
- **핵심 가치:**
  - 버스 대기 불편 해소
  - 교통 정보 실시간화
  - 통학 효율 향상

---

## ✨ 서비스 소개

『 유니버스(UNIBUS) 』는 인천대학교(University of Incheon)의 “유니(Uni)”와  
“버스(Bus)”를 결합한 이름으로, 인천대생을 하나의 연결된 공간(Universe)으로 묶는  
**실시간 통학버스 위치 제공 앱서비스**입니다.

</br>

### 🚏 서비스 배경 (문제 인식)
- 인천대 통학버스는 실시간 위치 정보 제공 수단이 없어, 학생들은 정류장에서 장시간 대기해야 함
- 버스 지연 여부를 확인할 방법이 없어, 이동 효율성이 떨어지고 불편 증가
- 기존 대중교통 앱은 일반 노선 중심이라, **대학 통학버스에 특화된 기능 부재**

</br>

### 💡 서비스 핵심 아이디어
- 통학버스에 **라즈베리파이 + GPS 모듈** 설치 → 위치 정보 실시간 수집
- **FastAPI 서버**에서 데이터 수집·저장 및 ETA 계산
- **Android 앱**을 통해 지도 기반으로 버스 위치와 예상 도착 시간 표시

---

<!-- 주요 기능에 서비스 시연 사진 및 부가 설명 덧붙이기 -->

## 🚀 주요 기능

1. **실시간 위치 추적**
   - GPS 모듈이 2~3초마다 버스 좌표를 전송
   - 앱은 WebSocket을 통해 실시간으로 지도에 표시

<div align="center">
  <img src="https://github.com/user-attachments/assets/xxxxxx" alt="실시간 지도 시연" width="80%"/>
</div>

2. **ETA(도착예정시간) 계산**
   - FastAPI 서버에서 T map / NAVER Directions API를 활용
   - 교통 상황 기반으로 각 정류장별 예상 도착 시간 산출

<div align="center">
  <img src="https://github.com/user-attachments/assets/xxxxxx" alt="ETA 계산 시연" width="80%"/>
</div>

3. **정류장별 도착 알림**
   - 사용자가 즐겨찾기한 정류장에 도착 임박 시 푸시 알림 전송
   - WorkManager를 이용한 주기적 ETA 모니터링

<div align="center">
  <img src="https://github.com/user-attachments/assets/xxxxxx" alt="정류장 알림 시연" width="80%"/>
</div>

4. **지도 기반 UI/UX**
   - Google Maps API 기반 실시간 지도
   - 노선, 정류장, 버스 마커를 직관적으로 표시

<div align="center">
  <img src="https://github.com/user-attachments/assets/xxxxxx" alt="UX/UI 시연" width="80%"/>
</div>

---

## 🧑‍💻 팀원 소개

| **이름** | **역할** | **담당 업무** |
|:--------:|:--------:|:-------------|
| <a href="https://github.com/smiinii"><img src="https://avatars.githubusercontent.com/smiinii" width="70px" style="border-radius:50%"/><br/><sub><b>이성민</b></sub></a> | BE / Docs | Raspberry Pi GPS 연동, 보고서 및 문서화, 배포 환경 구성 |
| <a href="https://github.com/fostacion"><img src="https://avatars.githubusercontent.com/fostacion" width="70px" style="border-radius:50%"/><br/><sub><b>이융현</b></sub></a> | BE / Mobile | FastAPI 서버 구성, ETA 알고리즘 설계, DB 모델링 |
| <a href="https://github.com/limwr706"><img src="https://avatars.githubusercontent.com/limwr706" width="70px" style="border-radius:50%"/><br/><sub><b>임완렬</b></sub></a> | FE / UX | UI 디자인, 기능 BE-FE 연동, 시간표 알람설정 등 추가 기능 구현 |
| <a href="https://github.com/yim0327"><img src="https://avatars.githubusercontent.com/yim0327" width="70px" style="border-radius:50%"/><br/><sub><b>임재영</b></sub></a> | BE / Mobile | FastAPI 서버 구성, API 연동, 서버 구조 설계 |
| <a href="https://github.com/hantaee22"><img src="https://avatars.githubusercontent.com/hantaee22" width="70px" style="border-radius:50%"/><br/><sub><b>한태연</b></sub></a> | FE / Docs | Raspberry Pi GPS 연동, 보고서 및 문서화, UI 디자인 |

---

## ⚙️ 기술 스택

<table>
  <thead>
    <tr>
      <th>분류</th>
      <th>기술 스택</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Hardware</td>
      <td>
        <img src="https://img.shields.io/badge/Raspberry_Pi-A22846?style=flat&logo=raspberrypi&logoColor=white"/>
        <img src="https://img.shields.io/badge/GPS_Module-0055FF?style=flat&logo=gnss&logoColor=white"/>
        <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white"/>
        <img src="https://img.shields.io/badge/pynmea2-3776AB?style=flat&logo=python&logoColor=white"/>
      </td>
    </tr>
    <tr>
      <td>Backend</td>
      <td>
        <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white"/>
        <img src="https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white"/>
        <img src="https://img.shields.io/badge/PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white"/>
        <img src="https://img.shields.io/badge/PostGIS-0064A5?style=flat&logo=qgis&logoColor=white"/>
        <img src="https://img.shields.io/badge/AWS_EC2-FF9900?style=flat&logo=amazonec2&logoColor=white"/>
      </td>
    </tr>
    <tr>
      <td>Mobile</td>
      <td>
        <img src="https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white"/>
        <img src="https://img.shields.io/badge/Android_Studio-3DDC84?style=flat&logo=androidstudio&logoColor=white"/>
        <img src="https://img.shields.io/badge/Google_Maps_API-4285F4?style=flat&logo=googlemaps&logoColor=white"/>
        <img src="https://img.shields.io/badge/WebSocket-6DB33F?style=flat&logo=websocket&logoColor=white"/>
        <img src="https://img.shields.io/badge/WorkManager-555555?style=flat&logo=android&logoColor=white"/>
      </td>
    </tr>
    <tr>
      <td>Infra & Deployment</td>
      <td>
        <img src="https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white"/>
        <img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white"/>
        <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white"/>
      </td>
    </tr>
  </tbody>
</table>

<!-- https://img.shields.io/badge/{배지이름}-{css컬러}?style={스타일}&logo={로고}&logoColor={로고컬러} -->

---

## 📐 아키텍쳐

<div align="center">
  <img src="https://github.com/user-attachments/assets/f0178978-a060-49dd-affe-9f9a93e6e424" alt="I:Dam_Architecture" width="70%"/>
</div>

---

## 🗄️ ERD

<div align="center">
  <img src="https://github.com/user-attachments/assets/8f5266ca-4bbd-4b6b-aedf-d774b35eeb81" alt="I:Dam_ERD" width="70%"/>
</div>

---

<div align="center">

<h3>💡 <strong>IDam connects, IDam reflects.</strong> 💡</h3>
<p>이담은 <strong>연결</strong>하고, 기업의 <strong>가치</strong>를 비춰줍니다.</p>

</div>
