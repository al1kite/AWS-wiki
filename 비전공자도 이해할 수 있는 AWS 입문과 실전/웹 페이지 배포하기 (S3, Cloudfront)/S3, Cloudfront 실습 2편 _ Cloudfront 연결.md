## Cloudfront 실습하기

<img width="976" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/dffd373f-c9ac-4589-aa91-a732e6c631ae">

원본 도메인을 선택하라 하는데, 원본 도메인이란 클라우드 프론트에서 실질적인 원본 파일이 어디에 있느냐를 물어보는 건데, 이는 S3에 있다.
클릭하면 정적 웹사이트 호스팅 주소가 뜰테니 그걸 선택해주면 된다.
그리고 경고로 나오는 `웹 사이트 앤드포인트 사용` 을 눌러준다.
내부적인 작동 과정으로 이렇게 사용하는게 더 효율적이라는 뜻이다.

<img width="644" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/542d29e4-a1dc-4981-bb43-ae286f126476">

그 후 기본 캐시 동작에서 뷰어 프로토콜 정책을 `Redirecr HTTP to HTTPS` 로 변경해준다.
HTTP로 들어오는 건 전부 HTTPS로 강제로 변환시켜 보완성이 낮은 HTTP로 통신하는 걸 막아주는 정책이다.

<img width="682" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/357a660b-fc26-4742-bc98-dd88f127c3f3">

이후 설정에서 컨텐츠, 아까 본 클라우드 프론트 임시 저장소를 세계 곳곳에 두고 있었는데 그 곳곳에서 어떤 임시저장소를 몇개나 사용할 건지에 따라 가격이 달라진다.북미, 유럽, 아시아로 클릭하고 넘어간다.
그리고 기본 루트 객체 생성으로는 index.html 을 입력해주고 넘어간다.

<img width="729" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/ca5dbfee-dd94-41af-b5d4-e40b14471549">

그럼 다음과 같이 배포된다.

<img width="1095" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/f24968db-ff4e-4e4d-8f5e-257993c61f74">

배포 도메인 이름이란, 사용자가 클라우드 프론트한테 요청을 보내 그 웹페이지를 전달받는 느낌이기 때문에 우리가 알아야하는 주소는 S3 주소가 아닌 클라우드 프론트 주소를 알아야 하고
클라우드 프론트 주소를 통해 접근해야 하는데 그 주소가 바로 배포 도메인 이름이다.

### 도메인 연결하기

HTTPS 를 적용할 때 가장 선행되어야 하는 건, 인증서를 가장 먼저 발급 받아야 한다.
특징 중 하나는, 클라우드 프론트는 HTTPS 를 적용하려면 인증서를 서울이 아니라 미국 동부 버지니아 북부에서 발급받아야 한다.

<img width="1038" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/826e4568-51f6-451d-9fea-4e4714121e15">

따라서 버지니아 북부 리전으로 들어가 인증서를 요청해준다.

<img width="839" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/0d6b14e3-0efa-429f-b515-3b4e43c3e727">

원하는 도메인 이름을 입력해주는 DNS 검증 설정 그대로 요청을 눌러준다.

<img width="1071" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/fd1914b8-c164-40f6-9584-b654e812f080">

그렇게 생성된 인증서에서 `Route53 레코드 생성`을 눌러준다.

<img width="880" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/a6cfad12-e65a-4bdd-89dd-390e7d9912bc">

그리고 내가 생성한 도메인의 DNS 레코드를 생성해주면 되는데.. 난 도메인을 안사서 레코드 생성을 못 한다
원래는 도메인 검증까지 마친 후 인증서를 발급받아 클라우드 프론트에서 인증서를 적용해준다.

<img width="1098" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/90d6902d-8da9-4651-b439-63fb162d1466">

인증서 발급까지 마치면 클라우드 프론트로 돌아가 설정에 편집을 누른다.

<img width="860" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/589b8121-244c-4dc0-bfd9-26727275822d">

그리고 대체 도메인 이름을 선택해주고 사용자 SSL 인증서에서 아까 발급 받은 인증서를 추가해준다.

이렇게 인증서를 적용하면 이젠 route53 에서 클라우드프론트의 도메인을 연결해줘야 한다.
이후의 과정은 내가 도메인을 살 생각이 들면 다시 진행해볼 예정.