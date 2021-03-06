# Dividend Yield가 Market Excess Return을 예측하는지에 대한 검증
- M. G. Gordon의 Dividend Growth Model을 기초로 하여 수행
- 지금 시점에서 다음날에 지급되는 배당을 D_t 라하면, g라는 일정한 성장률로 매기마다 성장한다고 가정한다면, 
  D_t  (1+g)의 비율로 배당은 성장할 것이고 이를 t-1시점에 현가로 할인을 한 가격은 다음과 같은 식으로 표현될 것임  
	P_(t−1)=D_t/(1+r)+(D_t (1+g))/〖(1+r)〗^2 + ∙ ∙ ∙ = (D_t/(1+r))/(1−(1+g)/(1+r))=D_t/(r−g)
- 이러한 무한한 배당 흐름의 현재가치가 가격이라고 한다면, 이 모형은 공비가 (1+g)/(1+r)  이고 초항이 D_t/(1+r) 인 무한 등비 급수가 되기 때문에 
  P_(t−1) 이 D_t/(r−g) 와 관련이 있다는 사실을 알 수 있음
- 위 식을 다시금 정리하면 다음과 같이 표현될 수 있기에, 이는 Dividend Price Ratio와 r의 값이 어느 정도 관련이 있다는 사실을 유추할 수 있음. 
  뿐만 아니라 D_t/P_(t−1)  이 r과 양의 방향으로 관련이 있을 것으로 사료됨
		
    r−g= D_t/P_(t−1) 
    
- 따라서 이 간단한 모형에서부터 마켓의 미래시점의 Access Return을 설명할 수 있는지를 확인하는 모형을 구현해보도록 하겠음
- t+1시점에 주식의 수익률을 나타내는 r_(mkt,t+1)−r_(f,t+1) 을 종속변수로 하고, D_t/P_(t−1)  를 독립변수로 하는 회귀식은 다음과 같이 표현할 수 있을 것임  
		R_(mkt,t+1)−R_(f,t+1)=α+β×(D_t/P_(t−1) )+ε_(t+1)

- 여기서 과거의 정보인 (D_t/P_(t−1) )로 t+1시점의 수익률을 예측하고자 한다면, (D_t/P_(t−1) )가 증가할 때 수익률이 양의 방향으로 예측된다면, β도 양의 방향으로 유의미한 값을 가질 것임. (반대로 β가 음의 방향으로 유의미하다면, (D_t/P_(t−1) )가 증가할 때 수익률은 감소할 것임)
- Dividend Price Ratio가 아무런 예측력을 가지지 않는다면, β값도 무의미한 값을 갖게 되어 설명력을 잃게 될 것임
		 		 
- 최종 결과 화면 및 해석
	n Coefficient는 양의 값으로 도출이 되었으나, β의 t-value는 1.585로 귀무가설을 β=0 기각할 수 없는 무의미한 수치가 도출되었음
	n 이는, 곧 “Dividend Ratio가 주가를 예측하는데 설명력이 없다”라는 것을 의미
