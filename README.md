# JPASHOP
<h3 align = "center"> 상품 주문 웹 애플리케이션 클론코딩 </h3>

<img width="100%" src="https://github.com/ksw64285/JPASHOP/assets/107480512/53b816b8-0d1f-4451-b333-2bd0e8490671"/>

____

## 회원 엔티티 분석

![image](https://github.com/ksw64285/JPASHOP/assets/107480512/7ad67eac-a418-4464-b2d7-3cc696c2d0af)

- 회원(Member):
  - 이름과 임베디드 타입인 주소(Address), 그리고 주문(orders) 리스트를 가진다.

- 주문(Order):
  - 한 번 주문시 여러 상품을 주문할 수 있으므로 주문과 주문상품(OrderItem)은 일대다 관계다. 주문은 상품을 주문한 회원과 배송 정보, 주문 날짜, 주문 상태(status)를 가지고 있다. 주문 상태는 열거형을 사용했는데 주문(ORDER), 취소(CANCEL)을 표현할 수 있다.

- 주문상품(OrderItem):
  - 주문한 상품 정보와 주문 금액(orderPrice), 주문 수량(count) 정보를 가지고 있다.

- 상품(Item):
  - 이름, 가격, 재고수량( stockQuantity )을 가지고 있다. 상품을 주문하면 재고수량이 줄어든다. 상품의 종류로는 도서, 음반, 영화가 있는데 각각은 사용하는 속성이 조금씩 다르다.

- 배송(Delivery):
  - 주문시 하나의 배송 정보를 생성한다. 주문과 배송은 일대일 관계다.

- 카테고리(Category):
  - 상품과 다대다 관계를 맺는다. parent, child 로 부모, 자식 카테고리를 연결한다.

- 주소(Address):
  - 값 타입(임베디드 타입)이다. 회원과 배송(Delivery)에서 사용한다.

____

## ⏰ 프로젝트 회고

### 👍 좋았던 점

- 회원 상품 주문에 대해 도메인과 테이블을 설계해보며 공부하였습니다
- 회원 상품 주문 도메인의 비즈니스 로직을 개발하며 공부하였습니다
- 타임리프를 사용하여 웹 화경에서 동작하도록 공부하였습니다

### 🤦‍♂️ 아쉬웠던 점
- 상속관계 매핑 전략 (JOINED, SINGLE_TABLE, TABLE_PER_CLASS)을 잘 이해하지 못한 것이 아쉬움에 남습니다.
- 같은 엔티티 내에서 parent-child로 연관관계를 왜 설정하는지, 왜 필요한지 이해하지 못해 아쉬움이 남습니다.

## ⚙️ Environment
- Spring Boot 2.7.12
- Java 11
- H2 Database 1.4.199
