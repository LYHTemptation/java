# 오버로딩

* ### 생성자 오버로딩

  * 매개 변수를 달리하는 생성자를 여러 개 선언하는 것을 말한다.

  ```java
  public class car{
      String company, model, color;
      int maxSpeed;
      //생성자
     Car(){
     }
     Car(String model){
         this.model = model;
     }
     Car(String model, String color){
         this.model = model;
         this.color = color;
     }
     Car(String model, String color, int maxSpeed){
         this.model = model;
         this.color = color;
         this.maxSpeed = maxSpeed;
     }
  }
  ```

  ```java
  //중복 코드 제거
  Car(String model){
      this(model,'은색',250); //제일 마지막 생성자 호출
  }
  Car(String model, String color){
      this(model,color,250); //제일 마지막 생성자 호출
  }
  Car(String model, String color, int maxSpeed){
      this.model = model;
      this.color = color;
      this.maxSpeed = maxSpeed;
  }
  ```

* ### 메소드 오버로딩

  * 조건의 매개 변수의 타입, 개수, 순서를 달리하여 여러개 선언하는 것을 말한다.

  ```java
  public class Calculator{
  	//정사각형의 넓이
      double areaRectangle(double width){
          return width*width;
      }
  	//직사각형의 넓이
      double areaRectangle(double width, double height){
          return width*height;
      }
  }
  ```

  