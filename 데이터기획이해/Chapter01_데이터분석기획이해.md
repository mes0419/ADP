## 데이터 분석 기획의 이해
### Chapter 01. 분석 기획 방향성 도출
* <b>분석 기획</b>이란, 분석을 수행하기에 앞서 분석을 수행할 과제의 정의 및 의도했던 결과를 도출할 수 있도록 이를 적절하게 관리할 수 있는 방안을 사전에 계획하는 일련의 작업
* 어떤 목표(What)를 달성하기 위하여 (Why)어떤 데이터 어떠한 방식으로(How) 수행할 것인지?

#### 1. 분석 기획의 특징
* IT 및 분석 기법에 치우치는 경향을 조심
* 분석을 기획한다는 것은, 해당 문제 영역에 대한 전문성 역량 및 수학/통계학적 지식을 활용한 분석 역량과 분석의 도구인 데이터 및 프로그래밍 기술 역량에 대한 균형잡힌 시각을 가지고 방향성 및 계획을 수립해야 한다는 것
* 분석의 대상, 분석의 방법에 따라서 4가지로 나뉨
> |  분석의 방법(How) \ 분석의 대상(What) | |  |
> |---|:---:|:---:|
> |                                     | known | un-known
>  | known | optimization| Insight|
>  | un-known| Solution| Discovery|
* 분석 주제 기법 특성상 이러한 4가지 유형을 넘나들면서 과제를 수행 함
* 목표 시점 별 접근 방식
  * 당면한 분석 주제의 해결(과제 단위)
    * Speed & Test
    * Quick & Win
    * Problem Solving
  * 지속적인 분석 문화 내재화(마스터 플랜 단위)
    * Accuracy & Deploy
    * Long Term View
    * Problem Definition
* 분석가는 분석 기술, IT 프로그래밍, 분석 주제에 대한 도메인 전문성에 추가하여 PM 역량,  리더십 역량이 필요

#### 분석 기획 시 고려사항
* 가용한 데이터, 적절한 유스케이스, 분석과제를 위한 장애 요소를 고려 해야 함
##### 가용한 데이터 고려
* 정형 데이터(RDB), 비정형 데이터(e-Mail, 보고서, 소셜 데이터 등), 반정형 데이터(센서 데이터, 버신 데이터)의 존재 유무 및 유형을 파악하는 것이 중요
##### 적절한 유스케이스 고려
* 기존에 잘 구현되어 있는 유사 분석 시나리오 또는 솔루션이 있다면 이를 최대한 활용하는 것이 중요
##### 분석 과제를 위한 장애 요소를 위한 사전 계획 수립
* 분석가만 이해할 수 있는 형태의 결과가 아닌 사용자가 쉽게 이해하고 활용할 수 있도록 방안 수립
* 실제 환경에서 잘 돌아가는 지 확인 필요
* 일회성 분석으로 그치지 않고 지속적인 변화 관리(Change Management)가 필요

### Chapter02. 분석 방법론
* 고정 관념, 편향된 생각, 프래이밍 효과 등은 합리적 의사결정을 가로막는 장애 요소
* 데이터 기반 의사결정을 위해서는 기업 문화의 변화와  업무 프로세스 개선이 필요하고, 이를 촉진시키는 도구로서 데이터 분석을 활용할 수 있음
* 데이터 분석을 기업 내 효과적으로 적용토록 위해선 체계화된 절차와 방법이 정리된 데이터 분석 방법론이 필수적
* 방법론은 상세한 절차, 방법, 도구와 기법, 탬플릿과 산출물로 구성되어 어느 정도의 지식만 있으면 활용 가능 해야함
* 일반적인 방법론의 생성 과정
  * 암묵지 --> ( 형식화 ) --> 형식지 ( 체계화 ) --> 방법론 --> (내재화) --> 암목지
  * 선순환적인 과정이 진행되면서 조직의 방법론이 완성 됨

####  방법론 개요
* 폭포수 모델(Waterfall Model)
  * 단계를 순차적으로 가져 감
  * 이전 단계가 완료되어야 다음 단계로 진행 가능
  * Top-Down 으로 진행되지만,  문제 및 개선사항이 발견되면 feedback과정이 수행
* 나선형 모델(Spiral Model)
  * 반복을 통하여 점증적으로 개발
  * 처음 하는 프로젝트에 용이
  * 반복에 대한 관리 체계를 효과적으로 갖추지 못 할 경우 복잡도가 상승하여 프로젝트 진행이 어려움
