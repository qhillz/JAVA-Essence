# String

* 기본적으로, Object 클래스 상속
* `==` 연산자, 두 String 변수 참조 주소 값 비교
* `equals` 메소드, 두 String 변수 문자열 비교



# ENUM

``` bash
package day3;  //정해진 값, 정해진 갯수의 데이터 열거한다.
public enum Week {
	Mon,Tue,Wed,Thr,Fri,Sat,Sun
}
```

* Week today = Week.Mon;

  * #### 변수타입이라는 것을 기억해라!!!!!!!

  * #### 인스턴스 생성불가. (Static으로 구성됨.)



# 클래스 문법

``` bash 
[modifier] class 이름 [extends...][implements...]
```

* implements는 여러번, extends는 한번



| 역할     | modifier  | class | var                   | method        | 생성자 |      |      |
| -------- | --------- | ----- | --------------------- | ------------- | ------ | ---- | ---- |
| 접근권한 | public    | o     | o                     | o             | o      |      |      |
|          | protected | x     | o                     | o             | o      |      |      |
|          | private   | x     | o                     | o             | o      |      |      |
| 사용방법 | static    | x     | o                     | o             | x      |      |      |
|          | final     | o     | o                     | o             | x      |      |      |
|          | abstract  | o     | x                     | o             | x      |      |      |
| 기타     |           |       | volatile   ,transient | native, synch |        |      |      |

## `부가설명`

*  **private –** **변수,메소드,생성자앞 선언.**

   **사용 영역을 현재 클래스 제한.**

   **no modifier** **–** **클래스, 변수,메소드,생성자앞 선언.**

  **사용 영역을 현재 패키지 제한**

  **protected -** **변수,메소드,생성자앞 선언.**

  **사용 영역을 현재 패키지 + 다른 패키지의 상속받은 클래스로 제한.**

  **public -** **클래스, 변수,메소드,생성자앞 선언.**

  **사용 영역을 무제한**



