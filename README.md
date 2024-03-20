# AWS-wiki
![image](https://github.com/al1kite/AWS-wiki/assets/102217402/09cae637-42f6-479e-ac7d-cadac95d28d3)
AWS 관련 공부 및 스터디를 진행하고 정리하는 페이지 입니다.

## 상반기 스터디 - 비전공자도 이해할 수 있는 AWS 입문/실전
 <details>
    <summary>백엔드 API 서버 배포하기 (EC2)</summary>
   
    __01-1 배포(Deployment)란?
   
    __01-2 EC2란? / EC2를 왜 배울까? / 현업에서 EC2는 주로 언제 쓸까?

    __01-3 [실습] 1. 리전(Region) 선택하기
    
    __01-4 [실습] 2. EC2 셋팅하기 - 기본 설정
    
    __01-5 [실습] 3. EC2 셋팅하기 - 보안그룹 설정
    
    __01-6 [보충 강의] IP와 Port 개념
    
    __01-7 [실습] 4. EC2 셋팅하기 - 스토리지 구성
    
    __01-8 [실습] 5. EC2 접속하기
    
    __01-9 [실습] 6. 탄력적 IP 연결하기
    
    __01-10 [실습] 7. Express 서버를 EC2에 배포하기
    
    __01-11 [보충 강의] 7-2. Spring Boot 서버를 EC2에 배포하기
    
    __01-12 비용 나가지 않게 EC2 깔끔하게 종료하기
  </details>

 <details>
    <summary>도메인 연결하기 (Route53)</summary>
   
    __01-1 Route53이란? / DNS란? / 현업에서의 Route53 활용 여부
   
    __01-2 [실습] 0. Route53에 연결할 EC2 생성하기

    __01-3 [실습] 1. Route53에서 도메인 구매
    
    __01-4 [실습] 2. Route53의 도메인을 EC2에 연결하기
    
    __01-5 [보충 강의] 무료로 도메인 구매하는 방법
  </details>

 <details>
    <summary>HTTPS 연결하기 (ELB)</summary>
   
    __01-1 ELB란? / TLS, SSL과 HTTPS
   
    __01-2 ELB를 활용한 아키텍처 구성

    __01-3 [실습] 1. ELB 셋팅하기 - 기본 구성
    
    __01-4 [실습] 2. ELB 셋팅하기 - 보안그룹
    
    __01-5 [실습] 3. ELB 셋팅하기 - 리스너 및 라우팅 / 헬스 체크
    
    __01-6 [실습] 4. ELB에 도메인 연결하기
    
    __01-7 [실습] 5. HTTPS 적용을 위해 인증서 발급받기
    
    __01-8 [실습] 6. ELB에 HTTPS 설정하기
    
    __01-9 비용 나가지 않게 ELB 깔끔하게 종료하기
    
    __01-10 [보충 강의] HTTPS 연결 시 ELB vs Nginx, Certbot
    
    __01-11 [보충 강의] Nginx, Certbot을 활용해 HTTPS 연결하기
  </details>

 <details>
    <summary>데이터베이스 연결하기 (RDS)</summary>
   
    __01-1 RDS란? / RDS를 왜 사용하는걸까? / 현업에서의 RDS
   
    __01-2 RDS를 활용한 아키텍처 구성

    __01-3 [실습] 1. RDS 생성하기
    
    __01-4 [실습] 2. 보안그룹 설정하기
    
    __01-5 [실습] 3. 파라미터 그룹 추가하기
    
    __01-6 [실습] 4. RDS에 접속하기
    
    __01-7 [실습] 5. Express 서버에 RDS 연결하기
  </details>

 <details>
    <summary>파일 및 이미지 업로드 (S3)</summary>
   
    __01-1 S3란? / S3를 왜 사용하는걸까? / 현업에서 S3를 많이 사용할까?
   
    __01-2 S3를 활용한 아키텍처 구성

    __01-3 [실습] 1. S3 버킷 생성하기
    
    __01-4 [실습] 2. S3에 파일 업로드 할 수 있도록 IAM에서 액세스 키 발급받기
    
    __01-5 [정오표] 3. S3를 활용해 Express 서버에 이미지 업로드 기능 구현하기
    
    __01-6 [실습] 3. S3를 활용해 Express 서버에 이미지 업로드 기능 구현하기
  </details>

   <details>
    <summary>웹 페이지 배포하기 (S3, Cloudfront)</summary>
   
    __01-1 웹 서비스를 배포할 때 사용하는 S3, CloudFront
   
    __01-2 S3, CloudFront를 활용한 아키텍처 구성

    __01-3 [실습] 1. S3 버킷 셋팅하기
    
    __01-4 [실습] 2. S3에 업로드하기 / 웹 호스팅 설정하기
    
    __01-5 [보충 자료] React 프로젝트를 S3에 업로드하는 방법
    
    __01-6 [실습] 3. CloudFront 생성하기

    __01-7 [실습] 4. 도메인 연결하기, HTTPS 적용하기
  </details>

  ## 실리콘밸리 엔지니어와 함께하는 아마존 웹서비스(Core)편

   <details>
    <summary>Identity and Access Management(IAM) 아이덴티티와 액세스 매니지먼트</summary>
   
    __01-1 IAM 소개
   
    __01-2 IAM MFA(멀티 팩터 인증) 알아보기

    __01-3 AWS CLI(Command Line Interfact) 알아보기
    
    __01-4 AWS Cloud Shell 알아보기
    
    __01-5 IAM Role 알아보기
    
    __01-6 IAM Best Practice(가장 좋은 방법) 알아보기
  </details>
  
  <details>
    <summary>Elastic Compute Cloud(EC2) Instance</summary>
   
    __01-1 EC2 인스턴스 소개
   
    __01-2 EC2 인스턴스 만들어보기

    __01-3 EC2 Security Group(보안 그룹) 알아보기
    
    __01-4 How SSH works(SSH는 어떤 식으로 작동하는지) 알아보기
    
    __01-5 EC2 Price Option(가격 옵션) 알아보기
  </details>

  <details>
    <summary>EC2 Advanced</summary>
   
    __01-1 EC2 Spot Instance에 대해 알아보기
   
    __01-2 Public and Private IPs에 대해 알아보기

    __01-3 EC2 Placement Group(전략적인 배치 방법) 알아보기
    
    __01-4 Elastic Network Interface(ENI) 알아보기
    
    __01-5 EC2 Instance State 인스턴스 상태에 대해 알아보기
  </details>

  <details>
    <summary>Elastic Block Store(EBS)</summary>
   
    __01-1 Elastic Block Store(EBS)에 대해 알아보기
   
    __01-2 EBS Snapshot(스냅샷) 알아보기

    __01-3 Amazon Machine Image(AMI) 아마존 머신 이미지 알아보기
    
    __01-4 EC2 Instance Store(임시 저장 장치) 알아보기
    
    __01-5 EBS Volume Type(볼륨 타입) 알아보기

    __01-6 Scalability vs. High Availability(확장성과 높은 가용성)의 차이점을 알아보기
  </details>

  <details>
    <summary>Elastic Load Balancer(ELB)</summary>
   
    __01-1 Elastic Load Balancer(ELB) 소개
   
    __01-2 Elastic Load Balancer(ELB) 만들어 보기

    __01-3 ELB Sticky Session(고정 세션) 알아보기
    
    __01-4 ELB Cross Zone Load Balancer(교차 영역 분배) 알아보기
    
    __01-5 SSL and TLS(SSL / TLS 인증) 알아보기

    __01-6 ELB Connection Draining(연결 배출) 알아보기

    __01-7 Auto Scaling Group(ASG) 알아보기
  </details>

  <details>
    <summary>Relational Database Service(RDS) - 데이타 베이스</summary>
   
    __01-1 Relational Database Service(RDS) 관계형 데이타 베이스 알아보기
   
    __01-2 RDS Read Replica(읽기 전용 복제) 알아보기

    __01-3 RDS 만들어 보기
  </details>
  
  <details>
    <summary>EC2 Advanced</summary>
   
    __01-1 RDS Aurora DB - AWS 오로라 데이타 베이스에 대한 모든 것 알아보기
   
    __01-2 RDS 데이타 베이스 백업과 복원 그리고 클론

    __01-3 RDS Security - 보안 알아보기
    
    __01-4 RDS Proxy - 프록시(대리) 서버 알아보기
  </details>

  <details>
    <summary>ElastiCache - 빠른 데이타 요청을 위한 캐시 서비스</summary>
   
    __01-1 ElastiCache에 대한 모든 것 알아보기
  </details>

  <details>
    <summary>Route53 - DNS 관리</summary>
   
    __01-1 DNS(Domain Name Service) -도메인 네임 서비스는 어떤 식으로 작동하는지 알아보기
   
    __01-2 Route53 서비스에 대해 알아보기

    __01-3 DNS 설정해서 EC2에 연결해보기
    
    __01-4 TTL(Time To Live)에 대해 알아보기
    
    __01-5 CNAME과 Alias Record의 차이점에 대해 알아보기
    
    __01-6 Route53 Routing Policy(라우팅 정책)에 대해 알아보기

    __01-6 아마존이 아닌 다른 도메인 등록 업체에서 산 도메인을 Route53 연결 방법에 대해 알아보기
  </details>

  <details>
    <summary>Simple Storage Service(S3)</summary>
   
    __01-1 S3에 대한 기본적인 이해
   
    __01-2 Security 측면에 대해 알아보기

    __01-3 Static Webiste(정적인 웹사이트) 만들어 보기
    
    __01-4 Versioning(버전화) 활성화하기
  </details>

  <details>
    <summary>Simple Storage Service(S3) Advanced</summary>
   
    __01-1 Replication(복제)하는 방법 알아보기
   
    __01-2 S3 Storage Classes(ft. Durability & Availability) 알아보기

    __01-3 Life Cycle Policy(라이프 사이클 정책)에 대해 알아보기
    
    __01-4 Event Notification(이벤트 알리미)에 대해 알아보기

    __01-4 S3 Performance Best Practice에 대해 알아보기

    __01-5 S3 Select(S3에서 SQL쿼리) 써보기

    __01-6 S3 Batch Operations 사용해 보기
  </details>

  <details>
    <summary>CloudFront(AWS CDN) & Global Accelerator</summary>
   
    __01-1 CloudFront 알아보기
   
    __01-2 CloudFront에서 ALB나 EC2를 Origin 사용해 보기

    __01-3 Geo Restriction(지리적 제한)에 대해 알아보기
    
    __01-4 CloudFront Price Classes(가격 클래스)에 대해 알아보기

    __01-4 CloudFront Cache Invalidation(캐시 강제 업데이트)에 대해 배워보기

    __01-5 Global Accelerator(Network optmizer)에 대해서 알아보기
  </details>
