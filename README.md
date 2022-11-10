[![Python](https://img.shields.io/badge/Python-Used-blue.svg)](https://shields.io/#/)

# KoG2Padvanced

KoG2Padvanced는 파이썬 기반의 한국어 발음 변환기 [KoG2P](https://github.com/scarletcho/KoG2P)를 기반으로 KoG2P에서 반영하지 못하는 음운론적 규칙을 추가함으로써 성능을 보다 높인 모델로써, <strong>이 연구는 2019년 정부(미래창조과학부)의 재원으로 정보통신기술진흥센터의 지원을 받아 수행된 연구입니다(2019-0-01371,Development of brain-inspired AI with human-like intelligence)</strong>. 본 모델에서 추가로 반영한 음운론적 규칙은 다음과 같습니다.

#### ㅎ탈락(/h/-deletion): - 강옥미(2003: 515) 한국어 음운론, 표준발음법 제12항 
- 제12항-2: ‘ㅎ(ㄶ, ㅀ)’ 뒤에 ‘ㅅ’이 결합되는 경우에는, ‘ㅅ’을 [ㅆ]으로 발음한다.
- 제12항-3: ‘ㅎ’ 뒤에 ‘ㄴ’이 결합되는 경우에는, [ㄴ]으로 발음한다.
- 제12항-4: ‘ㅎ(ㄶ, ㅀ)’ 뒤에 모음으로 시작된 어미나 접미사가 결합되는 경우에는, ‘ㅎ’을 발음하지 않는다.
- ㅎ탈락의 경우 용언에서는 필수적으로 탈락하나 명사에서는 수의적으로 탈락한다 

#### '의'처리: 한글맞춤법 제9항, 표준발음법 제5항 
- 자음으로 시작하는 'ㅢ'는 'ㅣ'로도 발음한다.
- 첫음의 '의'를 제외하고 모두 'ㅣ'로도 발음한다.
- 부사격 조사 '의'는 '에'로도 발음한다: ex) 민주주의의 의의[민주주이에 의이]

#### 자음 위치 동화(Place Assimilation) - 박선우. (2008)
- ㄴ, ㄷ → ㅁ, ㅂ / ____{ㅁ, ㅂ, ㅍ, ㅃ} (치경음 → 양순음)
- 옷보다[옫뽀다] -> 옵뽀다 (cf. 오뽀다) / 준비[준비]～[줌비]
- ㄴ, ㄷ → ㅇ, ㄱ / ____ {ㄱ, ㅋ, ㄲ} (치경음 → 연구개음)
- 숟가락[숟까락] -> 숙까락 (cf. 수까락) / 모든 걸[모든걸]～[모등걸]
- ㅁ, ㅂ → ㅇ, ㄱ / ____{ㄱ, ㅋ, ㄲ} (양순음 → 연구개음)
- 숲길[숩낄] -> 숙낄 (cf. 수낄) / 짐꾼[짐꾼]～[징꾼]

#### 자음 뒤 ‘ㅖ’처리: 한글맞춤법 제8항, 표준발음법 제5항
- 표준발음법 제5항-다만 2: ‘예, 례’이외의 ‘ㅖ’는 [ㅔ]로도 발음한다. 


## Requirements
해당 소프트웨어를 사용하고자 하시는 분들은 다음의 파이썬 기반 패키지들을 우선적으로 설치해주셔야 합니다.

* python >= 3.6
* jamo
* konlpy


## Installation
소프트웨어가 공개되어 있는 github링크를 복제하여 사용하시면 됩니다.

```
git clone https://github.com/seongmin-mun/KoG2Padvanced.git
```


## How to use
해당 소프트웨어에 대한 사용법은 아래와 같습니다.

```
>>> from G2P.KoG2Padvanced import KoG2Padvanced
>>> InputText = "가을이 되니 무성했던 꽃잎들이 땅으로 우수수 떨어지는구나."
>>> print(KoG2Padvanced(InputText))
가으리 되니 무성앧떤 꼰닙뜨리 땅으로 우수수 떠러지능구나
```


## Reference
해당 소프트웨어를 연구에 활용하고자 하시는 분들은 다음의 형식으로 참고문헌에 작성해 주시면 감사하겠습니다.

	@misc{Mun2022KoG2Padvanced,
	  title = {KoG2Padvanced},
	  author = {Seongmin Mun},
	  year = {2022},
	  publisher = {GitHub},
	  journal = {GitHub repository},
	  howpublished = {\url{https://github.com/seongmin-mun/KoG2Padvanced}}
	}
