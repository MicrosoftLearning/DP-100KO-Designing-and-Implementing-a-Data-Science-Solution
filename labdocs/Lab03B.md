# 랩 3B: 모델 학습 및 등록

기계 학습에서는 주로 애플리케이션에 예측 서비스를 제공하는 데 사용할 수 있는 모델의 학습을 수행합니다. 이 랩에서는 Azure Machine Learning 실험을 사용하여 학습 스크립트를 실행하는 방법과 학습된 모델을 등록하는 방법을 살펴보겠습니다.

## 시작하기 전에

이 랩을 시작하기 전에 [랩 1A](Lab01A.md) 및 [랩 1B](Lab01B.md)를 완료해야 합니다. 이 두 랩에는 이 랩에서 사용되는 Azure Machine Learning 작업 영역 및 기타 리소스를 만드는 작업이 포함되어 있습니다.

## 작업 1: Azure Machine Learning SDK를 사용하여 모델 학습 및 등록 진행

이 작업에서는 Notebook의 코드를 사용하여 학습 스크립트를 Azure Machine Learning 실험으로 실행합니다.

1. [Azure Machine Learning Studio](https://ml.azure.com)에서 작업 영역 **컴퓨팅** 페이지를 표시하고 **컴퓨팅 인스턴스** 탭에서 컴퓨팅 인스턴스를 시작합니다.
2. 컴퓨팅 인스턴스가 실행 중이면 인증된 세션이 만료되지 않도록 브라우저에서 Azure Machine Learning Studio 웹 페이지를 새로 고칩니다. 그런 다음 **Jupyter** 링크를 클릭하여 새 브라우저 탭에서 Jupyter 홈 페이지를 엽니다.
3. Jupyter 홈 페이지의 **Users/DP100** 폴더에서 **03B - Training Models.ipynb** Notebook을 엽니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.
4. Notebook에서 코드 실행이 완료되면 **파일** 메뉴에서 **닫기 및 중지**를 클릭하여 Notebook을 닫고 Python 커널을 종료합니다. 그런 후에 모든 Jupyter 브라우저 탭을 닫습니다.
5. Azure Machine Learning Studio의 **컴퓨팅** 페이지에서 컴퓨팅 인스턴스를 선택한 다음 **중지**를 클릭하여 인스턴스를 종료합니다.
