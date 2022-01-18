# [REST API] (REST, REST API 개념) / 예제 소스 (SpringBoot)
<br>
<img src="./img/RestAPI.PNG" width = 20%><br>**RestAPI**</img>
<br>
## [REST (Representational State Transfer)]
  : "분산 시스템"을 위한 HTTP 기반 소프트웨어 아키텍쳐 <br>
  
  ### "즉, 웹 어플리케이션, 다양한 언어, 모바일 어플리케이션, 다른 서버 (모두 HTTP 기반) 등 끼리 서로 통신할 수 있도록, 통역 역할을 해주는 API <br>
  ### 참고) 분산시스템 : 하나의 시스템으로 보이는 독립된 컴퓨터들의 집합 -> 이를 위해 네트워크를 통한 컴퓨터 간의 통신이 필요
<br>
<br>
## REST 구성 3가지 : 자원, 행위, 메시지
1. 자원(resource) : 접근할 대상 <br>
2. 메서드(method) : HTTP Method - GET(조회), POST(생성), PUT(수정), DELETE(삭제) <br>
  "일반적으로는 GET, POST 방식을 사용하나, REST엥서는 PUT, DELETE도 사용한다. <br>
3. 메시지
<br>
<br>

ex) "상품명이 진라면인 상품을 생성한다" 라는 호출이 있을 때, <br>
"상품" 은 생성되는 자원(Resource) <br>
"생성한다" 라는 행위는 메서드(post) <br>
"상품명이 진라면인 상품"은 메시지 ({"name":"진라면","price":"1000"}) <br>
<br>
-이를 REST 형태로 표현하면 다음과 같다. <br>
<br>
HTTP POST, http://localhost/products/{    <br>
    "products":{                          <br>
        "name":"진라면",                   <br>
        "price":"1000"                    <br>
    }                                     <br>
}                                         <br>

<br>
