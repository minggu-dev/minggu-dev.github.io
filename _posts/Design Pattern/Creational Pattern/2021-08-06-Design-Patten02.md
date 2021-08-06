---
layout: post
title:  "[Design Pattern] 디자인 패턴(2) - 생성 패턴 (싱글톤)"
date:   2021-08-06 11:00:18 +0900
categories: Design-Patten
tags: Design-Patten software Creational-Pattern
---
# Introduction

![패턴](/img/design/creational/Creational.jpg)
>
#### 객체의 생성과 관련된 생성 패턴 중 싱글톤 패턴에 대하여 알아보자.

<br>
<br>
# 싱글톤 패턴이란?
객체를 전역변수로 사용하지 않고 유일한 하나의 객체를 생성하여 객체가 필요한 곳이면 어느 곳에서든지 사용할 수 있도록 만드는 패턴이다.

<br>
<br>
# 사용하기 좋은 때
공통된 객체를 여러곳에서 생성하여 사용해야할 때 싱글톤 패턴으로 하나만 생성하여 사용해준다.


<br>
<br>
# 장단점
### 장점
- 객체가 필요한 여러 곳에서 생성하지 않고 사용할 수 있기 때문에 메모리 낭비를 방지할 수 있다.

### 단점
- 만약 싱글톤 인스턴스에게 너무 많은 일을 하게 하거나 많은 데이터를 공유한다면 SOLID원칙 중 SRP, OCP를 위반하기 때문에 꼭 필요한 경우에만 사용하도록 해야한다.
<br><br>

# 클래스 다이어그램
![Class Diagram](/img/design/creational/singleton-diagram.png)

**SingleObject** : 싱글톤 패턴을 적용할 클래스이다. 이곳에서 유일한 하나의 객체를 생성하고 여러곳에서 사용할 수 있도록 해준다.<br>
**SingletonPatternDemo** : 메인 클래스

<br><br>

# 코드 예시
- SingleObject.java

```java
//
public class SingleObject {
	private static SingleObject single = new SingleObject();	//유일한 하나의 객체 생성

	private SingleObject() {}	//외부에서 생성 불가능

	public static SingleObject getInstance() {
		return single;	//생성된 유일한 하나의 객체를 호출한다.
	}
}
```
싱글톤 객체를 만들어 주는 방법은 간단하다. 싱글톤 객체로 만들고자 하는 클래스에 private static형태로 자기 자신객체를 하나 생성해 주고 생성자를 private로 설정해 외부에서 생성하지 못하도록 막는다. 그리고 getInstance()메서드를 통해 외부에서 싱글톤 객체를 사용하고 싶을 때 사용할 수 있도록 해준다.

외부에서 사용하는 예시를 보면 다음과 같다.
<br><br>

- SingletonPatternDemo.java

```java
public class SingletonPatternDemo{
	public static void main(String[] args) {
		SingleObject so = SingleObject.getInstance();	//getter를 이용하여 객체 호출
	}
}
```





<br>
<br>
<br>
<br>
이제 막 알아가는 단계인 초보이므로 오류나 잘못된 점이 있다면 지적해주시면 감사합니다! 🥰
