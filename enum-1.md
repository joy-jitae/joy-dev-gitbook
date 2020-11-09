# Enum 사용 \(1\)

RoleType Enum

```text
public enum RoleType {
    ADMIN, USER
}
```

```text
package jpabook.start;

import lombok.*;

import javax.persistence.*;
import java.util.Date;

@Setter
@Entity
@AllArgsConstructor
@NoArgsConstructor
@Getter
@Table(name="MEMBER")
public class Member {

    @Id
    @Column(name = "ID")
    private String id;

    @Column(name = "NAME", nullable = false, length = 10)
    private String username;

    private Integer age;

    // Enum 사용시, 
    @Enumerated(EnumType.STRING)
    private RoleType roleType;

}
```

Enumerated 어노테이션으로 EnumType.String 으로 해야한다. 

EnumType.ORDINAL 은 RoleType 에 있는 필드를 순서대로 0, 1, 2 .. 으로 지정하기 때문이다.

```text
public enum RoleType {
    ADMIN, USER
}
```

그래서 처음에 ADMIN 에 대한 RoleType 이 0인데, 맨앞에 아래와 같이 VIP 가 추가가 되면, VIP 가 0이기 때문에 꼬여버린다. 그래서 아예 String 값으로 저장되게끔, **EnumType.String  으로 지정해야한다. 주의하**

```text
public enum RoleType {
   VIP, ADMIN, USER
}
```

