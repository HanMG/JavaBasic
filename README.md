# JavaBasic
Inflearn - JavaProgramming Basic Course (renew ver.) 무료기념 호다닥 복습,정리

1강 - 자바에 대한 간략소개와 JDK, Eclipse 설치, Hello JAVA World Project 생성
-----------------
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
