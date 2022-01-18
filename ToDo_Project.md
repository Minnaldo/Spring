
* @RestController - "이 클래스는 RESTful API를 위한 컨트롤러 클래스이다" 라고 스프링에게 알려줌. <br>
* @RequestMapping - 구체적으로 어떤 경로인지 지정해준다. <br>
* @RequestMapping - 어떤 REST 메서드를 사용할 것인지, 어떤 경로인지, 또는 pathVariable을 받는 경우, pathvariable의 이름을 지정해 줄 수 있다. <br>
* @PathVariable - 어떤 PathVariable이 어느 변수에 맵핑되어야 하는지 알려준다. <br>
                  "/{id}" -> value="id" 얘가 Integer id에 맵핑된다. <br>
* @ResponseBody - 이 메서드는 HTTP Resonse Body 부분을 JSON의 형태로 리턴할 것임을 알려준다. <br>
* @Getter, @Setter - Lombok 어노테이션 <br>
<br>
: 우리는 RESTful API를 만들 것이므로 @RestController 어노테이션을 이용해 이 컨트롤러가 RESTful API인 스프링 부트에게 알려주도록 한다. <br>
  또한 @RequestMapping 어노테이션을 이용해 이 컨트롤러의 URL을 정해준다. <br>
  RequestMapping은 위처럼 클래스 위에 하나, 메서드 위에 하나 정의할 수 있는데, 이 클래스 안의 모든 메서드들은 클래스의 RequestMapping을 공유한다. 따라서 http://localhost:8080/todo/{id}/ 를 보면 '/todo'는 클래스 위에 '/{id}'는 메서드 레벨에 정의 된 것을 확인 할 수 있다. <br>
  이 컨트롤러는 ToDoItemService를 사용하므로 이를 추가해줬다. @Getter, @Setter가 알아서 getter, setter를 만들어 준다. <br>
  @RequestMapping에 method = RequestMethod.GET이 보이는가? 바로 이 부분에서 우리는 RESTful API의 네가지 Method 중 어떤 것을 이용할 지 선택하는 것이다. 우리는 GET을 이용할 것이므로 GET으로 선택하고 value에는 /{id}를 넣었다. 이 id느 ㄴ아래의 @PathVariable의 value 값과 같은 값이어야 한다. <br>
  <br>
  이 때, 우리는 ToDoItem을 ToDoItemResponse로 바꿔주어야 하는데, 그 작업을 해주는게 바로 ToDoItemAdapter 이다. <br>
  
