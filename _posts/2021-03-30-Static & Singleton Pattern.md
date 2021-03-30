---
layout: post
title: "Static & Singleton Pattern"
subtitle: "JAVA"
date: 2021-03-30
background: '/img/posts/01.jpg'
categories: ['Java']
---

![Static & Final](/img/posts/Static & Final.jpg){: width="100%" height="800"}

![Singleton Pattern & 단축키](/img/posts/Singleton Pattern.jpg){: width="100%" height="800"}

-----

## Static

```java
package com.gd.test.controller;

import com.gd.test.service.TestService6;

public class TestController6 {

	public int a = 10;

	public static void main(String[] args) {

		TestService6.s = "Hi~";
		System.out.println(TestService6.s);

		// TestService6.SF = "Hi~"; // 오류. SF가 상수이기 때문에 값 변경 불가능
		System.out.println(TestService6.SF);

		// System.out.println(a); 오류
	}
}
```

-----

```java
package com.gd.test.service;

public class TestService6 {
	public static String s = "static 변수임";
	public static final String SF = "상수임";
}
```

-----

#### 실행결과

```java
Hi~
상수임
```

-----

-----

## Singleton Pattern

```java
package com.gd.test.controller;

import com.gd.test.service.SingletonService;
import com.gd.test.service.TestService6;

public class TestController6 {

	public int a = 10;

	public static void main(String[] args) {

		SingletonService ss = SingletonService.getInstance();
		System.out.println(ss.a);

		ss.a = 7;

		TestService6 ts = new TestService6();

		ts.test();
	}
}
```

-----

```java
package com.gd.test.service;

public class TestService6 {

	public void test() {
		SingletonService ss = SingletonService.getInstance();

		System.out.println(ss.a);
	}
}
```

-----

```java
package com.gd.test.service;

public class SingletonService {

	// 정적변수 선언
	private static SingletonService instance = null;

	// 객체취득 메소드
	public static SingletonService getInstance() {
		if (instance == null) {
			// 객체 생성
			instance = new SingletonService();
		}
		return instance;
	}
	public int a = 10;
}
```

-----

#### 실행결과

```java
10
7
```

