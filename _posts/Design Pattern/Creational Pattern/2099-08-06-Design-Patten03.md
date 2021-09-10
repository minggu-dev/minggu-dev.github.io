---
layout: post
title:  "[Design Pattern] 디자인 패턴(3) - 생성 패턴 (팩토리 메서드)"
date:   2099-08-06 13:00:18 +0900
categories: Design-Patten
tags: Design-Patten software Creational-Pattern
---
# Introduction

![패턴](/img/design/creational/Creational.jpg)
>
#### 객체의 생성과 관련된 생성 패턴 중 두 번째로 팩토리 메서드에 대하여 알아볼 차례이다. 처음 들었을 때 팩토리라는 용어를 보고 공장을 떠올리게 되었는데 어떠한 연관관계가 있을지 알아보자.

<br>
<br>
# 팩토리 메서드 패턴이란?
 팩토리(factory)라는 '공장'을 뜻하는 용어에서 보듯이 무언가를 생성해준다는 느낌이 든다. 이 용어에 걸맞게 팩토리 메서드는 객체의 생성에 대한 정의를 팩토리에 정의하여 객체 생성을 코드와 분리하여 준다. 어떤 객체를 생성할지에 대한 것은 서브클래스가 결정하도록 한다.

<br>
<br>
# 사용하기 좋은 때
상황에 따라 올바른 객체를 사용하고자 할 때 주로 사용이 된다.<br>
일반적으로 많이 사용이 된다. (ex. spring 프레임워크의 factory)

<br>
<br>
# 장단점
### 장점
- 인터페이스를 바탕으로 유연성과 확장성이 뛰어난 코드를 만들 수 있다.
- 객체의 자료형이 서브 클래스에 의해 결정된다.
- SOLID원칙 중 DIP를 성립한다.

### 단점
- 새로 생성할 객체의 종류가 늘어날 때마다 클래스가 증가하게 된다.
<br><br>

# 클래스 다이어그램
![Class Diagram](/img/design/creational/factory_method-diagram.png)
**ShapeFactory** : Shape에 대한 팩토리 메서드 패턴을 적용한 클래스이다.<br>
**Shape** : 팩토리로 생성할 객체의 종류이다.<br>
**Cicle, Square** : 팩토리로 생성할 구체적인 객체의 클래스이다.<br>
**FactoryPatternDemo** : 메인 클래스
<br><br>

# 코드 예시

```java
//
public interface Shape {
	void draw();
}

public class Circle implements Shape{
	@Override
	public void draw() {
		System.out.println("Circle draw() method.");
	}
}

public class Square implements Shape{
	@Override
	public void draw() {
		System.out.println("Square draw() method.");
	}
}
```
팩토리로 생성할 객체의 종류 Shape 인터페이스와 그걸 구현한 클래스이다. 간단하게 예시만 보여주기 위해 별 다른 기능을 넣지 않았다.

<br><br>

- ShapeFactory.java

```java
public class ShapeFactory {
	public Shape getShape(String shapeType) {
		if(shapeType.equalsIgnoreCase("CIRCLE"))
			return new Circle();
		else if(shapeType.equalsIgnoreCase("RECTANGLE"))
			return new Square();
		else
			return null;
	}
}
```





<br>
<br>
<br>
<br>
이제 막 알아가는 단계인 초보이므로 오류나 잘못된 점이 있다면 지적해주시면 감사합니다! 🥰
