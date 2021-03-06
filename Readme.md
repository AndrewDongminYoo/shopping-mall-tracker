## 프로그램 구성
- chromedriver.exe
  - 웹크롤링에 사용되는 크롬드라이버입니다. 사용하시는 크롬 브라우저와 버전을 맞춰야 할 수 있습니다.
- naver_search.exe
  - 크롤링 취합자료.xlsx의 상품코드를 읽고
  - 네이버 쇼핑검색 API를 활용해 지정하신 가격에 미달하는 상품을 찾아
  - 방문해 두번의 리다이렉팅 주소를 저장해
  - 상품 정보와 해당 상호명을 result-**.csv에 저장합니다.
- prod.env
  - 환경변수로 사용되는 파일입니다. 네이버 쇼핑검색 API에 사용되는 키값을 입력해줍니다.
  - 제가 등록한 API 키가 입력되어 있으며, 원하시면 네이버 개발자도구를 통해 발급받아 입력하실 수도 있습니다.
- 크롤링 취합자료.xlsx
  - 저한테 주셨던 파일 그대로입니다.
  - 첫번째 시트(아이템 정보)에 있는 모든 데이터를 실행파일이 인식하고 있기 때문에
  - 데이터 수정은 자유로우나 시트명과 시트 내 서식을 교체하면 프로그램이 작동하지 않습니다.

## 각 요소 주의사항
- naver_search.exe 외 다른 파일들은 이름이나 위치를 수정하시면 안됩니다.
- 모든 파일들은 같은 폴더에 위치해야 합니다.
- 크롤링 취합자료.xlsx는 엑셀 파일 포맷과 첫번째 시트명을 수정하시면 안됩니다.
- 크롤링 취합자료.xlsx의 매장정보는 수기로 프로그램에 복사되어 있어 해당 시트를 수정해도 자동으로 값이 갱신되지는 않습니다.
- 이 부분은 저에게 말씀해주시면 언제든 업데이트 도와드리겠습니다.
- 일반적인 환경에서 각 코드마다 최대 100개의 사이트를 불러오고 이를 순차방문하기 때문에 코드 하나당 길게는 2분 정도 소요됩니다.
- 특정 스타일코드 (예: 26번부터 29번까지)만 프로그램을 돌리고 싶으시면 아이템정보 시트 외에 다른 시트에 복사본을 두시고 아이템정보 시트를 수정하고 프로그램을 돌리시면 됩니다.
- 프로그램은 스타일코드를 한글명칭보다 우선하여 작동하기 때문에 한글명은 자유롭게 바꾸셔도 됩니다.
- 현재 코드는 쇼핑검색에 해당 상품 스타일코드를 검색하여 최대 100개의 상품을 불러옵니다. 이 숫자는 변경 가능하니 필요 시 문의 바랍니다.

## 결과물
- A열 : 해당 스타일코드의 원본 인덱스 값입니다.
- B열 : 스타일코드입니다.
- C열 : 한글명입니다. 실제 쇼핑몰에서 판매되고 있는 상품명을 가져옵니다.
- D열 : 해당 상품 내에 있는 A/S연락처입니다. 데이터베이스에 존재하는 연락처일 경우 한글 상호명으로 입력됩니다.
- E열 : 해당 상품 상세설명에 있는 상품코드에 지점 넘버가 있는 경우 해당 상호명을 가져옵니다. (AS -> 안산점)
  - D열에 값이 전화번호만 가져온 경우 E열을 참고하시는 식으로 보시면 됩니다.
- F열 : 원본 엑셀파일에 있는 시즌입니다.
- G열 : 해당 쇼핑몰에서 판매되고 있는 가격입니다.
- H열 : 엑셀파일에서 지정하신 공식할인가격입니다.
- I열 : 공식할인가격에 네이버 쇼핑검색 루트 접속 할인 등 기타 할인 (10%) 적용가격입니다.
  - G열이 I열의 값보다 큰 경우는 없습니다. 기준가격입니다.
- J열 : 상품을 판매 중인 쇼핑몰 사이트입니다. 주요 사이트에 해당되는 경우 한글명으로 출력됩니다.
- K열 : 네이버쇼핑검색에 나와있는 사이트를 클릭하면 자동으로 리다이렉트가 두번 일어납니다. 그 최종 주소입니다.

## 요청 사항
- 프로그램을 찬찬히 보시고 어려운 점이 있으시면 연락주세요.
- 사후 서비스는 모두 열려 있으며 간단한 수정이나 파일명 변경 등은 비용없이 해드리겠습니다.
- 크몽 판매를 새로 시작하여 리뷰 써주시면 무한 감사드리겠습니다.
- 요구사항을 최대한 충족시키려 했으나 저 혼자 만든 프로그램이다 보니 원하시는 부분과 다를 수 있습니다. 시일 내 의견 내 주시면 적극 반영하겠습니다.
- 맡겨주셔서 감사합니다. 번창하세요.
