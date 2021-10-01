# 오버로딩

* ### 생성자 오버로딩

  * 매개 변수를 달리하는 생성자를 여러 개 선언하는 것을 말한다.

  ```java
  public class Member {
  	private String name, address, phone;
  	private int age;
  	
  	public Member() {
  		
  	}
  	
  	public Member(String name, String address, String phone, int age) {
  		super();
  		setName(name);
  		setAddress(address);
  		setPhone(phone);
  		setAge(age);
  	}
  	
  	public String getName() {
  		return name;
  	}
  	public void setName(String name) {
  		this.name = name;
  	}
  	public String getAddress() {
  		return address;
  	}
  	public void setAddress(String address) {
  		this.address = address;
  	}
  	public String getPhone() {
  		return phone;
  	}
  	public void setPhone(String phone) {
  		this.phone = phone;
  	}
  	public int getAge() {
  		return age;
  	}
  	public void setAge(int age) {
  		this.age = age;
  	}
  }
  ```

  ```java
  //중복 코드 제거
  public class Test {
  
  	public static void main(String[] args) {
  		Member m1 = new Member("이윤호","성남","010-1111-2222",26);
  		Member m2 = new Member("이윤호","성남","010-4444-3333",26);
  		Member m3 = new Member();	
  	}
  
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

  