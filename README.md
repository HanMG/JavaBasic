# JavaBasic
Inflearn - JavaProgramming Basic Course (renew ver.) 무료기념 호다닥 복습,정리

목차 
====

[1강 - 자바 공부를 위한 준비, Hello World](#1강---jdk-eclipse-설치-hello-java-world-project-생성)

[2강 - 환경변수 설정, 자바 프로그램의 실행 구조, Garbage collector](#2강---환경변수-설정-자바-프로그램의-실행-구조-garbage-collector)

[3강 - 변수](#3강---변수)

[4강 - 기본자료형(Primitive Type)](#4강---기본자료형primitive-type) 

[5강 - 특수문자와 서식](#5강---특수문자와-서식)

[6강 - 연산자](#6강---연산자)

[7강 - 배열](#7강---배열)

[8강 - 배열과 메모리](#8강---배열과-메모리)

[9강 - 조건문](#9강---조건문)

[10강 - 반복문](#10강---반복문)


1강 - JDK, Eclipse 설치, Hello JAVA World Project 생성
-----------------

[Oracle JDK](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)

[Eclipse Download](https://www.eclipse.org/downloads/packages/)</br>

![HelloJava](https://user-images.githubusercontent.com/22463540/75841901-3a5fca80-5e12-11ea-9515-038bfe8172bb.png)

2강 - 환경변수 설정, 자바 프로그램의 실행 구조, Garbage collector
------------------

#### 2-1 환경변수 설정 
`````````````````````
javac.exe, java.exe를 다른 디렉토리에서도 실행할 수 있도록 하기 위해 환경 변수(Path)에 bin 경로를 등록
java.exe - JVM 구동 명령 / javac.exe - 컴파일러
1. 시스템 변수에 JAVA_HOME변수 생성( program files\java 아래에 있는 사용할 JDK 주소를 등록 )
2. Path에 해당 JDK 아래 있는 bin 까지 등록
`````````````````````

#### 2-2 실행구조 

![process](https://user-images.githubusercontent.com/22463540/75843331-3e8de700-5e16-11ea-945d-4e24cd8b9971.png)
(출처 : inflearn JavaProgramming Basic Course (renew ver.) )

#### @가비지 컬렉터 - 프로그램 실행에 필요한 메모리를 자바는 Garbage collector가 알아서 관리해줌

3강 - 변수 
------------------

#### 3-1 변수란?
``````````````````
데이터를 임시로 담을 수 있는 메모리 공간
``````````````````
#### 3-2 변수 선언과 초기화 
``````````````````
Ex) int i = 10; 
``````````````````
#### @ 변수 사용이유
``````````````````
메모리에 데이터를 저장해서 재활용하기위해
``````````````````

4강 - 기본자료형(Primitive Type)
------------------

#### 4-1 기본 자료형(Primitive Type)과 객체 자료형(Reference Type)
``````````````````
기본 자료형은 데이터가 변수에 직접 저장되고 (Ex: int i = 10), 

객체 자료형은 객체 메모리 주소가 변수로 저장된다.(Ex: 0x33ec45(C 계열에서는 포인터, Java에서는 레퍼런스 )
``````````````````

#### 4-2 Java 기본자료형
( 1byte = 8bit )
| 정수형  ||
| :--------: | :--------: |
| byte | 1byte |
| **char** | **2byte** |
| short | 2byte |
| **int** | **4byte** |
| long | 8byte |

| 실수형    ||
| :--------: | :--------: |
| float | 4byte |
| **double** | **8byte** |

| 논리형   ||
| :--------: | :--------: |
| **boolean** | **1byte** |

#### 4-3 형 변환

```java
  
  // 자동 (묵시적 ) 형 변환:
  // 작은 공간의 메모리에서 큰 공간의 메모리로 이동
  byte by = 10;
  int in = by;
  System.out.println("in = " + in ); // in = 10

  // 명시적 형 변환 : 
  // 큰 공간의 메모리에서 작은 공간의 메모리로 이동
  int iVar = 100;
  byte bVar = (byte)iVar;
  System.out.println("bVar = " + bVar); // bVar = 100

  iVar = 123456;
  bVar = (byte)iVar;
  System.out.println("bVar = " + bVar); // bVar = 64
  
```  

5강 - 특수문자와 서식
------------------

#### 5-1 특수문자 : 일반 문자가 아닌 특수한 목적으로 사용되는 문자
|  | RESULT |
| :---: | :---: |
| \\t | 탭 |
| \\n | 줄바꿈 |
| \\' | 작은 따옴표( ' ) |
| \\" | 큰 따옴표( " ) |
| \\\ | 역슬래쉬( \\ ) |

#### 5-2 서식문자 - 일반문자가 아닌 서식에 사용되는 문자

```````
printf() 메서드에 사용
:f 는 format(형식)을 뜻함
```````

|  | RESULT |
| :---: | :---: |
| \\t | 탭 |
| \\n | 줄바꿈 |
| \\' | 작은 따옴표( ' ) |
| \\" | 큰 따옴표( " ) |
| \\\ | 역슬래쉬( \\ ) |

#### 5-3 서식문자의 정렬과 소수점 제한 기능
```````````java

// 서식문자 정렬 기능
System.out.printf("%d\n",123);	//123
System.out.printf("%d\n",1234);	//1234
System.out.printf("%d\n",12345);	//12345

// 5자리를 맞춰서 오른쪽 정렬
System.out.printf("%5d\n",123);	//  123
System.out.printf("%5d\n",1234);	// 1234
System.out.printf("%5d\n",12345);	//12345

// 서식문자 소수점 제한 기능
System.out.printf("%f\n",1.23);	//1.230000
System.out.printf("%.0f\n",1.23);	//1
System.out.printf("%.1f\n",1.23);	//1.2
System.out.printf("%.2f\n",1.23);	//1.23
System.out.printf("%.3f\n",1.23);	//1.230

```````````

6강 - 연산자
--------------


6-1 피연산자 개수에 의한 연산자 구분
````````
단항 연산자 - 피연산자가 하나 존재 (Ex: +x, -x, !x )
이항 연산자 - 피연산자가 두개 존재 (Ex: x = y, x < y )
삼항 연산자 - 피연산자가 세개 존재 (Ex: 조건식 : true ? false )
````````

6-2 대입 연산자
``````
오른쪽의 결과를 왼쪽에 대입한다. ( = )

**주의** 왼쪽과 오른쪽이 같다의 의미는 '=='
``````

6-3 산술 연산자 
````````
덧셈 ( + ), 뺄셈 ( - ), 곱셈 ( * ), 나눗셈 ( / ), 나머지 ( % )
````````

6-4 복합 대입연산자
`````````
더하고 대입 ( += ), 빼고 대입 ( -= ), 곱하고 대입 ( *= ), 나누고 대입 ( /= ), 나머지를 대입 ( %= )
`````````

6-5 관계 연산자 - 두개의 피연산자를 비교해서 참/거짓의 결론을 돌출한다.
````````
크다 ( > ), 작다 ( < ), 크거나 같다 ( >= ), 작거나 같다 ( <= ), 같다 ( == ), 같지 않다 ( != )
````````

6-6 증감 연산자 - 1만큼 증가 하거나 감소를 수행
``````````
1만큼 증가 ( ++ ) , 1만큼 감소 ( -- )

**** 전,후위 연산자
int x = 10 
앞에 있으면 전위 연산자로 먼저 증감시키고 ( --x )	// x = 9
뒤에 있으면 후위 연산자로 다음 줄 부터 증감 (  x++ )	//  x = 9 
x = 10

````````````

6-7 논리 연산자 
`````````
둘 다 참이면 참 ( && )
둘 중 하나라도 참이면 참 ( || )
x의 상태를 부정 ( !x )
``````````

6-8 조건(삼항) 연산자 - 삼항 연산자로 두개의 피연산자 연산 결과에 따라 나머지 연산자가 결정된다.
`````
조건식 ? 식 1 : 식 2 
Ex: ( x > y ) ? 100 : 200;
`````

6-9 비트 연산자 
`````````
a & b : a 와 b가 모두 1이면 1 ( & : AND 연산 )
a | b : a와 b중 하나라도 1이면 1 ( | : OR 연산 )
a^b : a와 b가 같지 않으면 1 ( ^ : XOR 연산 )
`````````

7강 - 배열
-----------

7-1 배열이란?
````
인덱스를 이용해서 자료형이 같은 데이터를 관리하는 것 
`````
7-2 배열 선언 및 초기화
`````java
// 배열 선언 후 초기화
int[] arr1 = new int[3];
arr1[0] = 100;
arr1[1] = 100;
arr1[2] = 100;

// 배열 선언과 동시에 초기화
int[] arr1 = {10, 20, 30};
`````

8강 - 배열과 메모리
----------------

8-1 배열의 메모리 크기
`````````````````````````
배열을 구성하는 데이터의 자료형에 따라 배열의 메모리 크기가 결정된다.

( Ex: int[] arr = new int[3];  => arr : 12byte )
`````````````````````````

8-2 배열을 가리키는 배열이름
``````````````
기본 자료형 데이터를 담고 있는 변수와 달리 배열 변수는 배열 데이터의 주소를 담고 있다.
``````````````

8-3 배열 기본속성
````````````````java
// 배열 기본속성
int[] arrAtt1 = {10,20,30,40,50,60}
int[] arrAtt2 = null;
int[] arrAtt3 = null;

// 배열의 길이 - .length
System.out.println("arrAtt1.length : " +arrAtt1.length); // 6

// 배열의 요소 출력 - Arrays.toString()
System.out.println("arrAtt1 : " + Arrays.toString(arrAtt1) ;  // arrAtt1 : [10,20,30,40,50,60]

// 배열 요소 복사 - Arrays.copyOf(복사할배열, 복사할길이);
arrAtt3 = Arrays.copyOf(arrAtt1, arrAtt1.length);

// 배열 래퍼런스
arrAtt2 = arrAtt1;
System.out.println("arrAtt1 : " + arrAtt1);	// 주소값 
System.out.println("arrAtt2 : " + arrAtt2);	// arrAtt1과 같은 주소
System.out.println("arrAtt3 : " + arrAtt3);	// 배열의 데이터는 arrAtt1과 같으나 주소는 전혀 다름
````````````````

8-4 다차원 배열
``````````````
배열 안에 또 다른 배열이 존재한다.

// 다차원 배열
int[][] arrMul = new int[3][2];
```````````````

9강 - 조건문
-----------

9-1 조건문이란?
`````
조건의 결과에 따라서 양자 택일( 주로 if문 ) 또는 다자 택일( 주로 switch문 )을 진행한다.
`````
9-2 if문
`````java
// if (조건식)
int num1 = 10;
int num2 = 20;
			
if(num1 < num2) {
	System.out.println("num1는 num2보다 작다.");
}else if(num1 > num2) {
	System.out.println("num1는 num2보다 크다.");
}else if(num1 == num2) {
	System.out.println("num1과 num2는 같다.");
}else{
	System.out.println("num1과 num2는 크지도 작지도 같지도 않다.");
}
`````
9-3 switch문
`````java
//switch문
System.out.print("점수를 입력하세요 :  ");
Scanner scan  =  new Scanner(System.in);
int score = scan.nextInt();
			
switch (score) {
case 100:
case 90:
	System.out.println("수");
	break;
case 80:
	System.out.println("우");
	break;
case 70:
	System.out.println("미");
	break;
default:
	System.out.println("재시험!");
	break;
}
			
scan.close(); // 자원 반납
`````

10강 - 반복문
------------

10-1 반복문이란?
`````
프로그램 진행을 특정 조건에 따라 반복적으로 진행하는 것
`````

10-2 for문
`````
Ex) for( int i = 1; i < 10; i++)
i가 1부터 10보다 작을때 까지 i에 1씩 더해가며 프로그램 반복 진행
`````

10-3 while문
`````
for문과 달리 초기값은 외부에 존재하며, 조건의 증감을 내부에 따로 구현
Ex) 
int rNum = 1;
while(rNum < 10){
	내용
	rNum++;
}
``````

10-4 do-while문
``````
while문과 비슷하며, 차이점은 조건 결과에 상관없이 무조건 최초한번은 수행한다.
Ex)
int i = 10;
do{
	System.out.println("무조건 1번은 실행합니다.");
}while(i > 100);
``````
