# gcp-practice

##  Agenda

 - Google Cloud Platform
 - Virtual Machine
 - Storage
 - Containers
 - Applications
 - CI / CD
 - BigData / Machine Learning


## Cloud Computing

1. On-demand self-service
> 언제 어디서나 전문가 없이도 사용 가능하다.

2. Broad network access
> 모두가 접근 가능하다.

3. Resource pooling

4. Rapid elasticty
> 빠르게 확장할 수 있다.

5. Measured service
> 사용한 만큼 비용을 지불한다.


## Cloud

1. 자원을 한 곳에 모아두고 '관리'를 함
2. 자원을 '가상화'하고, 세분화하여 필요한 만큼 사용
3. 서버를 없애고 사업자가 '자동화'를 함

모든 회사는 데이터 회사: 데이터 관리를 잘 해야한다. - Google


## GCP Computing

> 모든 기능을 구현해놀고 사용자가 필요한 것을 사용할 수 있도록 만들어 놓은 클라우드
>> Kubernetes: 통합된 환경 안에서 사용
>> App Engine: 바로 사용할 수 있도록 자동화한 것
>> Cloud Functions(AWS에서는 Lamda): 이벤트 기반의 서비스 아키텍처를 만들 때 활용하기 좋은 솔루션


## GCP Network

> 대량의 해저 케이블을 가지고있는 장점이 있다.
>> 직접 설치했고, 전 세계 트래픽의 40%를 감당할 수 있을 정도의 네트워크 보유


## Region

> Zone: 실제로 설치해 놓은 데이터센터
>> 데이터센터를 모아놓은 지역
>
> 한국은 2020. 2. 에 region이 open된다.
>
> Zone에 데이터가 할당되어 사용
>
> 서비스가 중단될 경우를 대비하여 여러 Region을 보유
>
> 멀티 리전 간 가용성을 제공하는 서비스도 있다.


## 친환경 클라우드

> Google은 재생에너지를 사용하는 기업으로 환경에 대해 기여
>
> 가격적인 측면에서도 이점이 있다.
>> 사용한 만큼(초당 사용량) 비용 청구
>> 정액 계약에 대한 이점이 있다.
>> 불필요한 리소스에 대한 비용을 줄일 수 있다. -> 메모리 용량을 정확하게 지정할 수 있다.


## GCP APIs

1. Cloud Bigtable
> h base database
> NoSQL

2. Cloud Dataproc
> 자동화

3. TensorFlow

4. Kubernetes
> 타 클라우드 사업장에서도 관리형으로 제공

5. Google Stackdriver
> On-frame Server 확인 가능
> AWS Server 확인 가능


## GCP 사용

> 사용자에 대한 보안 강화 -> 이메일 확인을 해야한다.
>
> 조직에서 사용하기 용이함 -> 논리적인 계층 구조를 적용하여 효율적으로 제공됨
>> 폴더 안에 폴더가 들어가거나, 프로젝트가 들어감, 같이 들어갈 수 있음
>> ex) 경영지원 -> 경영지원팀 아래 부서에 접근 권한 부여(조직 관리자)
>> instance까지 권한 부여가 가능하다.


## Service Account

> 사용자가 될 수도 있는 계정
> 권한을 부여할 수도, 받을 수도 있는 계정


## Console

> 조직 내에서 통합 관리를 할 수 있다.
> 서비스를 운영하는 사람이면 간단한 기능을 모바일에서도 제공받을 수 있다.

### Cloud Shell

 - 조직 내에 할당된 리소스를 controll할 수 있다.
 - VM이 생성된다.
 - Source Repository(GCP상의 git)


## SDK

> 도커 이미지 배포
> URL로 접근하지 않아도 local로 접근할 수 있는 도구
> MongoDB: MongoDB에서 설치된 서비스가 자동으로 GCP에 만들어지기 때문에 사용이 편리하다.



# VPC Neteorking

 - 전 세계에서 가상화 클라우드로 쓰일 수도 있고, 개인적으로 사용될 수도 있다.
 - VPC 내부에 Region이 있고, Zone이 있고, Zone 내부에 Region, Subnet이 있다.
 - 서브넷은 각 Region 내부와 통신한다.
 - VPC 내부에서는 모든 통신이 가능하다.

## Compute Engine

> SSD, Disk를 원하는 사이즈로 할당받을 수 있다.
> 스냅샷 기능이 있어 쉽게 복구할 수 있다.
> CPU 사양을 높일 수 있다.(resize)
> 초당 가격, 지속 사용 할인, 정액 할인(최대 57%까지)이 있다.
> Preemptible instance: 24시간만 활동하고 꺼지는 서비스
>> 주기적으로 짧은 시간 내에 필요한 인스턴스
>> ex) 분기 평가
> Storage 접근에 따른 속도는 모두 다르다.
>> Storage는 모두 연결되어 있어 모든 자원 접근에 대한 시간이 동일하다. -> 타 지원사와 다름
> 1000의 트래픽을 다루다가 이벤트로 인해 10000의 트래픽을 다뤄야할 떄 유동적으로 지원이 가능하다.


## VPC Network

 - routing table 관리
 - 방화벽 설정
 - 피어링 설정


## Load Balancing

> 여러 지역에서 접근할 떄 가장 가까운 통신망으로 연결
> url이 들어왔을 때 어느 backend에 보내줄 지 결정


## Cloud Bigtable

> 관리형 NoSQL
> 미리 layout을 정의할 필요가 없다.
> 한 장비 위에서 돌아가는 것이 아니라 여러 장비에 분산되어 나눌 수 있다.
>> 박대아터, 대용량 트래픽이 들어왔을 때 용이하다.
>
> role-based로 접근 관리를 할 수 있다.
>
> 구글 Search 엣도 사요






