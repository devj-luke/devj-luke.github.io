---
layout: listings
date: 2023-08-30 09:17:39 +0900
---
* toc
{:toc}

# 개요

남은 시간을 계산하는 스크립트 실행 중 다음과 같은 에러가 났다.

> value too great for base (error token is 08 )



# 이유

zsh 쉘의 경우 0으로 시작하면 8진수로 간주한다.

이때 입력된 값이 만약 8진수가 가능한 숫자인 0,1,2,3,4,5,6,7이 아닌 숫자가 들어올 경우 에러가 뜨는 것이다.



## 에러 코드 예시

```shell
#!/bin/zsh

val1=00
# 에러나는 코드 
val2=08
# 정상 코드 
# val2=07

echo "$val1"
echo "$val2"


result=$(($val1 - $val2))
echo "결과 : ${result}"
```

0~7이 넘는 숫자가 들어올 경우 에러가 뜨고 아닌 경우 정상 출력된다.



# 해결

쉘의 연산시에 아래와 같이 10진수로 연산한다는 것을 명시해주면 된다.

```shell
# 10#${변수}
10#${val1}
```



## 해결 코드 예시

```shell
#!/bin/zsh

val1=00
# 에러나는 코드
val2=08

echo "$val1"
echo "$val2"


result=$((10#${val1} - 10#${val2}))
echo "결과 : ${result}"
```

실행해보면 아래와 같이 제대로 결과가 나옴을 확인할 수 있다.

> 00<br>
> 08<br>
> 결과 : -8



# 참조

- [ShellCheck - SC2080](https://github.com/koalaman/shellcheck/wiki/SC2080)