---
lab:
    title: '랩 1 - Azure Notebook에서 모델 학습'
    module: '모듈 1: Azure에서 데이터 과학 수행'
---

# 랩 1 - Azure Notebook에서 모델 학습

## 랩 1.0: 목표

이 랩에서는 다음의 능력을 갖추게 됩니다.

- Python과 함께 Azure Notebook을 사용하여 클라우드 기반 Jupyter Notebook 서비스 수행. 
- 탐색적 데이터 분석 수행
- 기계 학습 모델 기능 만들기
- 오픈 소스 기반 분류 예측 모델을 학습.

이 랩의 주요 목표는 학생들이 Adventure Works 사용 사례를 시작하면서 Azure Notebooks을 사용하여 속도를 높이는 것입니다.

## 소개

Python과 오픈 소스 패키지 scikit-learn을 사용하여 Azure Notebook에서 분류 모델을 학습할 것입니다. 그 일환으로 데이터를 이해하기 위해 몇 가지 기본 탐색적 데이터 분석을 수행해야 합니다.  그런 다음 모델 학습에 사용할 피기능을 작성해야 합니다. 마지막으로 모델을 학습하고 평가합니다. 참고:  이 시점에서 Azure 서비스를 사용하지 않습니다. 

팀의 데이터 엔지니어는 필요한 모든 데이터가 있는 CSV 형식의 데이터 추출 파일을 제공했습니다.  스타터 랩 노트북에서 이 랩에서 수행해야 하는 작업을 안내합니다. 



## 랩 1: 리소스

랩 폴더에서 다음 파일을 사용합니다.

이름                            | 설명
----                            | -----------
Starter_Lab1_Notebook.ipynb     | 사용해야 하는 랩 노트북입니다.  이를 노트북 프로젝트로 가져와 서 엽니다. 
AWData.csv                      | Adventure Works 데이터 추출 파일. 이 파일을 Azure Notebook 프로젝트에 업로드합니다. 

Azure Notebook 프로젝트 만들기 및 노트북 가져오기에 대한 도움말은 https://docs.microsoft.com/ko-kr/azure/notebooks/quickstart-migrate-local-jupyter-notebook을 참조하십시오

Azure Notebook에 데이터를 업로드하는 방법에 대한 도움말은 https://docs.microsoft.com/ko-kr/azure/notebooks/work-with-project-data-files을 참조하십시오.



## 전제 조건

이 실습을 수행하려면 다음이 필요합니다.
- 무료 Azure Notebook  서비스에 등록  
