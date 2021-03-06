# 객체 지향 프로그래밍

객체 지향 프로그래밍 **OOP**(Object Oriented Programming)

**객체**란  물리적으로 존재하거나 추상적으로 생각할 수 있는 것 중에서 자신의 속성을 가지고 있고 다른 것과 식별 가능한 것을 말한다.

현실 세계의 객체를 소프트웨어 객체로 설계한느 것을 **객체 모델링**이라고 한다.

## 특징

* 캡슐화(Encapsulation) - 객체의 필드, 메소드를 하나로 묶고 실제 구현 내용을 감추는 것
* 상속(Inheritance) - 상위 객체를 하위 객체가 재사용 할 수 있게끔 해주는 것
* 다형성(Polymorphism) - 같은 타입이지만 실행 결과가 다양한 객체를 이용할 수 있는 성질

## 클래스 선언

클래스에는 객체를 생성하기 위한 필드와 메소드가 정의되어 있다.

| 번호 | 작성 규칙                           | 예               |
| ---- | ----------------------------------- | ---------------- |
| 1    | 하나 이상의 문자로 이루어져야 한다. | Car, SporrtsCar  |
| 2    | 첫 번째 글자는 숫자가 올 수 없다.   | 3Car(x)          |
| 3    | $,_외의 특수 문자는 사용할 수 없다. | @Car(x), #Car(x) |
| 4    | 자바 키워드는 사용할 수 없다.       | int(x), for(x)   |

```java
public class 클래스이름{
    
}
```

## 클래스 생성

```java
클래스 변수 = new 클래스();
```

new 연산자로 객체를 생성하고 리턴된 객체의 주소를 변수에 저장하면 변수가 객체를 참조하게 된다.

## 클래스의 구성 멤버

```java
public class ClassName{
    //필드
    int fildName;
    
    //생성자
    ClassName(){
        ...
    }
    
    //메소드
    void methodName(){
        ...
    }
}
```

**필드** 

* 객체의 고유 데이터, 상태 정보를 저장하는 곳, 선언 형태는 변수와 비슷하지만 필드를 변수라고 부르지 않는다.

* 클래스  중괄호{} 어디서든 존재할 수 있다. 

* 중괄호 블록 내부에 선언된 것은 모두 로컬 변수가 된다

* ```java
  //기본타입(byte,short,int,long,float,double,booleadn), 참조타입(배열,클래스,인터페이스) 가능
  타입 필드 { = 초기값; }
  ```

* 초기값이 지정되지 않을 경우 기본 초기값으로 설정

* 도트(.) 연산자를 사용해서 필드에 접근 가능

**생성자**  

* 생성자는 new 연산자로 호출되는 특별환 중괄호 블록이다.

* 객체 생성 시 초기화를 담당한다.

* 필드를 초기화하거나 메소드를 호출해서 객체를 사용할 준비를 한다.

* 메소드와 비슷하게 생겼지만, 클래스 이름으로 되어 있고 리턴 타입이 없다.

* new 연산자에 의해 생성자가 성공적으로 실행되면 힙(heap) 영역에 객체가 생성되고 객체의 주소가 리턴 된다.

* 클래스 내부에 생성자 선언을 생략했다면 기본생성자(Default Constructor)를 자동 추가시킨다.

  ```java
  public class Car{
      public Car(){ } //자동추가(기본생성자)
  }
  ```

* ```java
  public class Korean{
      String nation="대한민국";
      String name;
      String number;
      //생성자
      public Korean(String n, String s){
          name = n;
          number = s;
      }
  }
  ```

* this를 이용해 내부 필드에 접근할 수 있다.

**메소드**

* 객체 간의 데이터 전달의 수단

* 외부로부터 매개값을 받을 수도 있고 실행 후 어떤 값을 리턴할 수도 있다.

* 리턴값이 있을 수도 있고 없을 수도 있다.

  ```java
  void powerOn{...}
  double divide(int x, int y){...}
  
  powerOn();
  divide(10, 20);
  ```

* 매개 변수의 수를 모를 경우 `배열 타입`으로 선언할 수 있다.

* 객체 내부, 외부에서 메소드 호출이 가능하다

  ```java
  public class Calculator{
      int plus(int x,int y){
          int result = x+y;
          return result;
      }
      double avg(int x, int y){
          double sum = plus(x,y);
          double result = sum/2;
          return result;
      }
      //내부호출
      void execute(){
          double result = avg(7,10);
          println("실행결과" + result);
      }
      void println(String message){
          System.out.println(message);
      }
  }
  //외부호출
  Calculator C = new Calculator();
  C.execute();
  ```

* 