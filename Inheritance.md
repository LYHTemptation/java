# 상속(Inheritance)

> 부모 클래스의 멤버를 자식 클래스에게 물려주는 것

1. 클래스를 재사용함으로써 코드의 중복을 막아준다.
2. 부모 클래스에서 private 접근 제한을 갖는 필드와 메소드는 상속 대상에서 제외된다.
3. 여러 개의 부모 클래스를 상속할 수 없다.
4. 자식 객체를 생성하면 부모 객체가 먼저 생성되고 자식 객체가 생성된다.

```java
// 부모클래스 = 상위 클래스
public class CellPhone {
	//필드
	String model;
	String color;
	
	//생성자
	
	//메소드
	void powerOn() { System.out.println("전원을 켭니다."); }	
	void powerOff() { System.out.println("전원을 끕니다."); }
	void bell() { System.out.println("벨이 울립니다."); }	
	void sendVoice(String message) { System.out.println("자기: " + message); }	
	void receiveVoice(String message) { System.out.println("상대방: " + message); }	
	void hangUp() { System.out.println("전화를 끊습니다."); }
}
```

```java
// 자식 클래스 = 하위 클래스
public class DmbCellPhone extends CellPhone {
	//필드
	int channel;
	
	//생성자
	DmbCellPhone(String model, String color, int channel) {
		this.model = model;
		this.color = color;
		this.channel = channel;
	}

	//메소드
	void turnOnDmb() {
		System.out.println("채널 " + channel + "번 DMB 방송 수신을 시작합니다.");
	}	
	void changeChannelDmb(int channel) {
		this.channel = channel;
		System.out.println("채널 " + channel + "번으로 바꿉니다.");
	}
	void turnOffDmb() {
		System.out.println("DMB 방송 수신을 멈춥니다.");
	}	
}
```

### 부모생성자

자식 생성자안에 부모 생성자 자동 호출 `super()`

super(매개값, ...) 매개값 넣을 수 있다.

반드시 자식 생성자 첫 줄에 위치해야 한다.

### 부모 메소드 호출(super)

자식 클래스 내부에서 오버라이딩된 부모 클래스의 메소드를 호출해야 할 때 super 키워드를 붙여 부모 메소드 호출 가능

```java
public class Airplane {
	public void land() {
		System.out.println("착륙합니다.");
	}	
	public void fly() {
		System.out.println("일반비행합니다.");
	}	
	public void takeOff() {
		System.out.println("이륙합니다.");
	}	
}
```

```java
public class SupersonicAirplane extends Airplane {
	public static final int NORMAL = 1;
	public static final int SUPERSONIC = 2;
	
	public int flyMode = NORMAL;
	
	@Override
	public void fly() {
		if(flyMode == SUPERSONIC) {
			System.out.println("초음속비행합니다.");			
		} else {
			//부모 클래스 fly()호출
			super.fly();
		}
	}
}
```

### final 클래스

상속할 수 없는 클래스

```java
public final class 클래스명{ ... }
```



### final 메소드

오버라이딩할 수 없는 메소드

```java
public class 클래스명{
	//final 메소드
    public funal void 함수명(){
        ...
    }
}
```









