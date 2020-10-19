# 랩 1B: Azure Machine Learning 도구 사용

이 랩에서는 Azure Machine Learning 작업 영역을 사용하는 데 필요한 여러 가지 다양한 도구를 살펴봅니다.

## 시작하기 전에

이 랩을 시작하기 전에 [이전 랩](Lab01A.md)의 지침에 따라 Azure Machine Learning 작업 영역을 만들어야 합니다.

## 작업 1: 컴퓨팅 인스턴스에서 Azure ML SDK 사용

환경 설정을 위한 대다수 자산 관리 작업은 *Studio* 인터페이스에서 수행할 수 있습니다. 하지만 이러한 작업을 더 쉽게 반복하고 자동화하기 위해 구성 작업을 스크립트로 작성할 수도 있습니다.

1. [Azure Machine Learning Studio](https://ml.azure.com)의 작업 영역 **컴퓨팅** 페이지에서 **컴퓨팅 인스턴스** 탭을 표시하고 필요한 경우 이전 랩에서 만든 컴퓨팅 인스턴스가 시작될 때까지 **새로 고침**을 주기적으로 클릭합니다.
2. 인증된 세션이 만료되지 않도록 브라우저에서 Azure Machine Learning Studio 웹 페이지를 새로 고칩니다. 그런 다음 컴퓨팅 인스턴스의 **Jupyter** 링크를 클릭하여 새 탭에서 Jupyter Notebook을 엽니다. 메시지가 표시되면 Azure 구독과 연결된 Microsoft 계정을 사용하여 로그인합니다.
3. Notebook 환경에서 새 **터미널**을 만듭니다. 그러면 명령 셸이 포함된 새 탭이 열립니다.
4. 컴퓨팅 인스턴스 이미지에는 Azure Machine Learning SDK가 이미 설치되어 있습니다. 그러나 이 과정에 필요한 선택적 패키지가 포함되어 있는 최신 버전을 사용하는 것이 좋으므로, 다음 명령을 입력하여 SDK 패키지를 업데이트합니다.

    ```bash
    pip install --upgrade azureml-sdk[notebooks,automl,explain]
    ```

    패키지 종속성이 설치 중 몇 가지 경고가 표시될 수 있습니다. 이러한 메시지는 무시해도 됩니다.

    > **추가 정보**: Azure ML SDK 및 선택적 구성 요소 설치에 대한 자세한 내용은 [Azure ML SDK 설명서](https://docs.microsoft.com/python/api/overview/azure/ml/install?view=azure-ml-py)를 참조하세요.

5. 그런 후에 다음 명령을 실행하여 현재 디렉터리를 **Users** 디렉터리로 변경하고 이 과정의 랩에서 사용할 Notebook을 검색합니다.

    ```bash
    cd Users
    git clone https://github.com/MicrosoftLearning/DP100
    ```

6. 명령이 완료되면 터미널 탭을 닫고 Jupyter Notebook 파일 탐색기에서 홈 페이지를 표시합니다. 그런 다음 **Users** 폴더를 엽니다. 이 폴더에는 이 랩의 나머지 부분에서 사용할 파일이 포함된 **DP100** 폴더가 있어야 합니다.
7. **Users/DP100** 폴더에서 **01B - Intro to the Azure ML SDK.ipynb** Notebook을 엽니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.
8. Notebook에서 코드 실행이 완료되면 **파일** 메뉴에서 **닫기 및 중지**를 클릭하여 Notebook을 닫고 Python 커널을 종료합니다. 그런 후에 모든 Jupyter 브라우저 탭을 닫습니다.
9. **컴퓨팅** 페이지의 Azure Machine Learning 스튜디오에서 그 날의 Azure Machine Learning 작업이 끝나면 컴퓨팅 인스턴스를 선택하고 **중지**를 눌러 종료하십시오. 또는 다음 랩을 위해 실행 상태로 둡니다.
