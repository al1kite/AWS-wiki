## 인스턴스 접속

컴퓨터를 하나 빌려왔으니 접속할 수 있어야 한다.

이때 퍼블릭 IPv4 주소는 EC2 인스턴스가 생성되면서 부여받은 IP 주소이다. EC2 인스턴스에 접근하려면 이 IP 주소로 접근하면 된다.

<img width="216" src="https://github.com/al1kite/AWS-wiki/assets/102217402/61dc38b2-7059-4ac0-a34c-f3620b41ab0d">

참고로 EC2 인스턴스를 중지, 재부팅, 종료도 할 수 있다.
중지는 컴퓨터를 잠시 꺼놓는 걸 의미하지만 종료는 컴퓨터를 아예 삭제시킨다는 걸 의미한다. 
EC2 인스턴스를 한 번 종료하면 도중에 취소할 수 없으니 조심해야 한다.

인스턴스 요약 하단에 연결을 클릭해준다.

<img width="840" src="https://github.com/al1kite/AWS-wiki/assets/102217402/b37350c6-4cea-4228-b22c-fc818a79519d">
여러 연결 방식이 있지만 우리는 EC2 인스턴스 연결 방식을 사용할 생각.
이 연결 방식은 AWS 에서 로그인 해서 홈페이지 자체에서 빌린 컴퓨터에 원격 접속하는 방식이다.
사용하는 이름은 기본 값인 ubuntu 로 사용할 생각.
내 경우 기본 사용자 이름으로 ec2-user 로 나오는데 인스턴스 세팅이 Ubuntu 가 아닌 Amazon Linux 로 됐다.
Ubuntu 로 설정해줬던 것 같은데 왜지 🤦

연결하기 클릭.

