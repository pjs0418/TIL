# Kotlin 기본 문법

# 함수 기본 형태

```kotlin
fun main() {
    println("Hello World!")
}
```

- 리턴 타입을 명시해 줄 필요가 없는 경우(void), 리턴 타입을 명시해주지 않아도 된다.
- 만약 명시한다면, Unit이라고 써주면 된다.

```kotlin
fun hello() : Unit{
    println("Hello World!")
}
```

- 리턴값이 있는 경우, 함수의 리턴 타입을 명시해주어야 한다.
- 자료형의 첫 번째 글자가 대문자여야 한다.

```kotlin
fun add(a : Int, b : Int) : Int {
    return a + b
}
```

# Val vs Var

- val = value (변하지 않는 값)
- var = variable (변할 수 있는 값)

# String Template

```kotlin
		val name = "Jun Su "
    val lastName = "Park"
    println("My name is ${name + lastName} I'm 24")
    println("this is 2\$bill")
```

- $ 표시를 단순하게 사용하고 싶을 때는 \ 를 이용한다.

# 조건식

- 조건식(if문)은 다른 언어와 비슷하다.
- 조건식(if문)의 다른 표현(삼항연산자와 비슷하다.)

```kotlin
fun maxBy(a : Int, b : Int) : Int = if (a > b) a else b
```

### when(switch문과 비슷하다.)

```kotlin
fun checkNum(num : Int) {
    when(num) {
        0 -> println("This is 0")
        1 -> println("This is 1")
        2, 3 -> println("This is 2 or 3")
        else -> println("I don't know")
    }

    // when이 리턴값을 가질 경우, else를 꼭 써주어야 한다. 아닐 경우, 생략 가능하다.
    var b : Int = when(num) {
        0 -> 0
        1 -> 1
        else -> 2
    }

    when(num) {
        in 90..100 -> println("You are genius.")
        in 0..80 -> println("Not bad")
        else -> println("OK")
    }
}
```

# Expression vs Statement

- Kotlin의 모든 함수는 Expression이다.
- Expression이란 무언의 과정을 통해 값을 반환하는 것이다.
- Statement는 단순하게 어떻게 하라는 명령의 의미를 가진다.

# Array and List

- Array는 기본적으로 mutable이다.
- List는 List와 MutableList가 있다. 기본적으로는 값을 변경할 수 없는 List이다.

```kotlin
fun array() {
    val array = arrayOf(1,2,3)
    val list = listOf(1,2,3)
    val array2 = arrayOf(1, "d", 3.4f)
    val list2 = listOf(1, "d", 11L)

    array[0] = 3
    // list[0] = 3 은 안 된다.

    val arrayList = arrayListOf<Int>()
    arrayList.add(10)
    arrayList.add(20)
    arrayList[0] = 20
}
```

# 반복문

```kotlin
fun forAndWhile() {
    val students = arrayListOf("A", "B", "C", "D")

    for (name in students) {
        println("${name}")
    }

    for((index, name) in students.withIndex()) {
        println("${index + 1}번째 알파벳 : ${name}")
    }

    var sum : Int = 0
    for (i in 1..10 step 2) {
        sum += i
    }
    println(sum)

    for (i in 10 downTo 1) {
        sum += i
    }

    // 100을 포함하지 않는다.
    for (i in 1 until 100) {
        sum += i
    }

    var index = 0
    while (index < 10) {
        println("current index : ${index}")
        index++
    }
}
```

# 참고 자료

[https://www.youtube.com/watch?v=IDVnZPjRCYg&t=2312s](https://www.youtube.com/watch?v=IDVnZPjRCYg&t=2312s)