* 계층적 프로세스 모델(일반적인  방법론)
  * 최상위 계층은 단계(Phase)로서 프로세스 그룹을 통해 완료된 산출물이 생성되어야 함
  * 각 단계는 기준선(baseLine)으로 설정되어 관리, 버전관리 등을 통해 통제가 이루어져야 함
  * 각 단계는 여러 개의 Task로 구성되며, Task는 단계를 구성하는 단위 활동으로써 품질검토의 항목이 될 수 있음
  * 마지막 계층은 Step으로, WBS(Work Breakdown Structure)의 워크패키지에 해당되고 입력자료, 처리 및 도구, 출력자료로 구성된 단위 프로세스.

#### 2. KDD 분석 방법론
 * KDD(Knowledge Discovery in DataBase)
 * Fayyad가 체계적으로 정리한 데이터 마이닝 프로세스
 * DB에 의미 있는 지식을 탐색
 * 9개의 프로세스를 제시
 * 도메인 이해 -> 데이터셋 선택 -> 노이즈, 이상값 제거 -> 변수 찾고 데이터 차원 축소 -> 데이터 마이닝 기법 선택 -> 데이터 마이닝 알고리즘 선택 -> 데이터 마이닝 시행 -> 결과 해석 -> 지식 활용

#### 3. CRISP-DM 분석 방법론
* 4개의 프로세스 모델로써 4개 레벨로 구성
* 최상위 레벨은 여러 phase로 구성되고, 각 단계는 generic task를 포함
* generic task는 단일 프로세스를 완전하게 수행하는 단위
* 세 번째 레벨은 Spcecialized Task로 일반화 테스크를 구체적으로 수행하는 단계
ex) 데이터 정제의 일반화 테스크는 범주형 데이터 정제, 연속형 데이터 정제 등..
* 마지막 레벨인 프로세스 실행은 데이터 마이닝을 위한 구체적인 실행을 포함
* 총 6단계로 되어 있으며,  단계 간 피드백을 통하여 단계별 완성도를 높이게 되어 있음
  * 업무 이해(업무 파악, 상황 파악, 데이터 마이닝 목표 설정, 프로젝트 계획 수립)
  * 데이터 이해(초기 데이터 수집, 데이터 기술 분석, 데이터 탐색, 데이터 품질 확인)
  * 데이터 준비(분석용 데이터셋 선택, 정제, 분석용 데이터셋 편성, 데이터 통합, 데이터 포맷팅)
  * 모델링(모델링 기법 선택, 모델 테스트 계획 설계, 모델 작성, 모델 평가)
  * 평가(분석결과 평가, 모델링 과정 평가, 모델 적용성 평가)
  * 전개(전개 계획 수립, 모니터링과 유지보수 계획 수립, 프로젝트 종료보고서 작성, 리뷰)

#### 4. 빅데이터 분석 방법론
* 빅데이터를 분석하기 위한 방법론은 계층적 프로세스 모델.
* 분석 기획(Planning)
  * 빅데이터 분석 프로젝트는 대용량의 정형, 비정형 데이터를 활용해야 하고, 분석 및 운영을 위한 인프라 구축을 병행하거나 legacy system과의 많은 인터페이스를 동반 하는 등, 위험 요소가 많음
  * 사전에 이러한 위험 요소를 차단 할 필요가 있음
* 데이터 준비(Preparing)
  * 전사 차원의 데이터 스토어 준비
  * 작업의 효율성을 위하여 필요시 ETL 등의 다양한 도구 사용
  * 품질통제와 품질보증 프로세스도 수행
* 데이터 분석(Analyzing)
  * 데이터 준비가 충분치 않을 경우 데이터 준비 단계 반복
* 시스템 구현(Developing)
  * 소프트웨어 개발 생명주기인 SDLC와 기업내 개발을 위하여 사용하고 있는 방법론을 커스터마이징하여 적용 할 수 있음
* 평가 및 전개(Deploying)


#### 5. 분석 계획(Planning)
##### 비즈니스 이해 및 범위 설정
* 비즈니스 이해
  * 입력 자료: 업무 매뉴얼, 업무전문가의 지식, 빅데이터 분석 대상 도메인 관련 자료
  * 프로세스 및 도구 : 자료 수집 및 비즈니스 이해
  * 출력자료 : 비즈니스 이해 및 도메인 문제점
