---
lab:
    title: '랩 2 - ML 모델 등록 및 배포'
    module: '모듈 2: Azure Machine Learning 서비스를 사용하여 데이터 과학 수행'
---

# 랩 2 - ML 모델 등록 및 배포

## 랩 2.0: 목표

이 랩에서는 다음의 능력을 갖추게 됩니다.

- Azure Machine Learning 서비스를 사용하여 모델 학습.
- 만든 모델을 작업 영역의 레지스트리 등록.
- 모델 채점 스크립트 만들기
- Python 모듈 종속성을 구성하는 YAML 파일 만들기
- 컨테이너 이미지 만들기
- 모델을 웹 서비스로 배포
- 배포된 모델로 새 데이터 채점하기


## 소개

이 랩에서는 Azure Machine Learning 서비스 및 Python SDK를 사용하여 Azure의 마지막 랩에서 개발한 모델을 학습합니다. 학습후 레지스트리에 모델을 등록하고 모델을 사용할 수 있는 Azure Machine Learning 서비스에 배포하는 데 필요한 단계를 수행합니다. 

## 랩 2: 리소스

랩 폴더에서 다음 파일을 사용합니다.

이름                            | 설명
----                            | -----------
Starter_Lab2_Notebook.ipynb     | 사용해야 하는 랩 노트북입니다.  이를 노트북 프로젝트로 가져와 서 엽니다. 


Azure Notebook 프로젝트 만들기 및 노트북 가져오기에 대한 도움말은 https://docs.microsoft.com/ko-kr/azure/notebooks/quickstart-migrate-local-jupyter-notebook을 참조하십시오.

Azure Notebook에 데이터를 업로드하는 방법에 대한 도움말은 https://docs.microsoft.com/ko-kr/azure/notebooks/work-with-project-data-files을 참조하십시오



## 전제 조건

이 랩을 수행하려면 다음이 필요합니다.
- 무료 Azure Notebook 서비스에 등록.  
- Azure Machine Learning 서비스 작업 영역을 프로비전할 수 있는 Azure 구독.