![image](https://github.com/al1kite/AWS-wiki/assets/102217402/635861b4-d61f-4deb-b1a0-c520f872e294)

드디어 EC2 인스턴스 생성한 컴퓨터에 접속 완료.
이게 우리가 선택한 Ubuntu 라는 OS 기반으로 깔려있는 컴퓨터이고 우리가 이 컴퓨터에 원격 접속한 상태.

## 탄력적 IP 연결

EC2 인스턴스를 생성하면 IP를 할당받지만 이는 임시적인 IP이다. 
EC2 인스턴스를 잠깐 중지시켰다가 다시 실행시켜보면 IP가 바뀌어있다. 
EC2 인스턴스를 중지시켰다가 다시 실행시킬 때마다 IP가 바뀌면 굉장히 불편하다. 
그래서 중지시켰다가 다시 실행시켜도 바뀌지 않는 고정 IP를 할당받아야 한다.
그게 바로 탄력적 IP.

왜 임시 IP를 발급했을까? 
처음부터 고정 IP를 발급해주면 좋았을텐데?

IP 개수가 전세계적으로 한계가 오고 있다.
IP의 규칙이 있는데 그게 지금 조금씩 부족해지고 있다.
IP를 아껴써야겠다는 생각에 인스턴스 안쓰고 있으면 자동으로 반납해서 다른 컴퓨터에게 양보하는 거.
그래서 탄력적 IP라는 개념이 나오게 된 것.

<img width="1047" src="https://github.com/al1kite/AWS-wiki/assets/102217402/f73adc88-d225-4631-bcdc-f4565223b9a5">

탄력적 IP에 들어가서 탄력적 IP 주소 할당을 클릭한다.
<img width="840" src="https://github.com/al1kite/AWS-wiki/assets/102217402/f4b7019c-14e2-4e68-a45f-4b45ca7fe1d4">

여러가지 세팅이 나오지만 기본값 사용 예정, 할당을 눌러준다.

<img width="798" src="https://github.com/al1kite/AWS-wiki/assets/102217402/30ea9e92-941a-4a12-8f8b-98df80f1089b">

그럼 탄력적 IP를 하나 발급받게 된다. 이름 변경 가능.

연결할 때는 작업 클릭 후 탄력적 IP 주소 연결에 들어간다.
인스턴스 선택 누르면 아까 우리가 만들었던 EC2 인스턴스가 있다.
그걸 클릭한 후 연결을 눌러주면 된다.

<img width="834" src="https://github.com/al1kite/AWS-wiki/assets/102217402/1fc09df0-e5d5-455b-9237-2299d4adad6e">

인스턴스에 들어가면 할당받은 IP 주소로 변경된 걸 확인할 수 있다.
이제 IP가 고정이 됐다.

## Express 서버를 EC2에 배포하기

일단 Ubuntu 원격 접속에 다시 들어간다.
우리는 Express 서버를 실행 시킬 거기 때문에 Express 서버를 구동하려면 제일 먼저 Node.js 를 먼저 설치해준다.

먼저 권한을 root 권한으로 변경한다.
![img](https://github.com/al1kite/AWS-wiki/assets/102217402/51858e6d-4966-4217-89fb-23932d19bec4)

나는 linux 로 설정이 됐기 때문에 sudo apt-get 이 아닌 sudo yum 명령어로 작성해줘야 한다.

<img width="670" src="https://github.com/al1kite/AWS-wiki/assets/102217402/210b09b2-0775-495e-afbc-9bfa6df499f1">
<img width="945" src="https://github.com/al1kite/AWS-wiki/assets/102217402/a479fb57-6037-4de4-b38f-e04338c00abc">

일단 git 부터 설치해준다.
<img width="562" src="https://github.com/al1kite/AWS-wiki/assets/102217402/73a7575d-63d6-482a-8e4a-601fac22ba35">
그 후 강의에서 미리 만들어진 Express 프로젝트를 clone 한다.
<img width="830" src="https://github.com/al1kite/AWS-wiki/assets/102217402/95632524-e707-4166-a0d2-58b9930806c5">

https://github.com/JSCODE-EDU/ec2-express-sample

<img width="495" src="https://github.com/al1kite/AWS-wiki/assets/102217402/eae48873-f004-4fb1-a4d1-c65ade2a9c1a">
npm i 로 라이브러리도 설치해준다. 

clone 된 프로젝트의 github 에 들어가서 clone 된 프로젝트가 app.js 파일을 열어 어떤 프로젝트인지 확인하면 
80번 포트에서 Express 서버를 실행 시킬 것이고, get 요청을 보냈을 때 이렇게 응답할 건데 여기서 process.env 을 실행시켰다.
이때 env 파일을 github 에 안올리게끔 gitignore에 추가해놓았다.
그럼 .env 와 같은 민감한 파일들은 어떻게 파일로 작성할까?
여러가지 방법이 있는데 인스턴스에서 .env 파일을 직접 만들어줄 수 있다.

<img width="365" src="https://github.com/al1kite/AWS-wiki/assets/102217402/6a066c30-0044-4bc9-a9be-af9d526f6779">
<img width="951" src="https://github.com/al1kite/AWS-wiki/assets/102217402/06364de9-b914-4694-974e-8293bdc0257c">
다음과 같이 민감한 정보를 .env 파일을 생성 및 저장해 직접 만들어주었다.

<img width="613" src="https://github.com/al1kite/AWS-wiki/assets/102217402/0963629e-58f6-4939-a084-c0f534d29211">
.env 파일이 생성된 걸 확인할 수 있다.

그 후 우리가 서버를 실행시킬 때 PM2를 활용해 Express 서버를 실행시킬 것이다.
따라서 PM2 의 설치가 필요하다.

<img width="441" src="https://github.com/al1kite/AWS-wiki/assets/102217402/ae728e94-0459-4414-930d-8ea37f59f758">

잘못된 디렉토리 위치에서 명령어를 입력해서 script 가 없다는 에러가 떴었다.
clone 받은 프로젝트 디렉토리에 들어가 app.js 를 기반으로 실행시킨 후 ip:80번 포트로 들어가면 서버가 실행 중인 걸 확인할 수 있다.
CI/CD 가 붙기 전까지는 현업에서도 이렇게 짜기도...
<img width="752" src="https://github.com/al1kite/AWS-wiki/assets/102217402/bd85dfab-cee9-484e-ab7f-3e14b4400acd">

## Spring boot 서버를 EC2 에 배포하기

제일 먼저 우리가 EC2 인스턴스를 생성 했을 때 어떤 걸 해야 하냐면 
스프링 부트를 실행하기 위한 JDK를 설치해야한다.

다운로드 받을 수 있는 java 버전을 확인한 뒤 실습에서와 같이 17 버전으로 다운로드 받았다.

<img width="1033" src="https://github.com/al1kite/AWS-wiki/assets/102217402/f1465c23-feda-416f-b249-f29696ffa59f">
<img width="913" src="https://github.com/al1kite/AWS-wiki/assets/102217402/5ef9b5af-58b5-4636-930d-58963c6b5bc1">

잘 설치됐는지 버전 확인.

<img width="818" src="https://github.com/al1kite/AWS-wiki/assets/102217402/2f190695-e87e-4a16-8e30-cfd89f65fbc0">

실습 Spring Boot 프로젝트를 clone 받고 해당 디렉토리로 이동해준다.

<img width="1034" src="https://github.com/al1kite/AWS-wiki/assets/102217402/10d040f2-bfb0-4a9a-8f69-112ca7a238e8">

동일하게 application.yml 파일 직접 만들어준 후 서버를 실행시켜준다.

```
$ ./gradlew clean build # 기존 빌드된 파일을 삭제하고 새롭게 JAR로 빌드 (gradlew 경로로 들어가야만 정상적 실행)
$ cd ~/ec2-spring-boot-sample/build/libs
$ sudo java -jar ec2-spring-boot-sample-0.0.1-SNAPSHOT.jar
```

참고) 백그라운드에서 Spring Boot 실행시키기


```
$ sudo nohup java -jar ec2-spring-boot-sample-0.0.1-SNAPSHOT.jar &
```

이제 실습이 종료됐으니 EC2 인스턴스를 종료하고 정상적으로 잘 종료되었다면 탄력적 IP를 릴리스해준다.