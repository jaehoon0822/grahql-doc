# Type System

일반적으로 `Object` 안의 `fields` 를 선택하는 `query langauge` 이다.
이는 다음과 같다.

```graphql
{
  hero {
    name
    appearsIn
  }
}
```

```json
{
  "data": {
    "hero": {
      "name": "R2-D2",
      "appearsIn": [
        "NEWHOPE",
        "EMPIRE",
        "JEDI"
      ]
    }
  }
}
```

1. 특별한 `root` 객체와 함께 시작한다.
2. `hero` 필드를 선택한다.
3. `hero` 가 반환된 객체의 경우, `name` 과 `appearsIn` 필드를 선택한다.

이렇게 보면 매우 단순해 보이고 쉽게 예측 가능할것으로 생각된다.
하지만 실질적인 문제가 존재한다.

해당 `field` 가 어떠한 `type` 을 가지는지 알아야 하고, 어떤 종류의 `object` 를 리턴하는지, `sub object` 는 존재하는지 같은 것이 필요하다.

## Type Language

`GrapgQL Schemas language` 를 사용한다. `GrapgQL` 은 특정한 언어에 의존하지 않는다고 한다.

## Object types and fields

`GrapgQL Schemas` 의 가장 기본적인 구성요소는 `Object type` 이다.
이 `Object type` 은 단지 `server` 로 부터 `fetch` 할 `Object` 종류를 묘사한다. 

다음을 보도록하자.

```graphql
type Character {
  name: String!
  appearsIn: [Episode!]!
}
```

. `Character` 는 `GraphQL Object Type` 이다.

. `name` 그리고 `appearsIn` 은 `Character type` 의 `field` 이다.

. `String` 은 `build-in scalar types` 이다. `scalar types` 에 대해서는 추후 나온다.

. `String!` 은 `non-nullable` 을 `field` 임을 의미한다.

. `[Episode!]` 은 `Episode Object` 의 배열을 나타낸다. 여기에 `!` 가 붙으니,  `non-nullable` 하다.





