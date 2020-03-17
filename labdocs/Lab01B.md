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

    > **추가 정보**: Azure ML SDK 및 선택적 구성 요소 설치에 대한 자세한 내용은 [Azure ML SDK 설명서](https://docs.microsoft.com/python/api/overview/azure/ml/install?view=azure-ml-py)를 참조하세요.

5. 그런 후에 다음 명령을 실행하여 현재 디렉터리를 **Users** 디렉터리로 변경하고 이 과정의 랩에서 사용할 Notebook을 검색합니다.

    ```bash
    cd Users
    git clone https://github.com/MicrosoftLearning/DP100
    ```

6. 명령이 완료되면 터미널 탭을 닫고 Jupyter Notebook 파일 탐색기에서 홈 페이지를 표시합니다. 그런 다음 **Users** 폴더를 엽니다. 이 폴더에는 이 랩의 나머지 부분에서 사용할 파일이 포함된 **DP100** 폴더가 있어야 합니다.
7. **Users/DP100** 폴더에서 **01B - Intro to the Azure ML SDK.ipynb** Notebook을 엽니다. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.
8. Notebook에서 코드 실행이 완료되면 **파일** 메뉴에서 **닫기 및 중지**를 클릭하여 Notebook을 닫고 Python 커널을 종료합니다. 그런 후에 모든 Jupyter 브라우저 탭을 닫습니다.
9. Azure Machine Learning Studio의 **컴퓨팅** 페이지에서 컴퓨팅 인스턴스를 선택한 다음 **중지**를 클릭하여 인스턴스를 종료합니다.

## 작업 2: Visual Studio Online 환경 설정

Azure Machine Learning의 컴퓨팅 인스턴스를 사용하면 자체 Python 설치를 관리하지 않고도 Azure ML 사용을 위한 Python 환경을 쉽게 관리할 수 있습니다. 하지만 자체 그래픽 Python 개발 환경을 사용하려는 경우도 있습니다. 이 과정에서는 환경을 간편하게 설치하기 위해 Visual Studio Online을 사용합니다. 그러나 Azure Machine Learning SDK 사용 시의 원칙은 어떤 Python 환경에서나 동일합니다.

> **참고**: 이 문서를 작성하는 시점에서 Visual Studio Online은 *미리 보기* 상태입니다. 따라서 예기치 않은 오류 메시지가 나타날 수 있습니다.

1. 새 브라우저 탭에서 [https://online.visualstudio.com](https://online.visualstudio.com)으로 이동하여 **시작하기**를 클릭합니다.
2. Azure에 로그인하는 데 사용한 것과 같은 Microsoft 자격 증명을 사용하여 Visual Studio Online에 로그인합니다.
3. 다음 설정을 사용하여 새 환경을 만듭니다. 해당 메시지가 표시되면 먼저 Azure 구독에서 청구 계획을 만듭니다.
    - **환경 이름**: *원하는 고유한 이름*
    - **Git 리포지토리**: MicrosoftLearning/DP100
    - **인스턴스 유형**: 표준(Linux)
    - **유휴 환경을 일시 중단할 시간**: 30분
4. 환경이 만들어질 때까지 기다렸다가 환경 이름을 클릭하여 환경에 연결합니다.

    Visual Studio Online은 웹 브라우저에서 사용할 수 있는 Visual Studio 코드의 호스트된 인스턴스입니다. 일반 코드 편집 환경인 Visual Studio Code에서는 *확장*을 설치하여 다양한 프로그래밍 언어를 지원할 수 있습니다. Python을 사용하려는 경우에는 Microsoft Python 확장이 필요합니다. 이 확장은 **DP100** 리포지토리에서 이 환경을 만들 때 일반적으로 사용되는 몇 가지 Python 패키지와 함께 설치된 상태입니다.

    호스트된 Visual Studio Code 환경에는 Python 설치 3개(버전 2.7.13, 3.5.3, 3.8.0)가 포함되어 있습니다. 여기서는 Python **3.5.3** 가상 환경을 사용합니다. 자체 설치를 사용하는 경우에는 Python 설치, 가상 환경 만들기, 필요한 패키지 설치를 직접 수행해야 합니다. 이 랩에서는 일반 Python 구성 작업이 대부분 완료된 상태입니다. 하지만 Azure Machine Learning SDK는 설치해야 합니다.

5. Visual Studio Online 환경에서 DP100 리포지토리의 콘텐츠가 로드될 때까지 기다린 다음 애플리케이션 메뉴(**&#9776;**)의 **보기** 메뉴에서 **명령 팔레트**를 클릭하거나 Ctrl+Shift+P를 누릅니다. 그런 다음 팔레트에서 **Python: 터미널 만들기** 명령을 입력합니다. 그러면 Visual Studio Online 인터페이스 하단에 Python 터미널 창이 열립니다.

    > **팁**: *Python: 터미널 만들기* 명령이 목록에 표시되지 않으면 브라우저를 새로 고쳐 환경을 다시 로드한 후에 다시 시도하세요.

6. 터미널 창에서 다음 명령을 입력하여 Python 3.5.3 가상 환경이 정의되어 있는 디렉터리로 변경합니다.

    ````bash
    cd /usr/bin
    ````

7. 이제 다음 명령을 사용하여 *notebooks* 추가 패키지(선택 사항)와 함께 Azure Machine Learning SDK를 설치합니다.

    ```bash
    sudo pip install azureml-sdk[notebooks]
    ```

8. 터미널 창을 닫습니다.

## 작업 3: Visual Studio Online에서 Azure ML SDK 사용

Python 개발 환경을 설치했으므로 이제 이 환경에서 Azure Machine Learning SDK를 사용할 수 있습니다. 그러려면 먼저 Azure Machine Learning 작업 영역에 연결하는 데 필요한 구성 정보를 가져와야 합니다.

1. 새 브라우저 탭에서 Azure Portal([https://portal.azure.com](https://portal.azure.com))을 열고 필요한 경우 로그인합니다.
2. 이전 랩에서 만든 Azure Machine Learning 작업 영역 리소스를 열고 해당 리소스의 **개요** 페이지에서 **config.json 다운로드**를 클릭하여 로컬 컴퓨터에 파일을 다운로드합니다.
3. 텍스트 편집기에서 다운로드한 **config.json** 파일을 열어 해당 내용을 클립보드에 복사합니다. 이 파일에는 작업 영역에 연결하는 데 필요한 구성 정보가 포함되어 있습니다.
4. Visual Studio Online에서 VS Online 작업 영역의 루트 폴더에 **config.json** 파일을 새로 만듭니다.
5. 복사된 구성 정보를 Visual Studio Online 작업 영역의 새 config.json 파일에 붙여넣고 파일을 저장합니다.
6. Visual Studio Online에서 **01B - Intro to the Azure ML SDK.ipynb** Notebook을 엽니다. 그러면 Visual Studio Online 내의 Jupyter Notebook 인터페이스에 Notebook이 로드됩니다. Jupyter Notebook 인터페이스는 처음 사용할 때 로드하는 데 시간이 다소 걸릴 수 있으며 창 두 개가 잠시 표시될 수 있습니다. 두 창 중 하나에는 Notebook의 JSON 표현이 포함되어 있고, 다른 하나에는 Notebook의 시각적 인터페이스가 포함되어 있습니다.
7. Notebook이 로드되면 Visual Studio Online 인터페이스의 왼쪽 하단에서 현재 Python 가상 환경을 클릭합니다. 리포지토리의 구성 설정에 따라 이 환경의 버전은 **Python 3.5.3**으로 변경되었을 것입니다. Notebook은 다른 버전(Notebook의 메타데이터에 표시되어 있음)에서 작성되었지만, 여기서는 이 가상 환경을 다시 선택합니다.
8. Azure Machine Learning Notebook VM Jupyter 환경에서와 마찬가지로 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.

## 작업 4: Visual Studio Code Azure Machine Learning 확장 사용

Visual Studio Online 또는 로컬에 설치한 Visual Studio Code에서 Azure Machine Learning을 사용하려는 경우 Azure Machine Learning 확장을 설치하면 코드 개발 환경과 Azure Machine Learning Studio 웹 인터페이스 간을 전환하지 않고도 작업 영역의 리소스를 더 쉽게 사용할 수 있습니다.

1. Visual Studio Online에서 **확장** 탭(&#8862;)을 클릭하고 "Azure Machine Learning"을 검색합니다. 그런 다음 Microsoft에서 제공하는 **Azure Machine Learning** 확장을 설치합니다. 확장을 설치한 후 **필수 항목 다시 로드** 단추를 클릭하여 확장이 설치된 환경을 다시 로드합니다.
2. Visual Studio Online에서 **Azure** 탭(***&Delta;***)을 클릭하고 **Azure Machine Learning** 섹션에서 구독 및 Azure Machine Learning 작업 영역을 확장합니다.
3. **컴퓨팅**을 확장한 다음 작업 영역에서 만든 **aml-cluster** 컴퓨팅 리소스가 **로컬** 컴퓨팅 리소스와 함께 목록에 표시되는지 확인합니다. 여기서 로컬 컴퓨팅 리소스는 Visual Studio Online 호스트된 환경을 나타냅니다. 작업 영역에 정의된 컴퓨팅 리소스와 로컬 컴퓨팅 리소스에서 Azure Machine Learning 코드 실험을 실행할 수 있습니다.
4. Visual Studio Online 브라우저 탭을 닫습니다.
