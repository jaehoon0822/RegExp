# CH10 조건달기

> 정규표현식의 조건문이다. 책에서는 자주 쓰이지는 않다고 말한다.   
	표현식이 복잡해지기 때문이다.
>


### 왜 조건을 다는가?

> p98 을 보자.
>


### 조건 사용하기

> 정규표현식 조건은 ? 를 사용해 정의한다.
>

| 메타문자 | 설명 |
| :---: | :---: |
| (?(breakReference)true\|false) | (?)로 조건을 시작하고, 괄호안에 조건을 넣는다. 맞으면 ture를 실행한다. 아니라면 else 처럼 false 를 실행한다. |


> ***ex***:   
	(<[Aa]\s+[^>]+>\s*)?<([Ii][Mm][Gg]\s+[^>]+>(?(1)\s*</[Aa]>))   

	위에서 [] 안의 ^ 는 부정형으로, > 가 아닌 다른 문자들을 말한다.   
	문자열중 > 가 들어가면 그대로 <[Aa]> 가 되는 문자열이기 때문이다.
	즉 (1) = <[Aa]> 에서 \s 형 메타클래스문자가 1개 이상있고 > 가 아닌 문자들이 1개이상   
	있으며, 그다음 > 가오고, \s 형 메타클래스 문자가 0 개에서 1개 이상있는 문자열을 말한다.
>

> 위에서 (?(1)\s\*<[Aa]>) 에서 역참조를 했는데, 사실 역참조는 \1 로 표현했었다.   
	하지만 조건문안에서는 1 로 표현한다. 책에서는 \1 로 표현해도 된다고도 한다.
>

> ***ex***:   
	(\()?\d{3}(?(1)\)|-)\d{3}-\d{4}   
   
	보기 불편하다. 위의 핵심은 앞에 (\())? 이다. 가로가 많아서 뭐가 뭔지 헷갈리지만,
	(\()? 는 '(' 가 있는지 확인한다. 즉 하위표현식이라는 것이다.   
	그러므로 (?(1)\)|-) 의 1 은 (\())? 이며, '(' 가 있다면 ')' 를, 아니면 '-'  이다.
>


###  전후방탐색 조건 

> 전후방탐색이 성공했는지에 따라 조건분기한다.
>

> ***ex***:   
	\d{5}(?(?=-)-\d{4})   

	이것 역시 설명이 필요하다.   
	?=- 는 - 가 있으면, true 이다. 하지만 - 를 consume 하지 않는다.   
	그러므로, 그냥 true 로 계산된다. 이렇게 이해해도 되는지 참... 책이 얇아서 내용이   
	부실하네.. 애매하다. 그냥 일단 이렇게 이해한다.

	\- 가 있으면 -\d{4} 가 실행되고, 해당 조건문을 만족시키는 문자열을 찾는다.
> 




