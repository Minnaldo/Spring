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
        "products":{                      <br>
        "name":"진라면",                   <br>
        "price":"1000"                    <br>
    }                                     <br>
}                                         <br>
<br>
=========================================================================== <br>
## REST 특징 <br>
1. HTTP 프로토콜 기반 -> 웹표준을 최대한 활용 -> Stateless (클라이언트의 상태를 저장 x) <br>
2. 웹에 존재하는 모든 자원에 고유한 URI(통합자원식별자:Uniform Resource Identifier)를 부여해 활용 <br>
   (uri는 url의 상위 개념) <br>
   -HTTP GET(조회), POST(생성), PUT(수정), DELETE(삭제) <br>
3. "다양한 클라이언트"에게 서비스를 제공하고 클라이언트의 서버 역할의 명확한 분리가 가능. <br>
   모바일, 태블릿 등과 같은 다양한 디바이스 및 이기종(다른 기술언어로 구축)된 시스템에게 HTTP기반 서비스를 제공하기 위해 사용됨. 클라이언트는 REST API를 통해 서버와 정보를 주고 받는다. <br>
4. "서비스별 분리, 통합"에 대한 표준화된 방법을 제공 <br>
   어플리케이션의 복잡도가 증가 -> 서비스 별로 독립적으로 구축, 운영하는 것에 대한 필요성 대두 <br>
   ex) 고객정보서비스 | 예약서비스 | 항공편서비스 <br>
<br>
<br>
======================================================================================== <br>
## [REST API] <br>
### :REST 기반 서비스 API <br>
### 어플리케이션 간의 데이터 통신을 위한 <br>
<br>
>RESTful : REST API 제공하는 웹서비스 시스템을 지칭, "A 서비스 시스템은 'RESTful' 하다" <br>
>RestTemplate : Spring에서 제공하는 REST API Server와의 HTTP 통신을 위한 객체 서버와 서버간의 연동을 위해 사용된다. <br>
>Http Method : get, post, put, delete 을 지원하는 메서드를 제공한다.
 -getForEntity() <br>
 -postForObject() <br>
 -put() <br>
 -delete() <br>
======================================================================================== <br>
<br>