* 프로젝트 범위 설정
  * 입력자료 : 중장기 계획서, 빅데이터 분석 프로젝트 지시서, 비즈니스 이해 및 도메인 문제점
  * 프로세스 및 도구 : 자료 수집 및 비즈니스 이해, 프로젝트 범위 정의서 작성 절차
  * 출력자료 :  프로젝트 범위 정의서(Statement of Work, SOW)

 ##### 프로젝트 정의 및 계획 수립
 모델의 운영 이미지를 설계하고, 평가 기준 설정
 프로젝트의 WBS 생성 및 프로젝트 수행 계획 작성
 * 데이터 분석 프로젝트 정의
   * 입력자료 : 프로젝트 범위 정의서, 분석 프로젝트 지시서
   *  프로세스 및 도구 : 프로젝트 목표 구체화, 모델 운영 이미지 설계
   * 출력자료 : 프로젝트 정의서, 모델 운영 이미지 설계서, 모델 평가 기준

* 프로젝트 수행 계획 수립
  * 입력자료: 프로젝트 정의서, 모델 운영 이미지 설계서, 모델 평가 기준
  * 프로세스 및 도구: 프로젝트 수행 계획 작성, WBS 작성, 일정계획 수립 도구
  * 출력자료:  프로젝트 수행 계획서, WBS

##### 프로젝트 위험 계획 수립
분석 프로젝트 수행시 발생 가능한 위험 발굴
* 데이터 분석 위험 식별
  * 입력자료: 프로젝트 정의서, 선행 프로젝트 산출물 및 정리자료
  * 프로세스 및 도구: 위험 식별 절차, 위험 영향도 및 발생가능성 분석, 위험 우선순위 판단
  * 출력자료: 식별된 위험 목록
* 위험 대응 계획 수립
위험에 대한 대응은 회피(Avoid), 전이(Transfer), 완화(Mitigate), 수용(Accept)로 구분
  * 입력자료: 식별된 위험 목록, 프로젝트 정의서, 프로젝트 수행 계획서
  * 프로세스 및 도구: 위험 정량적 분석, 정성적 분석
  * 출력자료:  위험관리 계획서

#### 6. 데이터 준비
##### 필요 데이터 정의
전사 차원에서 필요 데이터를 정의하는 것이 중요  
정형, 비정형, 반정형 등의 모든 내,외부 데이터를 포함  
데이터의 속성, 데이터 오너, 데이터 관련 시스템 담당자 등을 포함하는 데이터 정의서 작성  
데이터 정의서를 이용하여 구체적인 데이터 획득 방안을 상세하게 수립  
* 데이터 정의
  * 입력자료: 프로젝트 수행 계획서, 시스템 설계서, ERD, 메타데이터 정의서, 문서 자료
  * 프로세스 및 도구: 내,외부 데이터 정의, 정형, 비정형, 반정형 데이터 정의
  * 출력자료:  데이터 정의서
* 데이터 획득 방안 수립
  * 입력자료: 데이터 정의서, 시스템 설계서, ERD, 메타데이터 정의서, 데이터 구입
  * 프로세스 및 도구: 데이터 획득 방안 수립
  * 출력자료: 데이터 획득 계획서

##### 데이터 스토어 설계
데이터 획득 방안 수립 후 데이터 저장을 위한 데이터 스토어 설계
정형, 비정형, 반정형 데이터가 모두 저장될 수 있게 설계
* 정형 데이터 스토어 설계
  * 입력자료: 데이터 정의서, 데이터 획득 계획서
  * 프로세스 및 도구: DB 논리 설계, DB 물리 설계, 데이터 매핑
  * 출력자료: 정형 데이터 스토어 설계서, 데이터 매핑 정의서
* 비정형 데이터 스토어 설계
  * 하둡과 NoSQL 등을 이용
  * 입력자료: 데이터 정의서, 데이터 획득 계획서
  * 프로세스 및 도구: 반,비정형 논리 설계, 반,비정형 물리 설계
  * 출력자료: 비정형 데이터 스토어 설계서, 데이터 매핑 정의서

