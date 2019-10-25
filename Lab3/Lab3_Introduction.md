---
lab:
    title: '랩 3 - AutoML 및 HyperDrive 사용'
    module: '모듈 3: Azure Machine Learning 서비스를 사용하여 기계 학습 자동화'
---

# 랩 3 - AutoML 및 HyperDrive 사용

## 랩 3.0: 목표

이 랩에서는 다음의 능력을 갖추게 됩니다.

- 기계 학습 파이프라인 이해
- Azure Machine Learning 서비스 AutoML 및 Hyperdrive 이해
- Azure Machine Learning 서비스의 AutoML을 사용하여 모델을 추천하는 Python 스크립트 만들기
- Python 스크립트에서 권장 되는 모델 테스트.



## 소개

이 랩에서는 이전에 수동으로 만든 모델보다 성능이 우수한 모델이 있는지 확인하려고 합니다. Azure Machine Learning 서비스의 AutoML 및 HyperDrive를 사용하여 여러 유형의 분류 모델을 동시에 실행하고 결과를 비교하며 가장 성능이 좋은 모델을 권장하려고 합니다. 이렇게 하면 최상의 모델을 선택하는 데 소모되는 많은 시간을 절약할 수 있으므로 솔루션을 더 빨리 전달할 수 있습니다. 

## 랩 3: 리소스

랩 폴더에서 다음 파일을 사용합니다.

이름                            | 설명
----                            | -----------
Starter_Lab3_Notebook.ipynb     | 사용해야 하는 랩 노트북입니다.  이를 노트북 프로젝트로 가져와서 엽니다. 


Azure Notebook 프로젝트 만들기 및 노트북 가져오기에 대한 도움말은https://docs.microsoft.com/ko-kr/azure/notebooks/quickstart-migrate-local-jupyter-notebook을 참조하십시오

Azure Notebook에 데이터를 업로드하는 방법에 대한 도움말은 https://docs.microsoft.com/ko-kr/azure/notebooks/work-with-project-data-files을 참조하십시오



## 전제 조건

이 실습을 수행하려면 다음이 필요합니다.
- 무료 Azure Notebook 서비스에 등록.  
- Azure Machine Learning 서비스 작업 영역을 프로비전할 수 있는 Azure 구독.
