# AWS 개념 정리

## 1. 클라우드 서비스 모델

### IaaS (Infrastructure as a Service)
- 가상 서버, 네트워크, 스토리지 같은 인프라 자원을 제공
- 예: EC2, EBS
- 사용자가 서버 설치, 보안 설정, 환경 구성까지 모두 직접 수행

### PaaS (Platform as a Service)
- 애플리케이션을 개발/실행할 수 있는 플랫폼을 제공
- 예: Elastic Beanstalk, AWS RDS
- 사용자는 코드만 배포하고, 인프라는 AWS가 관리

### FaaS (Function as a Service)
- 이벤트 기반으로 함수 단위 코드 실행
- 예: AWS Lambda
- 서버 관리 불필요, 요청 시에만 동작

### CaaS (Container as a Service)
- 컨테이너 기반 애플리케이션 실행 및 관리
- 예: AWS Fargate, Amazon ECS
- 사용자는 컨테이너만 준비하고, AWS가 실행 환경을 제공

### SaaS (Software as a Service)
- 소프트웨어를 웹 기반으로 제공, 설치 불필요
- 예: WorkMail, AWS Chime, Gmail

---

## 2. 네트워크 기본 용어

- **라우터**: 서로 다른 네트워크 간 데이터 전달
- **스위치**: 같은 네트워크 내 장치 간 데이터 전송
- **방화벽**: 외부와 내부 트래픽 제어
- **IP 주소**: 고유 식별자 (IPv4/IPv6)
- **도메인**: 사람이 읽기 쉬운 주소 (예: google.com)
- **CIDR**: 네트워크 범위 표기 (예: 192.168.0.0/24)
- **포트**: 하나의 IP에서 여러 서비스 식별용 번호
- **주요 포트 번호**:
  - 22: SSH
  - 80: HTTP
  - 443: HTTPS
  - 3306: MySQL
  - 5432: PostgreSQL
  - 25: SMTP
  - 53: DNS
  - 21: FTP
- **프로토콜**: 통신 규약 (TCP, UDP, HTTP 등)

---

## 3. TCP/IP & HTTP 흐름 요약

1. 사용자가 도메인 입력
2. DNS 조회 후 IP 획득
3. TCP 전송, 패킷화
4. IP 경로 설정
5. 물리적 통신 진행
6. 패킷 조립 및 HTTP 요청 처리
7. 서버 응답을 역순으로 전송

---

## 4. 클라우드 핵심 기술

- **가상화**:
  - **호스트 기반**: OS 위에 VM 설치 (예: VirtualBox)
  - **하이퍼바이저 기반**: OS 없이 VM 직접 실행 (예: KVM, Xen)
  - **컨테이너 기반**: OS 공유, 격리된 환경 제공 (예: Docker)
- **분산 처리**: 여러 서버로 작업 분산 (예: Hadoop)
- **서버리스**: 코드만 배포, 서버 관리 X (예: Lambda)
- **로드 밸런싱**: 트래픽 분산 (예: ELB)
- **스케일 업/아웃, 오토스케일링**
- **데브옵스 (DevOps)**: CI/CD로 개발-운영 통합

---

## 5. AWS 인프라 구성 요소

- **리전**: 지리적 데이터 센터 그룹 (예: ap-northeast-2)
- **AZ (Availability Zone)**: 하나의 리전에 포함된 데이터 센터
- **에지 로케이션**: 전 세계 캐시 서버 위치 (CloudFront 사용)

---

## 6. 컴퓨팅 서비스

- **EC2**: 가상 서버
- **Lambda**: 서버리스 함수 실행
- **ECS**: 컨테이너 관리 서비스
- **EKS**: Kubernetes 클러스터 관리
- **Fargate**: 컨테이너 서버리스 실행
- **Lightsail**: 초보자용 웹 호스팅 패키지
- **Elastic Beanstalk**: 완전 관리형 PaaS

---

## 7. 스토리지 서비스

- **S3**: 객체 스토리지
- **S3 Glacier**: 장기 보관용 콜드 스토리지
- **EBS**: EC2 전용 블록 스토리지
- **EFS**: 공유 파일 시스템
- **Storage Gateway**: 온프레미스 ↔ AWS 연동

---

## 8. 데이터베이스 서비스

- **RDS**: 관리형 관계형 DB
- **Aurora**: 고성능 관계형 DB
- **DynamoDB**: 서버리스 NoSQL DB
- **Redshift**: 데이터 웨어하우스
- **DocumentDB**: 문서 기반 DB (MongoDB 호환)

---

## 9. 네트워크 서비스

- **VPC**: 가상 네트워크
- **Route 53**: DNS 및 트래픽 라우팅
- **CloudFront**: CDN
- **API Gateway**: API 관리 서비스
- **Direct Connect**: 전용선 연결
- **NAT Gateway**: 프라이빗 서브넷 외부 접근용
- **Internet Gateway**: 퍼블릭 서브넷 인터넷 연결
- **Security Group**: 인스턴스 방화벽
- **NACL**: 서브넷 단위 방화벽

---

## 10. 인공지능 서비스

- **Polly**: TTS (음성 변환)
- **Lex**: 챗봇 (음성 인식)
- **Rekognition**: 이미지/영상 분석
- **Comprehend**: 자연어 처리
- **Translate**: 기계 번역
- **Transcribe**: 음성 → 텍스트 변환

---

## 11. 데이터 분석 서비스

- **Athena**: S3 데이터 SQL 분석
- **Glue**: ETL 서비스
- **Kinesis**: 실시간 데이터 스트리밍
- **EMR**: 대용량 분산 분석 (Hadoop/Spark)
- **QuickSight**: 시각화 및 대시보드 도구

---

## 12. 개발자 도구

- **CodeCommit**: Git 기반 코드 저장소
- **CodeBuild**: 빌드 및 테스트 자동화
- **CodeDeploy**: 자동 배포
- **CodePipeline**: CI/CD 파이프라인
- **Cloud9**: 웹 IDE
- **X-Ray**: 분산 애플리케이션 성능 분석
