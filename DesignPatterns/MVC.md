# MVC 패턴
  - MVC란 Model-View-Controller의 약자로 애플리케이션을 세 가지 역할로 구분한 소프트웨어 디자인 패턴
  - 사용자 인터페이스로부터 비즈니스 로직을 분리하여 애플리케이션의 시작적 요소나 그 이면에서 실행되는 비즈니스 로직을 서로 영향 없이 쉽게 고칠 수 있는 애플리케이션을 만들 수 있음

<p align ="center">
  <img src="https://developer.mozilla.org/en-US/docs/Glossary/MVC/model-view-controller-light-blue.png" width = 800px height = 400px>
</p>


## 모델 (Model)
  - 어플리케이션이 포함해야할 데이터가 무엇인지를 정의함. 즉, 쉽게말해 데이터를 가지고 있는 객체
  - 모델의 상태에 변화가 있을 때 컨트롤러와 뷰에 이를 통보 (대부분 뷰) -> 이와 같은 통보를 통해 뷰는 최신의 결과를 보여줄 수 있고, 컨트롤러는 모델의 변화에 따른 적용 가능한 명령을 추가, 제거, 수정할 수 있음
  - 어떤 MVC 패턴에서는 모델이 통보하는 것 대신 뷰나 컨트롤러가 직접 모델의 상태를 읽어 오기도 함.
  - 규칙 
    - 사용자가 이용하려는 모든 데이터를 가지고 있어야 함.
    - 뷰나 컨트롤러에 대해서 어떠한 정보도 알지 말아야 함.
    - 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야 함.

## 뷰 (View)
  - 사용자에게 보여주는 화면(UI)이 해당됨.
  - 사용자와 상호작용 하며 컨트롤러로부터 받은 모델의 결과값을 사용자에게 화면으로 보여주는 일을 함.
  - MVC에서는 여러개의 View가 존재할 수 있음.
  - 규칙
    - 모델이 가지고 있는 정보를 따로 저장해서는 안됨
    - 모델이나 컨트롤러에 대한 정보를 알고 있으면 안되며 단순히 표시를 해주는 역할만을 해야함.
    - 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야 함

## 컨트롤러 (Controller)
  - 모델과 뷰 사이를 연결하는 역할. 즉, 모델이 데이터를 어떻게 처리할지 알려주는 역할을 함.
  - 사용자로부터 뷰에 요청이 있으면 컨트롤러는 해당 업무를 수행하는 모델을 호출하고 모델이 업무 수행을 마치면 다시 결과를 뷰에 전달함.
  - 규칙
    - 모델 또는 뷰에 대한 정보를 알고 있어야 함.
    - 모델 또는 뷰의 변경을 모니터링 해야 함.

## 장점
  - 기능별로 코드를 분리하여 하나의 파일에 코드가 모이는 것을 방지하여 가독성과 코드의 재사용성이 증가함.
  - 각 구성요소들을 독립시켜 협업을 할 때 맡은 부분의 개발에만 집중할 수 있어 개발의 효율성을 높여줌. -> 분업을 가능하게 해줌.
  - 비즈니스 로직과 UI로직이 분리되어 있어 유지보수를 독립적으로 수행가능함.
  - Model과 View가 다른 컴포넌트들에 종속되지 않아 애플리케이션의 확장성, 유연성에 유리함

## 단점
  - Model과 View는 서로의 정보를 갖고 있지 않는 독립적인 상태라고 하지만 Model과 View사이에는 Controller를 통해 소통을 이루기에 의존성이 완전히 분리될 수 없음.
  그래서 복잡한 대규모 프로그램의 경우 다수의 View와 Model이 Controller를 통해 연결되기 때문에 컨트롤러가 불필요하게 커지는 현상이 발생하기도 함.
  이러한 현상을 Massive-View-Controller 현상이라 함.
  
<p align ="center">
  <img src="https://imgopt.infoq.com/fit-in/1200x2400/filters:quality(80)/filters:no_upscale()/news/2014/05/facebook-mvc-flux/en/resources/flux-react-mvc.png" width = 800px height = 400px>
</p>

## Reference
https://velog.io/@2dubu/MVC-%ED%8C%A8%ED%84%B4
https://velog.io/@seongwon97/MVC-%ED%8C%A8%ED%84%B4%EC%9D%B4%EB%9E%80
https://ko.wikipedia.org/wiki/%EB%AA%A8%EB%8D%B8-%EB%B7%B0-%EC%BB%A8%ED%8A%B8%EB%A1%A4%EB%9F%AC
https://cocoon1787.tistory.com/733
https://ss-o.tistory.com/160
https://www.infoq.com/news/2014/05/facebook-mvc-flux/
https://developer.mozilla.org/ko/docs/Glossary/MVC
