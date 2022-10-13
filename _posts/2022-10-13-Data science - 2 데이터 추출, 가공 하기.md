---
title : Data science - 2 데이터 추출, 가공 하기
date : 2022-10-13 23:43:00 +09:00
categories : [Data Science]
tags : [Data Science, Data, csv]
---

> 위 글을 Google Cloab으로 진행됩니다. Colab의 기본적인 사용방법을 알고있으며, 파이썬 기초 지식을 알고 있으면 이 글을 보시는데 아무 지장도 없습니다.

> 포스트 내의 데이터는 위 링크에서 다운받으실수 있습니다. https://data.seoul.go.kr/dataList/OA-15968/S/1/datasetView.do
> 
> csv파일은 위 데이터에 50열만 추출했습니다.

## CSV 파일 업로드

이제부터 가지고 놀(?) **csv**파일을 **colab으로 불러오는**데에는 2가지 방법이 있습니다.

### 프로그래밍으로 불러오기

```python
from google.colab import files
import pandas as pd
uploaded = files.upload()
df = pd.read_csv('파일이름.csv', encoding='euc-kr')
```

Google Colab에서 제공하는 파일 업로드 모듈을 불러온 후 `files.upload()`로 파일을 볼러올수 있게 코드를 작성합니다.

코드를 실행시키면 다음과 같이 **[파일선택]** 버튼이 표시됩니다. **업로드할 파일을 선택해서 파일을 업로드** 합니다.

![Google Colab](https://user-images.githubusercontent.com/72495729/195628624-87f4e8de-1653-4605-a4c6-f5c23ab6464c.png)

### Colab 로컬 파일 가져오기

다음 코드는 **Pandas** 모듈을 사용해 **CSV** 파일을 불러오는 코드입니다.

```python
import pandas as pd
df = pd.read_csv('/content/data.csv', encoding='euc-kr')
```

1. **pandas** 모듈을 **pd**라는 별명을 사용해서 불러옵니다.
  
2. **pandas** 모듈에 내장되어있는 read_csv() 함수를 이용해 `content` 파일 내에 있는 `data.csv` 파일을 불러온후 `df` 변수에 저장합니다. 단, **csv파일 안에 한국어가 있을경우** 불러오는중에 한국어가 깨질수도 있기때문에 encoding 속성을 `utf-8` 혹은 `euc-kr` 로 설정해줍니다.
  

## CSV 파일 출력하기

csv안에 데이터들을 간단하게 확인하기 위해 `head()`라는 함수가 있습니다,

기본적으로 **csv파일 내에 첫행 부터 5행 까지 표시**됩니다.

또한, df.head(10)이라고 하면 10행까지 데이터가 보여집니다.

```python
df.head()
```

![Google Colab](https://user-images.githubusercontent.com/72495729/195628641-51afc3fd-0cc6-4c6c-a05b-3e38ef6f896d.png)

## CSV 특정 컬럼데이터 추출하기

csv파일중 `습도(%)` 컬럼만 추출하고 싶을땐

```python
df2 = df['습도(%)']
df2.head()
```

혹은,

```python
df['습도(%)'].head()
```

로 `습도(%)` 컬럼 데이터만 불러올수 있습니다.

#### 2개 이상 컬럼 데이터 추출하기

`습도(%)`와 `이산화탄소(ppm)` 컬럼을 **동시에 출력**하고 싶으면 아래 처럼 리스트 형태로 만들면 됩니다.

```python
df[['습도(%)', '이산화탄소(ppm)']].head()
```