##### 데이터 수집 및 정합성 점검
구축된 데이터 스토어에 크롤링, RT, NRT 처리, 배치 처리 등으로 데이터 수집  
DB 연동, API를 이용한 개발, ETL 도구의 활용 등 다양한 방법 이용하여 데이터 수집 프로세스 진행  
저장된 데이터는 품질 확보를 위한 데이터 정합성 검증 실시  
데이터 거버넌스에 근거하여 메타 데이터 및 데이터 사전이 작성되고 있는지 확인  

* 데이터 수집 및 저장
  * 입력자료: 데이터 정의서, 데이터 획득 계획서, 데이터 스토어 설계서
  * 프로세스 및 도구:  데이터 크롤링 도구, ETL 도구, 데이터 수집 스크립트
  * 출력자료:  수집된 분석용 데이터

* 데이터 정합성 점검
품질 점검을 통한 데이터 정합성 확보, 품질개선 보완작업
  * 입력자료: 수집된 분석용 데이터
  * 프로세스 및 도구: 데이터 품질 확인, 데이터 정합성 점검 리스트
  * 출력자료: 데이터 정합성 점검 보고서

#### 7. 데이터 분석(Analyzing)
##### 분석용 데이터 준비
데이터셋 준비를 위하여 프로젝트 목표, 도메인 이해, 비즈니스 룰 확인  
전사 차원 데이터 스토어에서 ETL 도구를 이용해서 추출  
* 비즈니스 룰 확인
  * 입력자료: 데이터 정의서, 데이터 스토어
  * 프로세스 및 도구: 프로젝트 목표 확인,  비즈니스 룰 확인
  * 출력자료: 비즈니스 룰, 분석에 필요한 데이터 범위
* 분석용 데이터 셋 준비
  * 입력자료: 데이터 정의서, 데이터 스토어
  * 프로세스 및 도구: 데이터 선정, 데이터 변환, ETL 도구
  * 출력자료: 분석용 데이터셋

#### 텍스트 분석
##### 텍스트 데이터 확인 및 추출
  * 입력자료: 비정형 데이터 스토어
  * 프로세스 및 도구: 분석용 텍스트 데이터 확인, 텍스트 데이터 추출
  * 출력자료: 분석용 텍스트 데이터

##### 텍스트 데이터 분석
  * 입력자료: 분석용 텍스트 데이터, 용어사전
  * 프로세스 및 도구: 분류체계 설계, 형태소 분석, 키워드 도출, 토픽 분석, 감성 분석, 오피니언 분석, 네트워크 분석
  * 출력자료: 텍스트 분석 보고서

#### 탐색적 분석
##### 탐색적 데이터 분석
  * 입력자료: 분석용 데이터 셋
  * 프로세스 및 도구: EDA 도구, 통계 분석, 변수간 연관성 분석, 데이터 분포 확인
  * 출력자료: 데이터 탐색 보고서

##### 데이터 시각화
  * 입력자료: 분석용 데이터 셋
  * 프로세스 및 도구: 시각화 도구 및 패키지, 인포그래픽, 시각화 방법론
  * 출력자료: 데이터 시각화 보고서

#### 모델링
##### 데이터 분할
  * 입력자료: 분석용 데이터셋
  * 프로세스 및 도구: 데이터 분할 패키지
  * 출력자료: 훈련용 데이터, 테스트용 데이터

##### 데이터 모델링
  * 입력자료: 분석용 데이터셋
  * 프로세스 및 도구: 통계 모델링 기법, 기계학습, 모델 테스트
  * 출력자료: 모델링 결과 보고서

##### 모델 적용 및 운영 방안
  * 입력자료: 모델링 결과 보고서
  * 프로세스 및 도구: 모니터링 방안 수립, 알고리즘 설명서 작성
  * 출력자료: 알고리즘 설명서, 모니터링 방안

#### 모델 평가 및 검증
별도의 데이터셋으로 모델의 객관성과 실무 적용성을 검증
목표 미달시, 튜닝 작업 수행

##### 모델 평가
품질 관리 차원에서 모델 평가 프로세스 진행
  * 입력자료: 모델링 결과 보고서, 평가용 데이터
  * 프로세스 및 도구: 모델 평가, 모델 품질관리, 모델 개선작업
  * 출력자료: 모델 평가 보고서

##### 모델 검증
운영용 데이터를 확보하여 모델의 품질을 최종 검증
  * 입력자료: 모델링 결과 보고서, 모델 평가 보고서, 검증용 데이터
  * 프로세스 및 도구: 모델 검증
  * 출력자료: 모델 검증 보고서

