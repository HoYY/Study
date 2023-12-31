DTO <> Entity 변환 방법
======================

## Mapper
- DTO 클래스와 Entity 클래스를 서로 변환해주는 클래스.
- DTO, Entity 변환 코드를 효율적으로 관리하기 위해 사용.
- Mapper 에게 DTO, Entity 변환 작업을 위임함으로써 역할 분리에 용이.

### 1. ModelMapper (Mapper)
- 런타임 시 매핑을 하기 때문에 성능면에서 Mapstruct 보다 성능이 떨어지고, 매핑에 오류가 있어도 코드가 실행되어야 오류 확인이 가능하다.

### 2. Mapstruct (Mapper)
- 컴파일 시 코드를 생성하기 때문에 런타임에서 안정성을 보장해준다.
- 구현 코드를 자동으로 만들어주기 때문에 사용이 쉽다.
- Lombok 라이브러리의 getter, setter builder 를 이용하기 때문에 Lombok 보다 먼저 의존성이 선언되면 안된다.
- DTO, Entity 의 필드가 같은 단순한 구조는 별도의 어노테이션 없이 간단하게 변환이 가능하지만 DTO, Entity 가 복잡한 구조일 경우 매핑 설정 코드가 길어져서 Mapstruct 를 사용하는 장점이 퇴색된다.
- Entity 당 하나의 클래스가 필요하다.

### 3. 정적 팩토리 메서드
- 캡슐화에 용이
- 의미있는 이름을 통해 작성자의 의도 파악이 용이
- 상속이 불가능하다.


※ 생성로직이 단순한 객체라면 그냥 생성자를 쓰는게 편하다.<br>
※ 생성할 때 비지니스 로직이나 의미있는 생성자 메서드 명이 필요하다면 정적 팩토리 메서드가 좋다.<br>
※ 생성로직이 너무 복잡하면 서비스 계층에서 이 문제를 해결하지 않고, 별도의 팩토리 오브젝트를 사용한다.<br>
※ 파라미터가 너무 많거나 복잡하면 빌더를 사용하는게 좋다.<br>
※ 복잡도를 높이지 않는 선에서 단순한 방법을 선택하는 것이 좋은 방법.<br>
※ 절대 Entity 가 View 용 DTO 를 의존하면 안된다.