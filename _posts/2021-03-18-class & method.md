---
layout: post
title: "Class & Method"
subtitle: "JAVA"
date: 2021-03-18
background: '/img/posts/01.jpg'
categories: ['Java']
---

## Class & Method

![Class](/img/posts/Class.jpg){: width="1000" height="800"}

![Method](/img/posts/Method.jpg){: width="1000" height="800"}

-----

```java
public class Test09 {

	public static void main(String[] args) {

    Test09s ts = new Test09s();
		Test09s ts2 = new Test09s("Hi");

		ts.a = 7;

		System.out.println(ts.a); // a에 있는 값을 가져옴
		System.out.println(ts2.a);

		ts2 = ts;
		System.out.println(ts.a);
		System.out.println(ts2.a);

		ts.a();

		System.out.println(ts.b("보낸값"));

		System.out.println(ts.plus2(1, 3));

		ts.plus(3, 7);
		ts.minus(3, 7);
		ts.mul(3, 7);
		ts.div(3, 7);
		ts.remainder(3, 7);

		ts.gugu(128);
	}

}

```

-----

```java
// 클래스
public class Test09s {
	int a = 10;

	public Test09s() {
		System.out.println("기본생성자 실행중.");
	}

	public Test09s(String str) {
		System.out.println("추가생성자 : " + str);
	}

// 메소드
	public void a() {
		System.out.println("a메소드 실행");
	}

	public String b(String str) {
		return "변경된 내용 : " + str;
	}

	public void plus(int a, int b) {
		System.out.println(a + b);
	}

	public int plus2(int a, int b) {
		return a + b;
	}

	public void minus(int a, int b) {
		System.out.println(a - b);
	}

	public void mul(int a, int b) {
		System.out.println(a * b);
	}

	public void div(int a, int b) {
		System.out.println(a / b);
	}

	public void remainder(int a, int b) {
		System.out.println(a % b);
	}

	public void gugu(int dan) {
		for (int i = 1; i <= 9; i++) {
			System.out.println(dan + " * " + i + " = " + dan * i);
		}
	}
}
```

-----

#### 실행결과

```java
기본생성자 실행중.
추가생성자 : Hi
7
10
7
7
a메소드 실행
변경된 내용 : 보낸값
4
10
-4
21
0
3
128 * 1 = 128
128 * 2 = 256
128 * 3 = 384
128 * 4 = 512
128 * 5 = 640
128 * 6 = 768
128 * 7 = 896
128 * 8 = 1024
128 * 9 = 1152
```

