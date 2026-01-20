### UNIBUS – 실시간 통학버스 위치 제공 서비스

<div align="center">
  <h1>🚌 UNIBUS – 인천대학교 실시간 통학버스 위치 제공 앱서비스</h1>
  <p>🚍 GPS·ETA 기반으로 인천대생의 이동을 하나로 잇는 캠퍼스 모빌리티 플랫폼 🚍</p>
</div>

<br/>

<div align="center">
  <img src="https://github.com/user-attachments/assets/d889abb3-68be-48f0-94f0-d036a54ed13d" alt="Main" width="100%"/>
</div>

<br/>

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

『 유니버스(UNIBUS) 』는 인천대학교의 학우를 뜻하는 “유니(Uni)”와 </br>
 “버스(Bus)”를 결합한 이름으로, 인천대생을 하나의 연결된 공간(Universe)으로 묶는 </br>
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

1. **로그인 및 지도 확대·축소**

	- 로그인 후 메인 지도 화면 진입
	- 지도 드래그/확대·축소로 주변 정류장/노선 확인
	- Android Google Maps SDK를 활용해 지도 화면 제공
<table align="center">
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/7c57f2f3-68f2-4a49-ae56-0b51de71213a"
           alt="로그인 및 지도 확대/축소 시연"
           width="200"/>
    </td>
  </tr>
</table>

2. **[등교/하교] 셔틀버스 실시간 위치 / 시내버스 도착 정보 보기**
	- 셔틀버스 실시간 위치
		- **GPS Module → NMEA 데이터 스트림 → Raspberry Pi** </br>
          **reading/parsing 후 → Backend(FastAPI/Uvicorn)** 순으로 좌표 수집
		- 앱은 서버에서 전달받은 위치를 지도에 실시간 반영
	- 시내버스 도착 정보
		- 공공데이터 포털 API를 통해 정류장 도착 정보 조회/표시
<table align="center">
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/093f4e00-dd12-492d-b2bb-0f32fc69462e"
           alt="등교: 셔틀 실시간 위치 + 시내버스 도착 정보 시연"
           width="200"/>
      <br/>
      <b>등교</b>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/755af404-228e-4134-966f-6446db16ac7c"
           alt="하교: 셔틀 실시간 위치 + 시내버스 도착 정보 시연"
           width="200"/>
      <br/>
      <b>하교</b>
    </td>
  </tr>
</table>

3. **호관별 건물 도착 예측 / 예측 분석 + 최적 경로 지도 보기 (미구현)**
	- 정류장 → 호관(건물)까지의 도착 예측 및 분석 리포트 제공
	- Tmap API 기반 최적 경로를 지도에 시각화 (MVP 미구현)
<table align="center">
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/639a85ef-eba7-47ec-b627-f82f0c2f5f73"
           alt="호관별 도착 예측/분석"
           width="200"/>
    </td>
  </tr>
</table>

4. **셔틀버스 알림 설정 및 관리**
	- 즐겨찾기 정류장/노선 기반으로 알림 조건 설정 및 관리
	- 서버에서 계산/수집되는 최신 위치/도착 정보에 따라 도착 임박 알림 제공
	- 설정/즐겨찾기/알림 상태 등은 서버에 저장하여 일관성 있게 관리
<table align="center">
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/d6090f38-e7e0-4fbd-92d2-5682d15624e4"
           alt="셔틀버스 알림 설정 및 관리 시연"
           width="200"/>
    </td>
  </tr>
</table>

5. **설문 기반 도착 정보 공유**
	- 사용자 설문 응답을 기반으로 도착 체감/혼잡 등 보조 정보를 공유
	- 수집된 설문 데이터는 서버에서 저장·집계 후 화면에 반영
<table align="center">
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/8923bb3a-265b-4482-9463-5d8658992c8e"
           alt="설문 기반 도착 정보 공유 시연"
           width="200"/>
    </td>
  </tr>
</table>

6. **미추홀 캠퍼스 셔틀버스 시간표 제공**
	- 미추홀 캠퍼스 셔틀버스 시간표 정보 제공
	- 추후 서비스 확장 시 송도캠퍼스와 동일하게 실시간 위치 정보 제공 예정
<table align="center">
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/17d92181-90aa-4e55-a3b1-592a2ac180cd"
           alt="셔틀버스 시간표 제공 시연"
           width="200"/>
    </td>
  </tr>