#### 8. 시스템 구현(Developing)
##### 설계 및 구현
* 시스템 분석 및 설계
알고리즘 설명서를 근거하여 Application 구축 설계 프로세스 진행
  * 입력자료: 알고리즘 설명서, 운영중인 시스템 설명서
  * 프로세스 및 도구: 정보시스템 개발방법론
  * 출력자료: 시스템 분석 및 설계서
* 시스템 구현
  * 입력자료: 시스템 분석 및 설계서, 알고리즘 설명서
  * 프로세스 및 도구: IDE, 프로그램 언어, 패키지
  * 출력자료: 구현 시스템

##### 시스템 테스트 및 운영
* 시스템 테스트
  * 입력자료: 구현 시스템,시스템 테스트 계획서
  * 프로세스 및 도구: 품질관리 활동
  * 출력자료: 시스템 테스트 결과보고서

* 시스템 운영 계획
  * 입력자료: 시스템 분석 및 설계서, 구현 시스템
  * 프로세스 및 도구: 운영계획 수립, 운영자 및 사용자 교육
  * 출력자료: 운영자 매뉴얼, 사용자 매뉴얼, 시스템 운영 계획서


#### 9. 평가 및 전개(Deploying)
##### 모델 발전 계획 수립
* 모델 발전 계획 : 모델의 계속성 확보
* 프로젝트 평가 및 보고 : 프로젝트의 성과를 정량, 정성적으로 평가, 지식 자산화, 프로젝트 종료

### Chapter 03. 분석 과제 발굴
분석 과제 도출 방식은 크게 2가지
* 하향식 접근 방식(Top Down)
문제가 주어지고, 이에 대한 해법을 찾기 위하여 각 과정이 체계적으로 단계화되어 수행
* 상향식 접근 방식(Bottom Up)
문제 정의 자체가 어려운 경우 데이터를 기반으로 문제의 재정의 및 해결방안 탐색 후 지속적으로 개선
* 최근 대규모의 데이터가 생성되고 빠르게 변하는 기업 환경에서 상향식 접근 방식이 증가하고 있는 추세
* 디자인 사고 프로세스의 예처럼 새로운 상품을 개발하거나 전략 수립 등 중요한 의사결정을 할 때 가능한 옵션을 도출하는 Bottom Up 접근 방식의 발산 단계와, 도출된 옵션을 분석하고 검증하는 하향식 접근 방식의 수렴 단계를 반복적으로 수행하는 식으로 상호 보완하는 것이 좋음

### 1. 하향식 접근법(Top Down Approach)
#### 문제 탐색(Problem Discovery) 단계
솔루션 관점보단 문제를 해결함으로써 발생하는 가치에 중점을 두는 것이 중요

#####  비즈니스 모델 기반 문제 탐색
  * 비즈니스 모델 캔버스의 9가지 블록을 단순화하여 업무(Operation), 제품(Product), 고객(Customer) 단위로 무제 발굴하고, 이를 관리하는 규제와 감사 영역과 지원 인프라 영역에 대한 기회를 추가로 도출하는 작업 수행
* 새로운 문제 발굴 및 장기적인 접급을 위해서는 "혁신(Innovation)"의 관점에서 분석 기회를 추가 도출 요구
* 거시적 관점의 요인, 경쟁자의 동향, 시장의 니즈 변화, 역량의 재해석 등 새로운 관점의 접근 통한 주제 발굴을 수행해야 함.
* 이러한 작업 수행 시 분석가뿐만 아니라, 해당 기능을 수행하는 직원 및 관련자에 대한 폭넓은 인터뷰, 워크숍 형태의 아이디어 발굴 작업이 필요
* 거시적 관점의 메가 트렌드에서는 STEEP 영역으로 나누어서 좀 더 폭넓게 기회 탐색 수행
  * Social 영역
  * Technological 영역
  * Economic 영역
  * Environment 영역
  * Political 영역
* 경쟁자 확대 관점에서는 대체재와 신규 집입자 등으로 관점을 확대하여 위협이 될 수 있는 상황에 대한 분석 기회 발굴의 폭을 넓혀 탐색
  * 대체재 영역
  * 경쟁자 영역
  * 신규 진입자 영역
