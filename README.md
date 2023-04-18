# 2023-1_Android

> # 메소드 오버로딩은 가져가다 쓰는 것이고, 메소드 오버라이딩은 가져다가 !덮어쓰는것!
# 메소드 오버로딩(Method Overloading)
     • 매개변수의 개수와 타입은 다르지만 이름이 같은 메소드를 여러개 개 정의하는 것
     • 메소드의 기능은 같지만 매개변수의 개수와 타입이 다를 때 효율적으로 사용이 가능
     • 소드의 이름을 동일한 이름으로 부여하여 메소드를 정의할 수 있도록
     • 문법적으로 허용하게 되는데
     • 이를 메소드 오버로딩(Method Overloading)이라고 한다.
     
## 메소드 오버로딩의 예
	• 가장 대표적인 것은 println 이다.
	• 매개변수로 지정하는 값의 타입에 따라서 호출되는 println 메서드가 달라진다.

 ## 메소드 오버라이딩의 장점
	• 하나의 이름으로만 기억하면 되므로 기억하기도 쉽고 이름도 짧게 할 수 있어서 오류의 가능성을 많이 줄일 수 있다.
	• 메서드의 이름만 보고 이름이 같으니, 같은 기능을 하겠구나라고 쉽게 예측할 수 있게 된다.
	• 메서드의 이름을 절약할 수 있다.


<img width="500" alt="image" src="https://user-images.githubusercontent.com/83889135/232644271-35408bd5-ccdc-44f7-9b26-b72390bc16e9.png">

<hr>

# 메소드 오버라이딩(Method Overriding)
## 메소드 오버라이딩 정의
    • 상위 클래스(부모 클래스)를 상속받은 하위 클래스(자식 클래스)에서
      상위 클래스에 정의된 메소드를 다시 정의하는 것으로(재정의)
      객체 지향 프로그래밍의 특징인 다형성을 나타낸다.
    • 재정의(Overriding)는 반드시 상속 관계에 있어야 하며,
      메소드의 이름, 리턴타입, 매개변수의 갯수나 타입이 완전히 일치해야 한다.
    • 『static』,『final』,『private』 메소드는 오버라이딩(Overriding)할 수 없다.
 
## 메소드 오버라이딩의 장점
    • 비슷한 형태의 메소드를 다시 작성하지 않아 효율성 향상
    • 상속으로 인해 코드의 재사용성 향상
    • 비슷하지만 다른 형태의 재정의가 가능해 다향성 확립

 ```java
  // ex) Bus 클래스는 부모클래스인 Car 클래스를 상속 받고 있다.
  // Car클래스 (부모 클래스)
    public class Car{
        public void run(){
            System.out.println("Car의 run메소드");
        }
    }
 
    // Bus 클래스 (자식 클래스)
    public class Bus extends Car{
 
    }
 
    public class BusExam{
        public static void main(String args[]){
            Bus bus = new Bus();
            bus.run();  //Car의 run메소드가 실행된다. 
        }
    }
 ```
 
  ```java
  // Bus클래스는 부모클래스인 Car 클래스의 모양이 같은 메소드를 선언
    public class Bus extends Car{
        public void run(){
            System.out.println("Bus의 run메소드");
        }
    }
 
    public class BusExam{
        public static void main(String args[]){
            Bus bus = new Bus();
            bus.run();  //Bus run메소드가 실행된다. 
        }
    }
 ```
 
 ``` java
     /* BusExam을 실행하면 Bus클래스의 run메소드가 출력된다.
        메소드를 오버라이드 하면, 항상 자식클래스에서 정의된 메소드가 호출된다.
        오버라이딩 한다고 해서 부모의 메소드가 사라지는 것은 아니다.
            super 키워드를 이용하면, 부모의 메소드를 호출 할 수 있다.
     */
     public class Bus extends Car{
        public void run(){
            super.run();  // 부모의  run()메소드를 호출
        }
    }
 ```

<hr>

## 4장 버튼과 에디트텍스트 (+ 소스코드)
    버튼을 클릭햇을 때 동작하는 Java 코드 3단계
   
<img width="500" alt="스크린샷 2023-04-18 오전 10 25 18" src="https://user-images.githubusercontent.com/83889135/232645384-fc95193f-c478-4a2d-bcff-8c96af702fb8.png">

<hr>

## 5장 레이아웃의 종류 + 특징 + 성격 + 속성
<img width="500" alt="스크린샷 2023-04-18 오전 10 30 59" src="https://user-images.githubusercontent.com/83889135/232646183-61477965-683a-4508-b71b-15fef11e99ad.png">
<img width="500" alt="스크린샷 2023-04-18 오전 10 31 19" src="https://user-images.githubusercontent.com/83889135/232646234-992ea43e-6979-4638-a1a2-99bff090c06f.png">
<img width="500" alt="스크린샷 2023-04-18 오전 10 31 25" src="https://user-images.githubusercontent.com/83889135/232646248-e86cf965-d891-4306-9dbf-d5ac4e08f37d.png">
<img width="500" alt="스크린샷 2023-04-18 오전 10 31 58" src="https://user-images.githubusercontent.com/83889135/232646334-91538829-01fc-4eba-b48c-5bd37622ed6c.png">

<hr>

## 예제 7.5.txt
```java
  public class MainActivity extends AppCompatActivity {

	LinearLayout baseLayout;
	Button button1;

	@Override
	public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);
		setTitle("배경색 바꾸기");

		baseLayout = (LinearLayout) findViewById(R.id.baseLayout);
		button1 = (Button) findViewById(R.id.button1);
	}

	@Override
	public boolean onCreateOptionsMenu(Menu menu) {
		
		super.onCreateOptionsMenu(menu);
		MenuInflater mInflater = getMenuInflater();
		mInflater.inflate(R.menu.menu1, menu);
		return true;
	}

	@Override
	public boolean onOptionsItemSelected(MenuItem item) {
		switch (item.getItemId()) {
		case R.id.itemRed:
			baseLayout.setBackgroundColor(Color.RED);
			return true;
		case R.id.itemGreen:
			baseLayout.setBackgroundColor(Color.GREEN);
			return true;
		case R.id.itemBlue:
			baseLayout.setBackgroundColor(Color.BLUE);
			return true;
		case R.id.subRotate:
			button1.setRotation(45);
			return true;
		case R.id.subSize:
			button1.setScaleX(2);
			return true;
		}
		return false;
	}

}
```

<hr>

# 안드로이드 앱 매니페스트 개요  AndroidManifest.xml
<img width="500" alt="스크린샷 2023-04-18 오후 12 27 01" src="https://user-images.githubusercontent.com/83889135/232663375-16642bc1-678b-4e08-a729-6d2353dd4504.png">

	매니페스트 파일에는 많은 정보를 담을 수 있지만 그중에서도 특히 선언되어야 하는 정보가 있습니다.
		• 앱의 패키지 이름
		• 앱에서 사용되는 컴포넌트(액티비티, 서비스, 브로드캐스트 리시버, 컨텐트 프로바이더)
		• 권한(Permission)
		• 앱에서 요구하는 하드웨어와 소프트웨어 특징

<hr>

# 인의예지신 중도
 <img width="500" alt="스크린샷 2023-04-18 오전 11 13 23" src="https://user-images.githubusercontent.com/83889135/232652251-211d7743-b1ee-4bfb-a813-5b0e18b93704.png">
