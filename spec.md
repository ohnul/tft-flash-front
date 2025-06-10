# TFT Flash Play
TFT Flash Play는 전략적 팀전투(TFT) 묘수풀이라는 컨셉의 서비스 입니다.

- 상황별 퀴즈/문제: "이 상황에서 어떤 아이템을 구매해야 할까요?", "어떤 챔피언을 판매하고 어떤 챔피언을 유지해야 할까요?" 등
- 커뮤니티 토론: 각 문제에 대한 다양한 해법과 의견 교환
- 전문가 해설: 상위 랭커나 전문가의 해설 제공
- 실전 시나리오: 실제 게임에서 발생할 수 있는 다양한 상황 시뮬레이션
- 개인 성장 추적: 문제 풀이 정확도, 이해도 등을 시각화하여 제공

## 기술 스택
- 프론트엔드: Next.js 15, React 19, TypeScript, Tailwind CSS 4, shadcn/ui
- 백엔드: Supabase
- 문제 관리: Google Sheets (초기), Supabase 동기화 (추후)
- 배포: AWS
- CI/CD: GitHub Actions
- 버전 관리: Git, GitHub
- 문서화: Markdown
- 커뮤니티: Discord
- 분석 도구: Google Analytics

## 문제 설계

### 문제 데이터 구조
!는 필수 정보. 나머지는 선택사항.

- !라운드 정보
- 다른 플레이어 정보 (7명까지)
    - 대략의 자금
    - 대기석 챔피언
    - 필드 챔피언 (아이템 정보 포함, 등급 정보 포함)
    - 전략가 레벨 (체력 정보 포함)
    - 증강체 정보
- 내 정보
    - 자금
    - !대기석 챔피언 (아이템 정보 포함, 등급 정보 포함)
    - !필드 챔피언 (아이템 정보 포함, 등급 정보 포함)
    - 시너지 정보
    - 전략가 레벨 (Exp 정보 포함, 체력 정보 포함)
    - 연승/연패 정보
    - 증강체 정보
    - 내 아이템
    - 상점 정보
    - 아이템 선택 정보

### 문제 관리 시스템
- 초기 단계: Google Sheets를 활용한 문제 입력 및 관리
  - 비개발자도 쉽게 접근 가능한 인터페이스
  - 실시간 협업을 통한 문제 출제 및 검증
  - 문제 데이터 구조화 및 표준화
- 향후 계획: Google Sheets → Supabase 자동 동기화
  - Google Apps Script 또는 정기 배치 작업 구현
  - 승인된 문제만 Supabase로 이관
  - 서비스는 Supabase에서 데이터 제공

## 구글 시트

### Main_Problems
https://docs.google.com/spreadsheets/d/e/2PACX-1vRca8gsN664nWMDKSMerNFUrgFjXxcfeq9vT4O1nYcUzLXqy6s7fZxl-wozeRuc96XniqyxKgkyYCQO/pub?gid=0&single=true&output=csv

### Player_States
https://docs.google.com/spreadsheets/d/e/2PACX-1vRca8gsN664nWMDKSMerNFUrgFjXxcfeq9vT4O1nYcUzLXqy6s7fZxl-wozeRuc96XniqyxKgkyYCQO/pub?gid=2068211344&single=true&output=csv

### Champions
https://docs.google.com/spreadsheets/d/e/2PACX-1vRca8gsN664nWMDKSMerNFUrgFjXxcfeq9vT4O1nYcUzLXqy6s7fZxl-wozeRuc96XniqyxKgkyYCQO/pub?gid=1927672651&single=true&output=csv

### Shop_Items
https://docs.google.com/spreadsheets/d/e/2PACX-1vRca8gsN664nWMDKSMerNFUrgFjXxcfeq9vT4O1nYcUzLXqy6s7fZxl-wozeRuc96XniqyxKgkyYCQO/pub?gid=939417559&single=true&output=csv

### Solutions
https://docs.google.com/spreadsheets/d/e/2PACX-1vRca8gsN664nWMDKSMerNFUrgFjXxcfeq9vT4O1nYcUzLXqy6s7fZxl-wozeRuc96XniqyxKgkyYCQO/pub?gid=1526512932&single=true&output=csv


---

## 추후 계획

### 문제 설계
- 문제 유형: 상황별 퀴즈, 전략적 선택, 아이템 조합 등
- 난이도: 초급, 중급, 고급으로 구분
- 문제 형식: 객관식, 주관식, 시뮬레이션 등
- 문제 출제: 커뮤니티 참여를 통한 문제 제안 및 검증
- 문제 검증: 상위 랭커나 전문가의 검토를 통한 문제 품질 보증

### 커뮤니티 참여
- Discord 서버 운영: 실시간 소통 및 피드백
- 문제 제안: 커뮤니티 회원이 문제를 제안하고 투표를 통해 채택
- 토론 게시판: 문제에 대한 다양한 의견 교환
- 랭킹 시스템: 문제 풀이 정확도 및 속도에 따른 개인 랭킹 제공

### 전문가 해설
- 상위 랭커나 전문가의 해설 영상 제공
- 해설 내용: 문제 풀이 과정, 전략적 선택 이유, 대안 제시 등
- 해설 영상은 YouTube에 업로드하고 링크를 문제 페이지에 삽입

### 실전 시나리오
- 실제 게임에서 발생할 수 있는 다양한 상황을 시뮬레이션
- 시나리오 예시: 특정 챔피언 조합, 아이템 조합, 경기 상황 등
- 시나리오 기반 문제 풀이: 사용자가 시나리오를 기반으로 문제를 풀고 피드백 제공

### 개인 성장 추적
- 문제 풀이 정확도, 이해도, 속도 등을 시각화하여 제공
- 개인 대시보드: 문제 풀이 기록, 랭킹, 성장 추적 그래프 등