* 시장의 니즈 탐색 관점에서는 직접 고객 뿐만 아니라, 고객과 접촉하는 역할을 수행하는 Channel, 고객의 구매와 의사결정에 영향을 미치는 Influencer에 대한 폭넓은 관점을 바탕으로 분석 기회 탐색
  * 고객 영역
  * 채널 영역
  * 영향자들 영역
* 영향의 재해석 관점에서는 해당 조직 및 기업이 보유한 역량 뿐만 아니라, 해당 조직의 비즈니스에 영향을 끼치는 파트너 네트워크를 포함한 활용 가능한 역량을 토대로 분석 기회 탐색
  * 내부 역량 영역
  * 파트너와 네트워크 영역

##### 외부 참조 모델 기반 문제 탐색
유사 동종의 환경에서 기존에 수행한 분석 과제를 살펴보는 것도 주요한 시사점 도출
데이터 분석을 통한 가치 발굴 사례를 정리하여 풀(Pool)로 만들어 둔다면 과제 발굴 및 탐색 시 빠르고 의미 있는 분석 기회 도출이 가능

##### 분석 유즈 케이스(Analytics Use Case) 정의
풀어야 할 문제에 대한 상세한 설명 및 해당 문제를 해결했을 때 발생하는 효과를 명시함으로써 향후 데이터 분석 문제로의 전환 및 적합성 평가에 활용

#### 문제 정의(Problem Definition) 단계
문제 해결 달성을 위해 필요한 데이터 기법을 정의하기 위한 데이터 분석의 문제로의 변환 수행
ex) 고객 이탈 증대 --> 고객의 이탈에 영향을 미치는 요인을 식별하고 이탈 가능성을 예측
분석 문제 정의 및 요구사항은 분석 수행 당사자 뿐만아니라 문제가 해결되었을때 효용을 얻을 수 있는 최종사용자 관점에서 이루어 져야 함

#### 해결방안 탐색(Solution Search) 단계
> |  | 분석 역량 확보|  분석 역량 미확보  |
> |---|:---:|:---:|
>  | 기존 시스템 사용 | 기존 시스템 개선 활용 | 교육 및 채용을 위한 역량 확보|
>  | 신규 도입| 시스템 고도화| 전문 업체 Sourcing |

#### 타당성 검토 단계
* 경제적 타당성
* 데이터 및 기술적 타당성
  * 분석 역량의 경우 실제 프로젝트 수행 시 걸림돌이 되는 경우가 많음

### 2. 상향식 접근법(Bottom up Approach)
  * 다양한 원천 데이터를 대상으로 분석을 수행하여 가치 있는 문제를 도출하는 일련의 과정
  * 현장 관찰과 감정이입, 대상의 관점으로의 전환을 수행
  * 답을 미리 내는 것이 아니라, 사물을 있는 그대로 인식하는 What 관점에서 보아야 함
  * 디자인 사고  프로세스
  * Empathize(감정이입) -> Define(정의) -> Ideate -> Prototype -> Test
    * 감정이입 : 데이터 자체를 관찰하여 대상을 좀 더 잘 이해하는 방식으로의 수행
  * 비지도 학습을 통한 인사이트 도출
  * 인과관계(Know-why) 로부터 상관관계(Know-affinity) 분석으로의 이동이 빅데이터 분석의 주요 변화

#### 시행착오를 통한 문제 해결
  * 프로토타이핑(Prototyping) : 사용자가 요구사항이나 데이터를 정확히 규명하기 어려워 일단 분석을 시도한 후 결과를 확인해 가면서 반복적으로 개선해 나가는 방법
  * 프로토타이핑 접근법 기본 프로세스
    * 가설의 생성(Hypotheses)
    * 디자인에 대한 실험(Design Experiments)
    * 실제 환경에서의 테스트(Test)
    * 테스트 결과에서의 통찰 도출 및 가설 확인(Insight)

  * 다음과 같은 이유 때문에 프로토타이핑의 필요성 존재
    * 문제에 대한 인식 수준 : 정의가 불명확.. 등
    * 필요 데이터 존재 여부의 불확실성
    * 데이터의 사용 목적의 가변성

### 3. 분석 과제 정의
  * 다양한 방식을 통해서 도출한 분석 과제를 정의서 양식을 활용해서 상세하게 정의
  * 분석과제 정의서는 향후 프로젝트 수행계획의 일부로 활용됨