</table>

---

## 🧑‍💻 팀원 소개

| **이름** | **역할** | **담당 업무** |
|:--------:|:--------:|:-------------|
| <a href="https://github.com/smiinii"><img src="https://avatars.githubusercontent.com/smiinii" width="70px" style="border-radius:50%"/><br/><sub><b>이성민</b></sub></a> | BE / IoT | - GPS 모듈 및 Raspberry Pi 설정·연동<br/>- 프로젝트 PPT 제작 |
| <a href="https://github.com/fostacion"><img src="https://avatars.githubusercontent.com/fostacion" width="70px" style="border-radius:50%"/><br/><sub><b>이융현</b></sub></a> | FE / BE |- FastAPI 서버 구축<br/>- 전반적인 ETA 알고리즘 구조 설계<br/>- 경로 폴리라인 구축 및 지도 시각화 |
| <a href="https://github.com/limwr706"><img src="https://avatars.githubusercontent.com/limwr706" width="70px" style="border-radius:50%"/><br/><sub><b>임완렬</b></sub></a> | FE / Design | - 전체 UI/UX 설계 및 화면 디자인<br/>- 지도 기반 화면 구성<br/>- 셔틀버스 알림 설정 기능 구현 |
| <a href="https://github.com/yim0327"><img src="https://avatars.githubusercontent.com/yim0327" width="70px" style="border-radius:50%"/><br/><sub><b>임재영</b></sub></a> | BE / Docs | - FastAPI 서버 구축<br/>- 외부 API 및 설문 데이터 기반 ETA 알고리즘 보정 설계<br/>- README 작성 |
| <a href="https://github.com/hantaee22"><img src="https://avatars.githubusercontent.com/hantaee22" width="70px" style="border-radius:50%"/><br/><sub><b>한태연</b></sub></a> | Design / IoT | - GPS 모듈 및 Raspberry Pi 설정·연동<br/>- 화면 디자인<br/>- IEEE 형식 기반 프로젝트 보고서 작성 |

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
      <td><b>Hardware / IoT</b></td>
      <td>
        <img src="https://img.shields.io/badge/Raspberry_Pi-A22846?style=flat&logo=raspberrypi&logoColor=white"/>
        <img src="https://img.shields.io/badge/GPS_Module-0055FF?style=flat&logo=gnss&logoColor=white"/>
      </td>
    </tr>
    <tr>
      <td><b>Backend</b></td>
      <td>
		<img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white"/>
        <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white"/>
        <img src="https://img.shields.io/badge/Uvicorn-A843A3?style=flat&logo=gunicorn&logoColor=white"/>
        <img src="https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white"/>
      </td>
    </tr>
    <tr>
      <td><b>Mobile (Frontend)</b></td>
      <td>
        <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat&logo=kotlin&logoColor=white"/>
        <img src="https://img.shields.io/badge/Android_Studio-3DDC84?style=flat&logo=android&logoColor=white"/>
        <img src="https://img.shields.io/badge/Google_Maps_SDK-4285F4?style=flat&logo=googlemaps&logoColor=white"/>
      </td>
    </tr>
    <tr>
      <td><b>External API</b></td>
      <td>
        <img src="https://img.shields.io/badge/Kakao_Map_API-FFCD00?style=flat&logo=kakaotalk&logoColor=black"/>
        <img src="https://img.shields.io/badge/Tmap_API-5A2EFF?style=flat&labelColor=5A2EFF"/>
	    <img src="https://img.shields.io/badge/Public_Data_API-0033A0?style=flat"/>
      </td>
    </tr>
  </tbody>
</table>

<!-- https://img.shields.io/badge/{배지이름}-{css컬러}?style={스타일}&logo={로고}&logoColor={로고컬러} -->

---

## 📐 아키텍쳐

<div align="center">
  <img src="https://github.com/user-attachments/assets/4ba6e4e2-7491-4c7b-af35-050703efb5fa" alt="UNIBUS_Architecture" width="70%"/>
</div>

---

## 🗄️ ERD

<div align="center">
  <img src="" alt="UNIBUS_ERD" width="70%"/>
</div>

---

<div align="center">

<h3>🎓 <strong>"Because getting to campus should be simple"</strong></h3>
<p>바쁜 하루 속에서, 매일의 통학이 조금 더 편해지기를.</p>

</div>
