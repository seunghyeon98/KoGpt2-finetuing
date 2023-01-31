"# KoGpt2-finetuing" 

맛집 추천 사이트인 다이닝 코드(https://www.diningcode.com/)에서 음식점들의 리뷰를 크롤링하여 리뷰데이터를 수집하였고,
Kogpt2 모델을 fastai로 finetuning하였습니다.

리뷰데이터는 특수문자를 제거 하였으며, 
한국어 띄어쓰기 교정 모델인 quickspacer(https://github.com/cosmoquester/quickspacer) 라이브러리를 활용하여 리뷰데이터 특성상 띄어쓰기가 잘 이루어지지 않는 점을 고려하여 교정 하였습니다.

이후 kogpt2를 통해 생성된 문장은 네이버에서 배포한 hanspell(https://github.com/ssut/py-hanspell)를 통하여 맞춤법과 띄어쓰기를 교정한후 생성문장을 다듬었습니다.

목표는 가짜리뷰를 생성하는 것이 목표였으나,
생성된 문장을 확인하였을 때 다른 업종의 음식이름이 언급되는가 하며, 생성된 문장들이 종결 어미로 끝나지 않는 다는 점이 있었고
가장 아쉬운점은 생성된 문장이 전체적으로 부자연(?) 스러운 느낌이 많이 나는 것 같습니다.

## Ref)
### fastai를 통해 kogpt2 finetuning하는 법
https://velog.io/@yeah7598/KoGPT2-%EB%8F%99%ED%99%94-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%95%99%EC%8A%B5%ED%95%98%EA%B8%B0

https://github.com/ttop32/KoGPT2novel/blob/main/train.ipynb

### fastai 학습률에 관해서 
https://github.com/jehyunlee/texts/blob/master/estimating_an_optimal_learning_rate_for_a_deep_neural_network/text.md