### chapter04. 분석 프로젝트 관리 방안
  * 과제 형태로 도출된 분석 기회는 프로젝트를 통해 그 가치를 증명하고 목표 달성 해야 함
  * 분석 과제의 주요 5가지 특성주요 관리 영역
    * Data Size : 데이터 양을 고려한 관리 방안 수립 필요
    * Data Complexity : 비정형 데이터를 통합해서 분석 프로젝트 진행 시, 초기 데이터의 확보, 해당 데이터에 잘 적용될 수 있는 분석 모델 선정 등 사전 고려 필요
    * Speed : 일단위, 주단위, 실시간인지에 대한 분석모델 성능 및 속도를 고려한 개발 필요
    * Analytic Complexity : 분석 모델 복잡도와 정확도는 trade off 관계
    * Accuracy & Precision : Accuracy는 모델과 실제 값 사이의 차이가 적다는 정확도를 의미, Precision은 모델을 지속적으로 반복했을 때 편차의 수준으로써 일관적으로 동일한 결과를 제시한다는 것을 의미  
    분석의 활용 측면 : Accuracy 중요, 분석의 안정성 측면 : Precision 중요  
    둘의 관계는 trade-off 관계 이므로, 모델의 해석 및 적용시 사전 고려 필요

#### 1. 분석 프로젝트의 특성
   * 프로젝트 관점에서는 도출된 분석 과제를 잘 구현하여 원하는 결과를 얻고 사용자가 원할하게 활용할 수 있도록 전체적인 과정을 고려해야 하기 때문에 개별적인 분석 업무 수행뿐만 아니라 전반적인 프로젝트 관리 또한 중요
   * 분석 프로젝트에서는 데이터 영역과 비즈니스 영역의 현황을 이해하고, 프로젝트 목표인 분석의 정확도 달성과 결과에 대한 가치 이해를 전달하는 조정자로써의 분석가의 역할이 중요
   * 프로토타이핑 방식의 Agile 프로젝트 관리방식에 대한 고려도 필요
   * 데이터 분석의 지속적인 반복 및 개선을 통하여 의도했던 결과에 더욱 가까워지는 형태로 프로젝트 진행될 수 있도록 적절한 관리 방안 수립이 사전에 필요

#### 2. 분석 프로젝트 관리방안
  * 분석 프로젝트는 데이터 분석의 특성을 살려 프로젝트관리 지침(KS A ISO 21500:2013)을 기본 가이드로 활용할 필요가 있음
  * 프로젝트관리 지침의 프로젝트 관리 체계는 10가지 주제 그룹으로 구성
     * 통합
       * 프로젝트관리 프로세스들이 통합적으로 운영될 수 있도록 관리   
     * 이해관계자
       * 데이터 분석 프로젝트는 데이터 전문가, 비즈니스 전문가, 분석 전문가, 시스템 전문가 등 다양한 전문가가 참여하므로 이해관계자의 식별과 관리가 필요
     * 범위
       * 분석 진행시 데이터 형태, 양, 모델 알고리즘에 따라 범위가 빈번하게 변경
     * 자원
       * 인력의 공급이 부족하므로, 프로젝트 수행 전 전문가 확보 검토 필요  
     * 시간
       *  초기에 의도했던 결과가 안나올 수 있으므로 많은 시간 소요 가능
       *  분석 결과에 대한 품질이 보장된다는 전제로 Time Boxing 기법으로 일정관리를 진행하는 것이 필요
     * 원가
       * 외부 데이터 분석인 경우 원가가 비쌀 수 있음
       * 상용 버전 도구 필요성 확인
     * 리스크
       * 분석에 대한 데이터 미확보로 분석 프로젝트 진행이 어려울 수 있어 관련 위험 식별
       * 데이터 및 분석 알고리즘 한계로 품질목표 달성 못할 수 있음
     * 품질
       * 분석 프로젝트를 수행한 결과에 대한 품질목표를 사전에 수립하여 확정해야 함
       * 프로젝트 품질은 품질통제와 품질보증으로 나누어 수행해야 함
     * 조달
       * 프로젝트 목적에 맞는 외부소싱을 적절하게 운영할 필요 있음
       * PoC 형태의 프로젝트는 인프라 구매가 아닌 클라우드 등의 다양한 방안 검토 필요
     * 의사소통
       * 전문성이 요구되는 데이터 분석의 결과를 모든 프로젝트 이해관계자가 공유할 수 있도록 해야 함
