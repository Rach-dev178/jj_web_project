# 🎼 Composer of the Day - CSS 구조 및 애니메이션 보고서

## 1. 스타일 구성 구조

| 파일명           | 역할                                       |
|------------------|--------------------------------------------|
| styles.css       | 모든 스타일 파일을 @import로 통합          |
| animetions.css   | 공통 애니메이션 효과 정의                   |
| main_main.css    | 메인 페이지 작곡가 리스트 디자인            |
| cotd.css         | 오늘의 작곡가 섹션 (motd) 전용              |
| chopin.css       | 작곡가 개별 상세 페이지 전용 스타일         |

## 2. 주요 레이아웃 설계

### index.html 기준
- `.motd`: "Composer of the Day" 메인 타이틀 영역
- `.motd__main`: 오늘의 작곡가 소개 섹션 (이미지 + 설명 텍스트)
- `.main_main`: 작곡가 목록 (리스트 형식의 카드)

### 작곡가 상세 페이지 (ex: chopin.html)
- `.composer`: 전체 페이지 여백 및 배경색 지정
- `.composer__imgbox`: 이미지 + 텍스트 설명 병렬 배치
- `.discs`: 3개의 회전형 디스크(음악 링크) 영역

## 3. 애니메이션 기능

| 애니메이션 이름 | 적용 대상           | 설명                                     |
|------------------|----------------------|------------------------------------------|
| liftUp           | .main_main__box:hover| 카드가 위로 들리는 듯한 입체 효과        |
| dropDown         | hover 해제 시        | 다시 원래 자리로 서서히 내려감           |
| liftUpDown       | .motd__main__box__img| 대표 이미지가 천천히 위아래로 부유 (loop)|

### 기술 요소
- transform: scale + rotateX + rotateY + translateY
- box-shadow를 통한 깊이감 부여
- will-change로 GPU 최적화

## 4. 시각 디자인 및 UX 요소

- border-radius: 30px로 통일감 있는 디자인
- hover 시 인터랙션 효과 적극 활용
- 향후 .discs_d__img에 회전 애니메이션 적용 가능

## 5. 개선/확장 제안

| 제안 항목             | 설명                                                  |
|------------------------|--------------------------------------------------------|
| 디스크 회전 효과 추가 | hover 시 rotate() 적용                                 |
| 반응형 디자인         | @media 쿼리 적용 추천                                  |
| 다크 모드             | .dark 클래스로 테마 전환 기능                          |
| 공통 클래스 리팩토링  | main_main__box__lift → card--lift 식으로 단순화 가능   |