---
description: jpa 공부
---

# JPA가 나온 이유

\[ JPA 의 장점 \]

* SQL 중심적인 개발에서 객체 중시으로 개발
* 생산성
  * 저장 : jpa.persist\(member\)
  * 조회 : Member member = jpa.find\(memberId\)
  * 수정 : member.setName\("변경할 이름"\)
  * 삭제 : jpa.remove\(member\)
  * JPA 에서 제공해주는것을 활용하면 된다.
* 유지보수
  * 예를들어 아래와 같은 Member 클래스가 있을때, tel 이라는 객체가 추가가 되었다  그러면 SQL 문에서 Member 클래스에서 조회, 수정, 저장이 일어난 것들에 tel 을 추가해야하는 반복작업이 일어나고 심지어 내가 쿼리문을 수정할때, tel 을 까먹고 못 넣을 수 있겠지만, jpa 를 사용함으로서, 줄일 수 있다. 

```text
public class Member {
    private String memberId;
    private String name;
    private String tel;
}

1. INSERT INTO MEMBER(MEMBER_ID, NAME, TEL) VALUES 
2. SELECT MEMBER_ID, NAME, TEL FROM MEMBER
3. UPDATE MEMBER SET ... TEL = ?
```

* 패러다임의 불일치 해결
  * 예를 들어서, jpa 조인을 쓰면, jpa 가 알아서 한방 쿼리로 조인해온 객체를 반환
  * 패러다임 불일치를 해결할 적절한 쿼리를 날려줌 \( jdbc api 랑 매핑해서 결과를 반환해줌 \)
* 성능
  * 1차 캐시와 동일성 보장
    * 동일한 트랜잭션안에서 내가 select 로 무엇을 조회해왔어. 근데 두번째로 또 조회를 해. 그럼 아까 1차로 조회해온게 jpa 얘딴에 캐시로 저장되어 있어. 그래서 1차 캐시에 저장되어있는걸 가져와 근데 동일성도 보장됨.
  * 트랜잭션을 지원하는 쓰기 지연
  * 지연 로딩\(lazy loading\)
* 데이터 접근 추상화와 벤더 독립성
* 표준

