# Static

> 정적(static)은 고정된이란 의미를 가지고 있다.
>
> 정적 멤버는 고정된 멤버로서 객체를 생성하지 않고 사용할 수 있는 필드와 메소드를 말한다.
>
> 각각 정적 필드, 정적 메소드라고 부른다.

```java
public class Calculator{
    static double pi = 3.14159;
    static int plus(int x, int y){
        return x+y
    }
}
```

```java
public class CalculatorExample{
    public static void main(String[] args){
        double result = 10*10*Calculator.pi;
        int result2 = Calculator.plus;
    }
}
```

정적 필드는 선언과 동시에 초기값을 주는 것이 보통이다.

자바는 정적 필드의 복잡한 초기화 작업을 위해서 `정적 블록(static block)`을 제공한다.

정적 블록 내부에서 인스턴스 필드나 인스턴스 메소드를 사용할 수 없다. this 키워드 역시 쓸 수 없다.

```java
public class ClasName{
    int field1;
    void method1(){...};
    static int field2;
    static void method2(){...};
    //정적블록
    static{
        field1=10; //컴파일에러
        method1(); //컴파일에러
        field2=20;
        method2();
    }
}
```



___



# final

> 초기값이 저장되면 최종적인 값이 되어서 프로그램 실행 도중에 수정을 할 수 없다.
>
> 초기화되지 않으면 컴파일 에러가 발생한다.

1. 필드 선언 시에 주는 방법
2. 생성자에서 주는 방법

```java
public class Person{
    final String natiom = "대한민국";
    final String ssn;
    String name;
    public Person(String ssn, String name){
        this.ssn = ssn;
        this.name = name;
    }
}
```

___



# 상수

>불변의 값을 상수라고 부른다.
>
>변하지 않고 공용성을 지니고 있는 값을 말한다.
>
>정적 블록 사용 가능하다.

```java
static final 타입 상수명 = 초기값;
```



