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

## 작업 2: Visual Studio 코드 공간 설정

Azure Machine Learning의 컴퓨팅 인스턴스를 사용하면 자체 Python 설치를 관리하지 않고도 Azure ML 사용을 위한 Python 환경을 쉽게 관리할 수 있습니다. 하지만 자체 그래픽 Python 개발 환경을 사용하려는 경우도 있습니다. 이 과정에서는 환경을 간편하게 설치하기 위해 Visual Studio 코드 공간을 사용합니다. 그러나 Azure Machine Learning SDK 사용 시의 원칙은 어떤 Python 환경에서나 동일합니다.

> **참고**: 이 문서를 작성하는 시점에서 Visual Studio 코드 공간은 *미리 보기* 상태입니다. 따라서 예기치 않은 오류 메시지가 나타날 수 있습니다.

1. 새 브라우저 탭에서 [https://online.visualstudio.com](https://online.visualstudio.com)으로 이동합니다. 메시지가 표시되면 Azure 로그인에 사용한 것과 같은 Microsoft 자격 증명을 사용하여 Visual Studio 코드 공간에 로그인합니다.
2. 다음 설정으로 코드 공간을 만듭니다(Visual Studio 코드 공간 계획이 아직 없는 경우 메시지가 표시되면 코드를 만들 수 있습니다 - 이는 코드 공간의 리소스 사용률 추적에 사용됩니다).
    - **코드 공간 이름**: *원하는 고유한 이름*
    - **Git 리포지토리**: MicrosoftLearning/DP100
    - **인스턴스 유형**: 표준(Linux)
    - **유휴 코드 공간을 일시 중단할 시간**: 60분
3.  코드 공간이 만들어질 때까지 기다립니다. Visual Studio Code의 브라우저 기반 인스턴스가 열립니다.
4. 환경을 설정하는 동안 1분 정도 기다립니다. 아무 일도 일어나지 않는 것처럼 보일 수 있지만 백그라운드에서는 랩에서 사용할 몇 가지 확장 프로그램을 설치하고 있습니다. 다음과 같은 사항을 확인할 수 있습니다.
    - 코드 공간이 준비되면 스크립트 창이 열려 상태를 표시합니다.
    - Visual Studio Code 인터페이스가 로드됩니다.
    - 이 리포지토리의 파일은 왼쪽의 창에 나타납니다.
5. 설치가 성공적으로 완료되면 **만들기 로그** 창을 닫을 수 있습니다. 

    Visual Studio 코드 공간은 웹 브라우저에서 사용할 수 있는 Visual Studio Code의 호스트된 인스턴스입니다. 일반 코드 편집 환경인 Visual Studio Code에서는 *확장*을 설치하여 다양한 프로그래밍 언어를 지원할 수 있습니다. Python을 사용하려는 경우에는 Microsoft Python 확장이 필요합니다. 이 확장은 **DP100** 리포지토리에서 이 환경을 만들 때 일반적으로 사용되는 몇 가지 Python 패키지와 함께 설치된 상태입니다.

    코드 공간에는 Visual Studio Code 인터페이스 내 Jupyter 노트북의 공통 패키지 및 지원을 포함하여 Python(버전 3.x)의 설치가 포함되어 있습니다. Azure Machine Learning과 함께 작동하는 코드를 실행하려면 Azure ML SDK를 설치하기만 하면 됩니다.

6. Visual Studio 코드 공간의 애플리케이션 메뉴(**&#9776;**)의 **보기** 메뉴에서 **명령 팔레트**를 클릭합니다(또는 CTRL+SHIFT+P를 누릅니다). 그런 다음 팔레트에서 **Python**:** 터미널 만들기** 명령을 입력합니다. 그러면 인터페이스 하단에 Python 터미널 창이 열립니다.
7. 터미널 창에서 이제 다음 명령을 입력하여 *notebooks* 추가 패키지(선택 사항)와 함께 Azure Machine Learning SDK를 설치합니다.

    ```bash
    pip install azureml-sdk[notebooks]
    ```

8. 터미널 창을 닫습니다.

## 작업 3: Visual Studio Online에서 Azure ML SDK 사용

Python 개발 환경을 설치했으므로 이제 이 환경에서 Azure Machine Learning SDK를 사용할 수 있습니다. 그러려면 먼저 Azure Machine Learning 작업 영역에 연결하는 데 필요한 구성 정보를 가져와야 합니다.

1. 새 브라우저 탭에서 Azure Portal [https://portal.azure.com](https://portal.azure.com)을 열고 필요한 경우 로그인합니다.
2. 이전 랩에서 만든 Azure Machine Learning 작업 영역 리소스를 열고 해당 리소스의 **개요** 페이지에서 **config.json 다운로드**를 클릭하여 로컬 컴퓨터에 파일을 다운로드합니다.
3. 로컬 컴퓨터에서 다운로드한 **config.json**파일을 브라우저의 코드 공간으로 끌어서 노트북 파일에 놓습니다. 이렇게 하면 구성 파일이 업로드되고 코드 공간 편집기에서 열립니다.
4. config.json 파일의 내용을 검토하고 닫습니다.
5. 코드 공간에서 **01B - Intro to the Azure ML SDK.ipynb** Notebook을 엽니다. 그러면 Jupyter Notebook 인터페이스에 로드됩니다. Jupyter Notebook 인터페이스는 처음 사용할 때 로드하는 데 시간이 다소 걸릴 수 있으며 창 두 개가 잠시 표시될 수 있습니다. 두 창 중 하나에는 Notebook의 JSON 표현이 포함되어 있고, 다른 하나에는 Notebook의 시각적 인터페이스가 포함되어 있습니다.
6. Notebook이 로드되면 Azure Machine Learning Notebook VM Jupyter 환경에서와 마찬가지로 각 코드 셀을 차례로 실행하여 포함된 메모를 읽습니다.

## 작업 4: Visual Studio Code Azure Machine Learning 확장 사용

Visual Studio 코드 공간 또는 로컬에 설치한 Visual Studio Code에서 Azure Machine Learning을 사용하려는 경우 Azure Machine Learning 확장을 설치하면 코드 개발 환경과 Azure Machine Learning Studio 웹 인터페이스 간을 전환하지 않고도 작업 영역의 리소스를 더 쉽게 사용할 수 있습니다.

1. Visual Studio 코드 공간 인터페이스에서 **확장** 탭(&#8862;)을 클릭하고 "Azure Machine Learning"을 검색합니다. 그런 다음 Microsoft에서 제공하는 **Azure Machine Learning** 확장을 설치합니다. 확장을 설치한 후 **필수 항목 다시 로드** 단추를 클릭하여 확장이 설치된 환경을 다시 로드합니다.
2. Visual Studio 코드 공간 인터페이스에서 **Azure** 탭(***&Delta;***)을 클릭하고 **Azure Machine Learning** 섹션에서 구독 및 Azure Machine Learning 작업 영역을 확장합니다.
3. **컴퓨팅 클러스터**를 확장한 다음 작업 영역에서 만든 **aml-cluster** 컴퓨팅 리소스가 **로컬** 컴퓨팅 리소스와 함께 목록에 표시되는지 확인합니다. 여기서 로컬 컴퓨팅 리소스는 호스트된 코드 공간 환경을 나타냅니다. 작업 영역에 정의된 컴퓨팅 리소스와 로컬 컴퓨팅에서 Azure Machine Learning 코드 실험을 실행할 수 있습니다.
4. Visual Studio 코드 공간 브라우저 탭을 닫습니다.
