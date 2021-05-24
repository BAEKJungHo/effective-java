# 펙스(PECS) : producer-extends, consumer-super

`PECS` 원칙은 다음과 같다.

매개변수화 타입 T 가 생산자라면 `<? extends T>`를 사용하고, 소비자라면 `<? super T>` 를 사용하라. PECS 공식은 와일드카드 타입을 사용하는 기본 원칙이다.

- E 소비자(consumer) 매개변수에 와일드카드 타입 적용

```java
public void popAll(Collection<? super E> dst) {
  while(!isEmpty())
    dst.add(pop())
}
```

- 생산자(producer) 매개변수에 와일드카드 타입 적용

```java
public Chooser(Collection<? extends T> choices) {

}
```

Comparable 과 Comparator 는 모두 소비자이다.

> 만약, 클래스 사용자가 와일드카드 타입을 신경 써야 한다면 그 API 에 무슨 문제가 있을 가능성이 크다. 
