# JiYu Documentation

## 소개
jiyu-lang은 컴파일시간 메모리 안정성과 빠른속도를 지향하는 정적 타입 컴파일 언어입니다.
이 문서는 프로그래밍을 어느정도 알고 있는 사람을 기준으로 작성되어 있습니다.  

## 목차

<table>
    <tr><td width=25% valign=top>

* [Hello world](#hello-world)
* [주석](#주석)
* [변수](#변수)
    * [상수](#상수)
* [함수](#함수)
* [데이터 타입](#데이터-타입)
* [흐름제어](#흐름제어)
* [컴파운드 타입](#컴파운드-타입)

</td><td width=25% valign=top>

* [Hello world](#hello-world)

</td><td width=25% valign=top>

* [Hello world](#hello-world)

</td><td valign=top>

* [Hello world](#hello-world)

</td></tr>
</table>

## Hello, world!
```jiyu
fn main () {
  println("Hello, world!");
} 
```

## 주석
주석은 다음과 같지 작성할 수 있습니다.
```jiyu
// 주석 입니다
/* 주석
입니다*/
```

## 변수
기본적으로 모든 변수는 불변변수입니다. 
변수는 
```jiyu
let foo :i32 = 119; 
``` 
같이 선언하거나 혹은 자료형을 빼서
```jiyu
let foo := 119; 
``` 
다음과 같이 선언할 수 있습니다. 이 경우에는 컴파일러가 정해준 타입으로 저장됩니다.
변수는 선언될때 무조건 :=으로 초기화가 시켜야됩니다.
또한 변수는 무조건 {}블록 안에서만 선언할 수 있습니다.
변수의 이름 스타일은 스네이크 케이스를 권고합니다.

가변변수가 필요하다면 다음과 같이 선언할 수 있습니다.
```jiyu
mut foo :i32 = 119;
//혹은
mut foo := 119;
```
### 상수
상수는 기본적으로 변수와 같지만 어디에서나 선언할 수 있습니다.
```jiyu
const foo := 119;
```

## 함수 
함수는 
```jiyu
fn add(x :i32, y :i32) -> i32 {
    x + y
}
```
다음과 같이 선언합니다.
괄호 안의 x와 y는 매개변수를 의미합니다.
화살표 -> 뒤의 i32은 함수의 반환 타입을 의미합니다.
;이 붙어 있지 않은 x + y는 표현식입니다.
```jiyu
fn foo() -> i32, string {
}
```
다음과 같이 여러 값을 반환할 수 있습니다.

```jiyu
let add :fn = (x :i32, y :i32) -> i32 {
    x + y
}
```
## 데이터 타입
### 정수 타입
부호 있음: i8, i16, i32, i64
부호 없음: u8, u16, u32, u64

정수 리터럴은 다음과 같이 표현할 수 있습니다.
Hex: 0x77
Dec: 119
Oct: 0o167
Bin: 0b01110111

### 실수 타입
f32 f64

### 불리언 타입
불리언 타입은 true나 false 중 하나를 나타냅니다.

### 문자 타입
알파벳 타입: char
문자열 타입: string

## 흐름제어
### if
```jiyu
fn main() {
    let foo := 9;
    let bar := 1
    
    if foo < bar {
        println("foo < bar");
    } else if foo > bar {
        println("foo > bar");
    } else {
        println("foo == bar");
    }
}
```
if는 표현식으로도 사용될 수 있습니다.
```jiyu
fn main() {
    let foo := 9;
    let bar := 1
    
    let bigger := if foo < bar {
        bar
    } else if foo > bar {
        foo
    } else {
        foo
    }
    
    println("bigger number is: {}", bigger);
}
```
### 루프

## 컴파운드 타입 
