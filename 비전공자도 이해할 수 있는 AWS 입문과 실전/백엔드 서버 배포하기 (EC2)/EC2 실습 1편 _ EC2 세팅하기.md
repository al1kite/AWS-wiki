## 리전(Region) 선택하기

### 1. EC2 에 들어가 가장 먼저 리전을 선택한다

![img](https://github.com/al1kite/AWS-wiki/assets/102217402/f1f9d6b5-14db-4b09-b1f9-df794fd64cc2)
   
리전(Region)이란 인프라를 지리적으로 나누어 배포한 각각의 데이터 센터를 의미. <BR>
EC2를 통해 빌려서 쓸 수 있는 컴퓨터들이 전 세계적으로 다양하게 분포해있다. <BR>
이렇게 컴퓨터들이 위치한 위치를 보고 AWS에서는 리전(Region)이라고 한다. <BR>
각 Region은 고유의 이름을 가지고 있다. (서울의 경우 ap-northeast-2) <BR>
    
사람들이 애플리케이션을 사용할 때는 네트워크를 통해 통신하게 된다. <BR>
이 때, 사용자의 위치와 애플리케이션을 실행시키고 있는 컴퓨터와 위치가 멀면 멀수록 속도가 느려진다. <BR>
따라서 애플리케이션의 주된 사용자들의 위치와 지리적으로 가까운 리전(Region)을 선택하는 것이 유리하다. <BR>

참고: 리전(Region)마다 EC2가 따로따로 관리가 되고 있으니 유의

### 2. 리전 세팅하기 - 기본 설정

인스턴스 시작을 눌러줍니다. AWS 를 익히는 핵심 중 하나는 모든 걸 익히려고 하면 안되고 파레토의 법칙에 따라 중요한 걸 부분적으로 학습.
![image](https://github.com/al1kite/AWS-wiki/assets/102217402/82cd5a09-dcf0-45e9-b1b4-d8cac0cf8cd6)

이름 및 태그는 나중에 서버 종류를 다양하게 가져갈 수도 았기에 여러 컴퓨터를 빌리게 될텐데, (기능별로 나눌 수도 있고 개발용 서버, 배포용 서버로 나눌 수도)
일반적으로 이 이름은 그런 여러 가지의 컴퓨터들을 나중에 EC2 인스턴스를 사용하게 될텐데 그 EC2 인스턴스끼리 각각 분리해서 어떤 건지 식별 가능하게끔
하는 이름을 작성하면 된다. 보통 서비스의 이름으로 많이 작성.

![image](https://github.com/al1kite/AWS-wiki/assets/102217402/af9ac18e-9f1b-4252-a19a-4d3ec1e1ec55)

그 후, 내려가면 Application and OS Images (Amazon Machine Image)가 있다. 이는 OS를 선택하는 단계이다. <BR>
우리가 실제 컴퓨터를 고를 때 윈도우를 살지 맥을 살지를 고민하는데, 그런 것처럼 우리가 어떤 OS를 가진 컴퓨터를 살 건지를 선택하는 창이다.

우리는 우분투를 쓸 생각이다. 실제 맥과 윈도우 운영체제는 컴퓨터를 잘 모르는 사람도 쉽게 쓰게 하기 위해 여러 편한 기능들을 너무 많이 넣어놨다. 
그러다 보니 용량도 많이 차지하고 성능도 많이 잡아먹는다. 서버를 배포할 때는 그런 용량과 성능을 많이 차지한다면 서버의 성능이 떨어지다 보니 최대한 서버를 배포할 때
필요한 기능만 들어가 있는 OS 를 선택하는게 유리하기에 우분투를 사용한다. 버전은 그냥 최신 버전 사용.
![image](https://github.com/al1kite/AWS-wiki/assets/102217402/374d6e2a-6144-4e29-a922-849f643ee71f)

다음 인스턴스 유형이 있다. 이때 인스턴스란 AWS EC2에서 빌리는 컴퓨터 1대를 의미한다. <BR>
인스턴스 유형이란 컴퓨터 사양을 의미한다. 컴퓨터 사양이 좋으면 좋을수록 많은 수의 요청을 처리할 수 있고, 무거운 서버나 프로그램을 돌릴 수 있다.

프리 티어에 해당하는 t2.micro를 사용할 것. 걱정하는 것 보다 나름 괜찮은 사양. 하루 방문자 수가 2,000명 정도였던 서비스를 운영했었는데 문제 없이 잘 돌아갔다.
![image](https://github.com/al1kite/AWS-wiki/assets/102217402/9dd3915e-0193-4d6a-a2c4-08fe872f4beb)

더 메뉴를 내리면 키 페어가 뜬다. 키 페어 생성 클릭. <BR>
키 페어는 EC2 컴퓨터에 아무나 접근하면 안되니 EC2 컴퓨터에 접근할 때 사용하는 비밀번호 정도로 생각하면 된다. 

**키 페어 이름**은 어떤 EC2에 접근하기 위한 키 페어였는 지 알아볼 수 있게 지정하면 좋다.
`RSA`와 `.pem`을 선택한 후에 키 페어를 생성하면 된다.

키 페어를 생성하면 파일이 하나 다운받아질텐데, 키 페어가 유출되는 순간 다른 사람도 접근 가능해지므로 파일은 안 잃어버리게 잘 보관해야한다.
- **참고)** 실습에서는 `키 페어`를 활용해서 EC2에 접근하지 않고, 더 편한 방법으로 접근할 예정이다.

![image](https://github.com/al1kite/AWS-wiki/assets/102217402/e8f123cf-5b96-4da3-9ee1-089ae8c4f922)

### 3. EC2 세팅하기 - 보안그룹 설정

이제 네트워크 설정 부분을 볼 것. 
VPC, 서브넷, 퍼블릭IP 자동할당, 방화벽(보안 그룹) 등의 내용이 생겼다.

![image](https://github.com/al1kite/AWS-wiki/assets/102217402/00807a56-969f-4302-92c1-c2f3eb6899fa)

세팅 전 개념 먼저 잡을 것.
네트워크 설정 칸을 보면 VPC 필수라는 부분이 있고 크게는 보안그룹과 관련된 부분이 있다.
여기서 VPC 라는 개념은 AWS를 입문하는 입장에서는 크게 중요하지 않다.
VPC 개념은 AWS 가 익숙해졌을 때 학습 후 적용 추천...

보안그룹은 필수적으로 알아야 하는 개념이기에 짚고 넘어 가보자.

#### 보안그룹이란
보안 그룹(Security Group)이란 AWS 클라우드에서의 네트워크 보안을 의미한다.
우리는 하나의 컴퓨터인 EC2를 빌렸고, 보안그룹은 접근할 때 접근해도 되는 요청인지 먼저 검사해주는 역할을 한다.
보안 그룹을 먼저 거쳐서 EC2 인스턴스에 들어가야. 도착 전 들어와도 되는 트래픽인지 검사하는 기능.

인터넷에서 일부 사용자가 EC2 인스턴스에 접근(액세스)하려고 한다고 가정해보자.
위 그림과 같이 EC2 인스턴스 주위에 방화벽 역할을 할 보안 그룹(Security Group)을 만들고 보안 그룹에 규칙을 지정할 것.
보안그룹의 규칙은 크게 2가지가 존재한다.
첫번째로는 인바운드 트래픽(즉, 외부에서 EC2 인스턴스로 보내는 트래픽)에서 어떤 트래픽만 허용할 지 설정할 수 있고, 
두번째로 아웃바운드 트래픽(즉, EC2 인스턴스에서 외부로 나가는 트래픽)에서 어떤 트래픽만 허용할 지 설정할 수 있다.
![img](https://github.com/al1kite/AWS-wiki/assets/102217402/feb02d7e-f1f9-41fe-8286-de0b6d12d3a5)

이런 보안 그룹을 설정할 때는 허용할 IP 범위와 포트(port)를 설정할 수 있다.
우리는 이런 IP만 요청을 받을 거고, 이런 포트에 대해서만 요청을 받을 것이다, 나머지 포트는 우리의 EC2 인스턴스로는 못 들어가게 막을 것이라는 규칙 설정.

그럼 이제 EC2 인스턴스 생성 시 어떻게 보안그룹을 설정할지 알아볼 것. 편집을 눌러준다.
보안그룹 이름은 원하는 이름으로 수정. 설명도 더 자세하게 써도 된다.

![image](https://github.com/al1kite/AWS-wiki/assets/102217402/5a1378c7-554b-4094-8eb2-5364bef9564f)

그 밑 인바운드 보안 그룹 규칙이 나온다.
인바운드 외부에서 EC2 안쪽으로 요청이 들어오는 것에 대해 어떤 것을 허용할 건지를 정하는 규칙이라 했다.
그때 IP와 Port 를 바탕으로 설정한다 했다.

첫번째로 SSH 로 22 번 포트가 이미 설정이 되어있다. 
이게 무슨 뜻이냐면 SSH 란 쉽게 표현하자면 원격 접속하기 위한 경로이다.
우리는 EC2 에 원격 접속해 컴퓨터에 들어가서 무언가 작업을 할 것.
그러면 포트에 대해 허용이 되어 있어야만 우리는 EC2 인스턴스에 접근할 수 있다.
그래서 보면 위치 무관으로 EC1 포트가 열려있다는 건 어떤 컴퓨터의 IP에서든 EC2에 접근할 수 있게끔 만드는 규칙이다.
그래서 이걸 응용해서 내가 만약 내 집에 있는 특정 IP에 대해서만 EC2에 접근하게 만들고 싶다면, 사용자 지정에서 IP를 직접 입력하면 된다.

우리는 일단 위치 무관으로 설정.

한 가지 보안 그룹 규칙을 더 추가해줄 것. 
어떤 거에 대해 허용할 거냐면 tcp로 사용자 지정 tcp 유형을 http 로 변경할 것.
그럼 자동으로 80 번 포트로 설정된다. 왜 이걸 설정했냐면, 우리는 80번 포트로 들어오는 http 요청에 대해서는 EC2로 들어오게 만들 것이다,
왜냐면 우린 백엔드 서버를 만들 건데 백엔드 서버를 80번 포트에 띄울 예정이기 때문.
그래서 그 서버에 요청이 들어와야 응답 할 수 있으니 이렇게 80번 포트는 인바운드 규칙에서 허용할 수 있게 열어두겠다.
그리고 소스 유형을 봤을 때 위치 무관, 그러니까 모든 IP 에 대해서 다 요청을 받겠다.
왜냐면 요청을 보내는 사용자들이 불특정 다수이기 때문에 모든 IP 사용자들이 접속할 수 있어야 한다.
![image](https://github.com/al1kite/AWS-wiki/assets/102217402/b2761966-3755-4aec-b26c-268267374f44)

### 4. EC2 세팅하기 - 스토리지 구성

#### 스토리지 구성이란?

우리가 쓰는 노트북이나 데스크탑 컴퓨터는 전부 하드디스크를 갖고 있다.
하드디스크란 컴퓨터에서 파일 같은 걸 저장하는 공간인데 EC2도 하나의 컴퓨터다 보니 여러 파일을 저장할 저장공간이 필요하다.
이 저장 공간을 보고 EBS(Elastic Block Storage)라고 부른다. 
즉, EBS란 EC2 안에 부착되어 있는 일종의 하드디스크라고 생각하면 된다. 
EBS와 같은 저장 공간을 조금 더 포괄적인 용어로 스토리지(Storage) 혹은 볼륨(Volume)이라고 부른다. 

![img](https://github.com/al1kite/AWS-wiki/assets/102217402/6e29cf1e-7149-46da-8a4c-a503c09d7ebd)

스토리지의 종류를 보면 gp3 이외에도 여러가지 종류의 스토리지가 있다. 
하지만 가성비가 좋은 gp3를 선택. 용량을 30GiB를 설정한 이유는 프리 티어에서 30GiB까지 무료로 제공해주기 때문. 
이 스토리지의 크기는 추후에 늘릴 수도 있으므로 처음 설정할 때 너무 큰 고민을 할 필요는 없다.

이제 설정은 끝났다. 생성하기 버튼을 눌러준다.

![img](https://github.com/al1kite/AWS-wiki/assets/102217402/281e0411-3859-4ba5-a05e-481457f50fef)

인스턴스를 시작했다고 하니 이걸 보기 위해 EC2 대시보드로 가준다.

그 후 대시보드에서 인스턴스 실행 중에 들어간다. 
![img](https://github.com/al1kite/AWS-wiki/assets/102217402/17c5051b-a064-4779-a1b2-c5470902625a)

인스턴스가 잘 생성된 걸 확인할 수 있다.
이때, EC2 라는 컴퓨터가 켜지는데에도 시간이 소모되므로 곧바로 들어가면 running 중에 뜨지 않을 수도 있다.
기다리면 곧 실행이 되고, 서울이 아닌 다른 region을 선택해 들어가면 인스턴스가 없는 걸 확인할 수 있다.

![img](https://github.com/al1kite/AWS-wiki/assets/102217402/ae85bd0c-0b53-45d9-bd1c-56a45403d9fd)