<br>
<img src="./img/Spring_Sequence.PNG" width = 20%><br>**Spring 동작 과정**</img>
<br>
<br>
## 동작 순서 <br>
1. 클라이언트(사용자)의 모든 요청은 DispatcherServlet 이 받는다. <br>
2. DispatcherServlet은 handlerMapping을 통해서 요청에 해당하는 Controller를 실행. <br>
3. Controller는 적절한 서비스 객체를 호출시킨다. <br>
4. Service는 DB 처리를 위해 DAO를 이용하여 데이터를 요청한다. <br>
5. DAO는 mybatis를 이용하는 Mapper를 통해 작업 처리를 한다. <br>
6. 결과(처리한 데이터)가 mapper->DAO->Service->Controller로 전달된다. <br>
7. Controller는 전달된 결과(처리된 데이터)를 View Resolver를 통해 전달 받을 View가 있는지 검색한다. <br>
8. 전달 받은 View가 있다면 View에게 전달된 결과(처리된 데이터)를 전달한다. <br>
9. View는 전달 받은 결과(처리된 데이터)를 다시 DispatcherServle에게 전달한다. <br>
10. DispatcherServlet은 전달 받은 결과(처리된 데이터)를 클라이언트에게 전달한다. <br>
<br>
<br>
## 특징 <br>
- 고객이 대표전화로 전화를 걸면 상담원이 관련 부서로 연결해 주듯이 가장 먼저 전화를 받는 상담원이 DispatcherServlet 이다. <br>
- (DispatcherServlet의 등장은 web.xml의 역할을 상당히 축소시켜주었다. <br>
   기존에는 모든 서블릿에 대해 URL 매핑을 활용하기 위해서 web.xml에 모두 등록해주어야 했지만, DispatcherServlet이 해당 어플리케이션으로 들어오는 모든 요청을 핸들링해주면서 작업을 상당히 편리하게 할 수 있게 됨.) <br>
   <br>
- 클라이언트로부터 오는 모든 요청은 DispatcherServlet 을 거친다. <br>
  이때 DispatcherServlet 으로 들어온 요청은, Handler Mapper로 가서 각각의 요청 url을 key로 해서, 해당되는 value, 즉 등록된 url과 일치하는 컨트롤러를 찾는다. <br>
<br>
- 컨트롤러는 모델과 뷰를 이어주는 역할을 한다. 비즈니스 로직이 구현되어 있음. <br>
- 기존에는 컨트롤러 설정을 위해 xml을 사용했는데, 이제는 어노테이션으로 간편하게 설정 가능하다. <br>
- 각각의 컨트롤러에서 요청에 대한 처리를 한 후, 데이터를 뷰를 통해 사용자에게 제공한다. <br>
<br>
- 스프링 컨트롤러는 뷰에 의존적이지 않다. <br>
- 이유는 : 컨트롤러에서 로직 처리를 한 후, 뷰의 이름만 지정해주면 뷰 리졸버에서 뷰 객체를 생성한다. <br>
- 이렇게 생성한 뷰 객체를 통해 사용자는 원하는 데이터를 제공받을 수 있게 된다. <br>
<br>
<br>
## IoC(Inversion of Control) : 제어의 역전 <br>
