# CH4. 메타 문자 사용하기


> 메타 문자는 그 앞에 역슬래시를 붙여 문자 그대로 해석( 이스케이프 )되게 할수 있다.
>


### 정규 표현식 문법 메타문자
---

> ' [ ' , ' ] ' , ' \\ ' , ' . '  
>


### 텍스트와 일치하는 문자
---

> 텍스트의 메타 문자이다.
>


| 메타 | 내용 |
| :--- | :---: |
| [\b] | 역스페이스 |
| \f | 페이지 넘김( form feed ) |
| \n | 캐리지 리턴 |
| \t | 탭 |
| \v | 수직 탭 |


> 윈도우에서는 \r\n 을 쓰고 리눅스에서는 \n 을 사용한다.
그러므로, \n 을 쓰면서 필요할때 \r 을 쓸수 있도록 하는게 좋다.
>

> \r, \n, \t 을 가장 많이 쓴다.


### 특정한 문자 형태와 일치시키기
---


> 문자 집합의 모음을 문자 클래스라 한다.
>



| 메타 | 내용  |
| :--- | :---: |
| \d | [ 0-9 ] |
| \D | [ ^0-9 ] |
| \w | [ a-zA-Z0-9\_ ] |
| \W | [ ^a-zA-Z0-9\_ ] |
| \s | [ \f\n\r\t\v ] |
| \s | [ ^\f\n\r\t\v ] |



### POSIX 문자 클래스
---


| 문자 클래스 | 내용 |
| :--- | :---: |
| [:alnum:] | [ a-zA-Z0-9 ] |
| [:alpha:] | [ a-zA-Z ] |
| [:black:] | [ \t \|\| space ] |
| [:cntrl:] | [ 0-31 || 127 ] |
| [:digit:] | [ 0-9 ] |
| [:graph:] | [ :print: ] 와 같지만 ^space |
| [:lower:] | [ a-z ] |
| [:print:] | [ 출력가능한 모든 문자] |
| [:space:] | [ \f\n\r\t\v ] |
| [:upper:] | [ A-Z ] |
| [:xdigit:] | 16진수 [ a-fA-F0-9 ] |



> javascirpt 에서는 미지원
>


> POSIX 문자 클래스는 사용시 대괄호 포함한다. 집합 안에 문자클래스를 넣는 방식이다. -> [[:alnum:]] 
>






