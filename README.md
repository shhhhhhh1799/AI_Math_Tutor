# 🧮 AI 수학 튜터 시스템 (Mathtutor)

손글씨 수학 문제를 카메라로 인식해 계산하고, LLM(Gemma)을 통해 풀이를 생성한 뒤  
음성으로 설명해주는 **AI 수학 튜터 시스템**입니다.

---

## 📌 프로젝트 개요
이 프로젝트는 **수식 인식 → 자동 계산 → 자연어 풀이 설명 → 음성 출력**까지  
통합한 **AI 기반 수학 학습 보조 시스템**입니다.  
사용자는 카메라 또는 음성으로 수학 문제를 입력할 수 있으며,  
시스템은 단계별로 계산 후 음성으로 설명해줍니다.

> 교육, 튜터링, 자율 학습 등에서 활용할 수 있는 AI 교재 보조 기술을 목표로 합니다.

---

## 🧑‍💻 팀 정보
- **팀명**: Team6_Mathtutor  
- **팀원**: 박승헌, 정민교, 윤종민, 조성현  
- **진행 기간**: 2025.07.01 ~ 2025.07.11  

**역할 분담**
- 🗣️ STT/음성 처리: 박승헌  
- 🔄 통합 흐름 및 테스트: 정민교  
- 🧮 수식 계산 및 Gemma 연동: 윤종민  
- 📸 이미지 처리 및 OCR 연동: 조성현  

---

## ⚙️ 주요 기능
- 📸 **수식 이미지 인식** (Mathpix API 사용)  
- 🧠 **수식 계산** (SymPy – 미분, 적분, 방정식, 푸리에 변환 등 지원)  
- 💬 **자연어 풀이 생성** (Gemma 3B LLM 연동)  
- 🔈 **음성 출력** (gTTS + Speech Rule Engine)  
- 🎤 **음성 입력 지원** (Whisper 기반 STT)  

---

## 🧰 사용 기술
| 영역 | 기술 |
|------|------|
| 프로그래밍 | Python |
| 컴퓨터 비전 | OpenCV |
| 수식 OCR | Mathpix API |
| 수식 계산 | SymPy |
| 자연어 생성 | Gemma 3:12B via Ollama |
| 음성 처리 | Whisper (STT), gTTS (TTS), SRE (수식 발음 규칙) |
| 환경 | Raspberry Pi, Windows, Linux 가능 |

---

## 📁 주요 파일 설명
| 파일명 | 설명 |
|--------|------|
| `main.py` | 전체 파이프라인 제어 및 실행 메인 파일 |
| `server.py` | Ollama 기반 Gemma LLM 서버 실행 파일 |
| `sre.js` | LaTeX 수식 → 음성 변환용 SRE 스크립트 |
| `capture.jpg` | 촬영된 수식 이미지 |
| `recorded.wav` | 음성 녹음 파일 |
| `transcript.txt` | Whisper로 인식한 명령어 텍스트 |
| `gemma3_answer.txt` | Gemma가 생성한 풀이 결과 저장 |
| `output_sre_gtts.mp3` | gTTS로 변환된 음성 설명 결과 |
| `output_sre_gtts.txt` | 음성 출력용 텍스트 저장 파일 |

---

## 🚀 실행 흐름
1️⃣ **사용자 입력**  
   - 이미지 입력 (카메라 촬영)  
   - 음성 명령 입력 (STT)  

2️⃣ 📸 **Mathpix** → 수식 LaTeX 추출  
3️⃣ 🧮 **SymPy** → 계산 수행  
4️⃣ 🤖 **Gemma** → 풀이 설명 생성  
5️⃣ 🔈 **gTTS + SRE** → 음성 설명 출력  

---

## 🎓 학습 목표 및 성과
- 수식 OCR + 계산 + 설명 + 음성 출력까지 통합한 전체 AI 파이프라인 구현  
- 실제 AI 기반 튜터링 시스템의 구성 방식을 실습  
- Raspberry Pi 기반 AI 응용 시스템 구축 경험  

---

## 📂 파일 구조
```plaintext
project_root/
├── main.py
├── server.py
├── sre.js
├── capture.jpg
├── recorded.wav
├── transcript.txt
├── gemma3_answer.txt
├── output_sre_gtts.mp3
└── output_sre_gtts.txt
```
---

## 🔚 마무리 및 확장 가능성
이 프로젝트는 **AI와 음성 기술을 융합**하여 사용자 친화적인 수학 학습 환경을 제공하는 데 중점을 두었습니다.  
특히 수식 인식부터 계산, 자연어 풀이, 음성 안내까지 전 과정을 자동화함으로써,  
시각적·청각적 학습을 동시에 지원하는 **차세대 학습 보조 도구**로 발전 가능성이 있습니다.  

---

## 🔭 향후 확장 방향
- ✍️ **손글씨 직접 입력 UI 연동**  
  (태블릿/터치 스크린 기반 수식 입력 기능 추가)  
- 📶 **모바일 앱 연동 및 실시간 서버 구축**  
  (스마트폰 카메라 활용 및 클라우드 연산 지원)  
- 💡 **사용자 맞춤 학습 피드백 기능**  
  (난이도 분석, 개념 설명 강화, 학습 진도 관리)  
- 🧑‍🏫 **교육 플랫폼과의 연동**  
  (LMS 시스템, 문제은행 자동 분석 및 추천)  
- 🗣️ **다국어 음성 안내 지원**  
  (한국어, 영어, 일본어 등 다국어 학습 지원)  

---

## 📹 시연 영상 👉
[블로그에서 시연 영상 보기](https://blog.naver.com/PostView.naver?blogId=sssssssh17&Redirect=View&logNo=223931109704&categoryNo=1&isAfterWrite=true&isMrblogPost=false&isHappyBeanLeverage=true&contentLength=10476)
