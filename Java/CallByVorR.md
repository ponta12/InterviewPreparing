# Call By Value 와 Call By Reference



## Call By Value

> 값에 의한 호출

메서드가 호출될 때, 메모리 공간 안에서는 메서드를 위한 별도의 임시공간이 생성됨 (종료 시 해당 공간 사라짐)

call by value 호출 방식은 메서드 호출 시 전달되는 변수 값을 복사해서 메서드 인자로 전달함

이 때 복사된 인자는 메서드 안에서 지역적으로 사용되기 때문에 local value 속성을 가짐

```
따라서, 메서드 안에서 인자 값이 변경되더라도, 외부 변수 값은 변경 안됨
```

```c
void func(int n) {
	n = 20;
}

void main() {
    int n = 10;
    func(n);
    printf("%d", n);
}
```

> printf로 출력되는 값은 그대로 10이 출력된다.



## Call By Reference

> 참조에 의한 호출

call by reference 호출 방식은 메서드 호출 시 인자로 전달되는 변수의 레퍼런스를 전달함

따라서 메서드 안에서 인자 값이 변경되면, 매개변수로 전달된 객체의 값도 변경됨

```c
void func(int *n) {
    *n = 20;
}

void main() {
    int n = 10;
    func(&n);
    printf("%d", n);
}
```

> printf로 출력되는 값은 20이 된다.



## Java 메서드 호출 방식

자바의 경우, 메서드에 전달되는 인자의 데이터 타입에 따라 메서드 호출 방식이 달라짐

- primitive type(원시 자료형) : call by value

  > int, short, long, float, double, char, boolean

- reference type(참조 자료형) : call by reference

  > array, Class instance

```
String은 약간 특이함
String은 참조 자료형이지만, Java에서 동작할 때는 원시 자료형처럼 적용된다.
```



## 정리

Call by value의 경우, 데이터 값을 복사해서 함수로 전달하기 때문에 원본의 데이터가 변경될 가능성이 없다. 하지만 인자를 넘겨줄 때마다 메모리 공간을 할당해야해서 메모리 공간을 더 잡아먹는다.



Call by reference의 경우 메모리 공간 할당 문제는 해결했지만, 원본 값이 변경될 수 있다는 위험이 존재한다.

