# 혼자 공부하는 C언어
![image](https://github.com/user-attachments/assets/d7961499-439e-4605-801d-f11bae383b85)
***

## 1. 상수와 데이터 출력

### 1.2) C 프로그램의 구조와 데이터 출력 방법

* 머리(head)와 몸통(body)로 구성된다.

* 머리는 함수 원형(function prototype)이라고 하며, 함수의 이름과 필요한 데이터 등을 표시한다.

* 함수에서 실행할 일들은 몸통의 중괄호 안에 작성하며 return 0;을 넣어 프로그램을 종료한다.


#### 10과 20을 더하는 프로그램

* stdio.h는 standard input output을 의미하며 C 언어에서 기본으로 사용하는 입출력 함수가 들어 있다.

```
#include <stdio.h>  // stdio : standard input output(표준입출력)의 줄임말

int main(void)
{
  10 + 20;  // 10과 20을 더한다

  return 0;
}
```

#### 문자열을 화면에 출력하는 프로그램

* printf 함수는 stdio.h 에 포함되어 있다.

```
#include <stodio.h>  // stdio : standard input output(표준입출력)의 줄임말

int main(void)
{
  printf("Be happy");
  printf("My friend");

  return 0;
}
```

#### 제어 문자를 사용한 출력

```
#include <stdio.h>

int main(void)
{
  printf("Be happy\n");  // "Be happy"를 출력하고 줄을 바꿈(\n)
  printf("123456789\n");
  printf("My\tfriend\n);  // "My"를 출력하고 탭 위치로 이동(/t) 후에 "friend"를 출력하고 줄을 바꿈(\n)
  printf("Goot\bd\tcahnce\n")  // t를 d로 바꾸고  탭 위치로 이동(\t) 후에 "cahnce"를 출력하고 줄을 바꿈(\n)
  printf("Cow\rW\a\n");  // 맨 앞으로 이동(\r)해 C를 W로 바꾸고 벨소리(\a)를 내고 줄을 바꿈(\n)

  return 0;
}
```

#### 정수와 실수의 출력

```
#include <stdio.h>

int main(void)
{
  printf("%d\n", 10);  // %d 위치에 10 출력
  printf("%lf\n", 3.4);  // %lf 위치에 3.4를 소수점 이하 6자리까지 출력
  printf("%.1lf\n", 3.45);  // 소수점 이하 첫째 자리까지 출력(둘째 자리에서 반올림)
  printf("%.10lf\n", 3.4);  // 소수점 이하 10자리까지 출력

  printf("%d와 %d의 합은 %d입니다.\", 10, 20, 10 + 20);
  printf("%.1lf-%.1lf = %.1lf\n, 3.4, 1.2, 3.4 - 1.2);

  return 0;
}
```

#### printf 함수 사용법

|출력 데이터|사용 예|출력 결과|
|:---:|:---:|:---:|
|문자열|printf("Be happy");|Be happy! 출력|
|제어 문자|printf("Be happy\n");|Be happy! 출력 후 줄 바꿈|
|정수|printf("%d", 10);|정수 10출력(변환 문자 %d)|
|실수|printf("%lf", 3.5);|실수 3.500000 출력(변환 문자%lf)|
|수식||printf("%d", 10 + 20);|10과 20을 더한 결과인 30 출력|

#### 제어 문자의 종류

|제어문자|의미|기능|
|:---:|:---:|:---:|
|\n|개행(new line)|줄을 바꾼다.|
|\t|탭(tab)|출력 위치를 다음 탭(tab) 위치로 옮긴다.|
|\r|캐리지 리턴(carriage return)|출력 위치를 줄의 맨 앞으로 옮긴다.|
|\b|백스페이스(backspace)|출력 위치를 한 칸 왼족으로 옮긴다.|
|\a|알럿(alert) 경보|벨(bell)소리를 낸다.|

***

### 2.2) C 프로그램의 구조와 데이터 출력 방법

#### 세가지 진법의 정수 상수

* 정수 상수는 10진수, 8진수, 16진수로 표현할 수 있으며, 8진수는 숫자 앞에 0, 16진수는 0x를 붙여 구분한다.

* 8진수로 출력하려면 %o, 16진수 소문자는 %x & 대문자는 %X를 사용한다.

```
#include<stdio.h>

int main(void)
{
	printf("%d\n", 12);	// 10진수 정수 상수 출력
	printf("%d\n", 014);	// 8진수 정수 상수 출력
	printf("%d\n", 0xc);	// 16진수 정수 상수 출력

	return 0;
}
```

#### 지수 형태의 실수 상수

* %lf 변환 문자로 실수를 출력하면 소수점 이하 6자리까지만 출력된다.

```
#include<stdio.h>

int main(void)
{
	printf("%.1lf\n", 1e6);	// 지수 형태의 실수를 소수점 형태로 출력
	printf("%.7lf\n", 3.14e-5);	// 소수점 이하 7자리까지 출력
	printf("%le\n", 0.0000314);	// 소수점 형태의 실수를 지수 형태로 출력
	printf("%.2le\n", 0.0000314);	// 지수 형태로 소수점 이하 둘째 자리까지 출력

	return 0;
}
```


#### 문자와 문자열 데이터의 출력

```
#include<stdio.h>

int main(void)
{
	printf("%c\n", 'A');	// 문자 상수 출력
	printf("%c\n", "A");	// 문자열 상수 출력
	printf("%c은 %s입니다.", '1', "first");	// 문자(%c)와 문자열(%s)을 함께 출력

	return 0;
}

```




