---
description: JPA 공부중 자바 컬렉션이란 단어가 나와서 검색하게 되었다
---

# 자바 컬렉션\(Java Collection\)

JPA 에 대해 공부하던중 아래와 같은 문구를 마주하고, 해당 단어에 대해 찾아보게 되었다

> INSERT SQL 을 직접 작성하는 것이 아니라 객체를 마치 자바 컬렉션에 저장하듯이 ORM 프레임워크에 저장하면 된다

여러 원소들을 담을 수 있는 자료구조를 뜻함

데이터를 한 곳에 모아 편리하게 저장 및 관리하는 가변 크기의 객체 컨테이너

```text
 * @see Collection
 * @see List
 * @see SortedSet
 * @see HashSet
 * @see TreeSet
 * @see AbstractSet
 * @see Collections#singleton(java.lang.Object)
 * @see Collections#EMPTY_SET
 * @since 1.2
 */

public interface Set<E> extends Collection<E> 

public interface List
...
```

![](.gitbook/assets/image%20%281%29.png)

컬렉션 안에 인터페이스들이 들어있는 것 같다 

#### Collection 인터페이스



**Collection 인터페이스를 구현하는 제네릭 클래스**

| 인터페이스 | 특징 | 구현클래스 |  |
| :--- | :--- | :--- | :--- |
| Collection | List | 객체의 순서가 있고, 원소가 중복될 수 있다. | ArrayList, Stack, Vector, LinkedList |
| Queue | 객체를 입력한 순서대로 저장하며, 원소가 중복될 수 있다. | DelayQueue, PriorityQueue, LinkedList |  |
| Set | 객체의 순서가 없으며, 동일한 원소를 중복할 수 없다. | HashSet, TreeSet, EnumSet |  |



**Collection 인터페이스가 제공하는 주요 메서드**

| 메서드 | 설명 |
| :--- | :--- |
| boolean add\(E e\) | 객체를 맨 끝에 추가한다. |
| void clear\(\) | 저장된 모든 객체를 제거한다. |
| boolean contains\(Object o\) | 명시한 객체의 저장 여부를 조사한다. |
| boolean isEmpty\(\) | 리스트가 비어있는지 조사한다. |
| Iterator&lt;E&gt; iterator\(\) | Iterator\(\)를 반환한다. |
| boolean remove\(Object o\) | 명시한 첫 번째 객체를 제거하고, 제거 여부를 반환한다. |
| int size\(\) | 저장된 전체 객체의 개수를 반환한다. |
| T\[\] toArray\(T\[\] a\) | 리스트를 배열로 반환한다. |

