#  Azure의 데이터 과학 솔루션 디자인 및 구현

> ## 중요 공지 사항!
>
> 이 리포지토리는 **2020년 12월 12일**에 [새 리포지토리](https://aka.ms/mslearn-dp100)로 바뀝니다. 해당 교육 과정 자료도 이 날짜에 업데이트됩니다. 변경의 이유는 다음과 같습니다.
> - [DP-100 강사 진행 과정](https://docs.microsoft.com/learn/certifications/courses/dp-100t01_)에서 사용되는 랩과 [Microsoft Learn](https://docs.microsoft.com/learn/paths/build-ai-solutions-with-azure-ml-service/)의 해당 온라인 모듈에 포함된 자기 주도적 연습 통합
> - Azure Machine Learning 서비스와 SDK의 최근 변경 내용을 반영하도록 랩 업데이트
> - 기계 학습 모델 작성 시의 책임 관련 주제를 다루는 신규 랩 추가
>
> Azure ML SDK 1.19.0은 2020년 12월 7일에 릴리스되었습니다. 이 릴리스에서는 추정기 사용이 중단되었으므로 추정기를 사용하는 랩에서는 오류가 발생합니다. 다음 주에 이 문제가 해결된 개정판 교육 과정이 릴리스될 예정입니다. 일단은 다음 해결 방법 중 하나를 적용할 수 있습니다.
> - SDK 버전을 1.18.0으로 고정합니다. 즉, SDK 설치 단계에서 pip install azureml-sdk==1.18.0을 사용합니다. 단, 이 방법을 사용하는 경우에는 이후 랩에서 호환성 문제가 다소 발생할 수도 있습니다.
> - 다음 주부터 https://aka.ms/mslearn-dp100에서 개정판 교육 과정의 "공식" 랩으로 제공될 업데이트된 랩을 사용합니다. 업데이트된 랩도 진행 방식은 기존 랩과 어느 정도 비슷하지만 추정기는 사용하지 않습니다.
>
> 이 리포지토리는 조만간 보관될 예정입니다.

## 과정 랩

[DP-100 *Azure의 데이터 과학 솔루션 디자인 및 구현*](https://docs.microsoft.com/ko-kr/learn/certifications/courses/dp-100t01) 과정용 실습 랩 연습을 시작합니다. 랩은 과정과 함께 진행할 수 있으며, 강의 자료에 설명되어 있는 기술을 사용하여 랩을 연습할 수 있습니다.

각 Markdown 문서의 지침을 그대로 따르면서 순서대로 랩을 완료해야 합니다.

랩을 진행하려면 Microsoft Azure 구독이 필요합니다. 강사가 구독을 제공하지 않은 경우 [https://azure.microsoft.com](https://azure.microsoft.com)에서 등록을 하면 무료 평가판을 받을 수 있습니다.

> **팁**: 랩 작업을 진행할 때는 고유한 브라우저 설정, 네트워크 구성 등으로 인해 예기치 않은 문제가 발생할 수 있습니다. 흔히 발생하는 몇 가지 문제와 도움이 될 수 있는 관련 정보는 [팁](TIPS.md) 문서에서 확인할 수 있습니다. 해당 문서에서 이러한 랩의 [알려진 문제](https://github.com/MicrosoftLearning/DP100/issues)도 확인할 수 있습니다.

### 모듈 1: Azure Machine Learning 소개

- [랩 1A: Azure Machine Learning 작업 영역 만들기](Lab01A.md)
- [랩 1B: Azure Machine Learning 도구 사용](Lab01B.md)

### 모듈 2: Designer를 활용한 코드 없는 기계 학습

- [랩 2A: Azure ML Designer를 활용해 학습 파이프라인 만들기](Lab02A.md)
- [랩 2B: Azure ML Designer를 활용해 서비스 배포](Lab02B.md)

### 모듈 3: 실험 실행 및 모델 학습

- [랩 3A: 실험 실행](Lab03A.md)
- [랩 3B: 모델 학습 및 등록](Lab03B.md)

### 모듈 4: 데이터 사용

- [랩 4A: 데이터 저장소 사용](Lab04A.md)
- [랩 4B: 데이터 세트 사용](Lab04B.md)

### 모듈 5: 컴퓨팅 컨텍스트

- [랩 5A: 환경 사용](Lab05A.md)
- [랩 5B: 컴퓨팅 대상 사용](Lab05B.md)

### 모듈 6: 파이프라인을 사용해 작업 오케스트레이션

- [랩 6A: 파이프라인 만들기](Lab06A.md)
- [랩 6B: 파이프라인 게시](Lab06B.md)

### 모듈 7: 모델 배포 및 사용

- [랩 7A: 실시간 유추 서비스 만들기](Lab07A.md)
- [랩 7B: 일괄 처리 유추 서비스 만들기](Lab07B.md)

### 모듈 8: 최적 모델 대상 학습 진행

- [랩 8A: 하이퍼 매개 변수 튜닝](Lab08A.md)
- [랩 8B: 자동화된 Machine Learning 사용](Lab08B.md)

### 모듈 9: 모델 해석

- [랩 9A: 자동화된 Machine Learning 설명 검토](Lab09A.md)
- [랩 9B: 모델 해석](Lab09B.md)

### 모듈 10: 모델 모니터링

- [랩 10A: Application Insights를 사용해 모델 모니터링](Lab10A.md)
- [랩 10B: 데이터 드리프트 모니터링](Lab10B.md)

> **중요**: 이러한 랩에서 사용되는 가상 머신은 더 이상 필요하지 않으면 중지해야 합니다. 그러면 이러한 서비스와 관련하여 소진되는 Azure 크레딧을 최소화할 수 있습니다. 모든 랩을 완료한 후에 랩에서 만든 리소스 그룹을 사용하여 더 이상 실험을 수행하지 않으려는 경우 해당 리소스 그룹을 삭제하는 것이 좋습니다.

## 정보 제공

현재 이 리포지토리에서는 외부 참여가 불가능합니다. 제안 사항이 있거나 오류가 확인되면 [문제](https://github.com/MicrosoftLearning/DP100/issues)로 보고해 주시기 바랍니다.

