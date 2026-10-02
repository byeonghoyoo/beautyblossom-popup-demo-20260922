# 뷰티블라썸 7개국 공통 팝업 — 컨펌용 목업

공유주소는 `04-live-events-preview.html` 그대로 유지합니다. 현재 운영 홈페이지에는 새 팝업을 설치하지 않았습니다.

- 하단: 공지사항 → 프로모션 → 이벤트 → 병원소개. 처음 열리는 화면은 기존 승인본과 같은 이벤트입니다.
- 상단 국가 선택: 한국 / 영어 / 일본 / 중국 / 대만 / 태국 / 홍콩. 각 홈페이지의 실제 게시판을 사용합니다.
- 공지·프로모션·이벤트: 대표 이미지, 게시 순서, 게시글 링크 자동 반영. 열 때 조회하고 열린 상태에서 60초 간격으로 갱신합니다. 서버 캐시 60초를 포함하면 변경 반영은 통상 1~2분 내입니다. 즉시 푸시 방식은 아닙니다.
- 병원소개: 실제 6층 로비·8층 프리미엄 라운지 사진. 정적 이미지입니다.
- PC 3열 / 모바일 1열. 게시물 이미지 전체 비율 유지. 1.8초 간격, 0.6초 디졸브, 이전·다음·일시정지 지원. 마지막 남은 게시물도 표시합니다.
- 이미지 없는 글은 제목 카드로 표시합니다. 조회 실패 시 이전 가격 이미지를 유지하지 않고 재시도 및 원본 게시판 링크를 표시합니다.
- 오늘 하루 보지 않기: 방문 기기의 해당 국가 팝업을 다음 자정까지 숨깁니다. 수동 다시 열기는 가능합니다.

## 컨펌 후 설치 파일

`04-live-events-code-KO.txt`, `-EN.txt`, `-JP.txt`, `-CN.txt`, `-TW.txt`, `-TH.txt`, `-HK.txt`를 준비했습니다. 국가 지정 파일을 각 사이트에 적용합니다. 공통 `04-live-events-code.txt`는 공식 호스트를 자동 판별합니다. 미리보기 국가 선택기는 설치 코드에는 포함되지 않습니다.

기존 vanilla HTML/CSS/JS 위젯 구조를 유지했습니다. 요청한 React 예제의 카드 모서리, 입체 선택 버튼, 이동하는 선택 배경을 이 구조에 적용했으며 새 React 런타임이나 외부 폰트 의존성은 추가하지 않았습니다.

## 연동 원본

| 국가 | 공지 | 프로모션 | 이벤트 |
|---|---|---|---|
| KO | beautyblossom.kr/20 | /promotion | /22 |
| EN | en.beautyblossom.kr/20 | /promotion | /22 |
| JP | jp.beautyblossom.kr/20 | /promotion | /22 |
| CN | cn.beautyblossom.kr/20 | /promotion | /22 |
| TW | tw.beautyblossom.kr/20 | /promotion | /22 |
| TH | www.beautyblossomth.kr/notice/ | /promotion/ | /events/ |
| HK | hk.beautyblossom.kr/notice | /promotion | /events |

피드: 기존 `beautyblossom-popup-feed.beautyblossom.workers.dev`의 `/notices`, `/promotions`, `/events`와 `country` 파라미터. 기존 국가 미지정 `/events`는 한국 이벤트로 호환됩니다. 공개 게시물만 읽으며 CMS 로그인/작성/삭제는 수행하지 않습니다.
