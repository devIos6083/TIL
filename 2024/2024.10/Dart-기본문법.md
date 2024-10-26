- 주석 처리하기
1. 한 줄 주석: //를 사용합니다.
```
// 한 줄 주석입니다.
```
2. 여러 줄 주석: /* ... */를 사용합니다.
```
/*
 * 여러 줄 주석입니다.
 */

```
- Print 함수 : print 함수를 통해 콘솔에 문자열이나 변수를 출력할 수 있습니다.

```
void main() {
  print("Hello world!"); // Hello world! 출력
}
```
- 변수 선언 및 사용
1. 변수 선언: var 키워드를 사용해 변수를 선언할 수 있으며, 선언 시 값에 따라 타입이 결정됩니다.

```
void main() {
  var name = "강홍규";
  print(name); // "강홍규" 출력

  // 변수 값 변경하기
  name = "코드 팩토리";
  print(name); // "코드 팩토리" 출력
}
```

2. Dynamic 타입 변수 선언: dynamic 키워드를 사용하면 변수의 타입이 자동으로 유추됩니다. 타입을 동적으로 변경할 수 있어 유연하지만, 런타임 에러가 발생할 수 있으므로 주의가 필요합니다.

```
void main() {
  dynamic name = "코드 팩토리";
  name = 1; // 정수로 변경
  print(name); // 1 출력

  // 변수 타입 출력
  print(name.runtimeType); // int 출력
}
```

3. Final / Const
* 공통점: final과 const 모두 선언 후 값을 변경할 수 없습니다.
* 차이점:
final: 런타임에 값이 할당되는 상수입니다.
const: 빌드 시점에 값이 할당되는 상수입니다.

```
void main() {
  final String name = "블랙핑크";
  // name = "BTS"; // 에러 발생

  const String name2 = "2NE1";
  // name2 = "빅뱅"; // 에러 발생
}

// 예제: DateTime.now() 함수를 이용한 final과 const의 차이
void main() {
  final DateTime now = DateTime.now();
  print(now); // 런타임 시점에 실행 가능

  // const DateTime now = DateTime.now(); // 에러 발생
}
```

4. Dart 데이터 타입
문자열: String
정수형: int
실수형: double
불린형: bool

* 리스트 (List)
1. 리스트 선언 및 접근

```
void main() {
  List<String> blackPink = ["지수", "제니", "로제", "리사"];
  
  // 인덱스로 접근
  print(blackPink[0]); // 지수 출력
  print(blackPink[3]); // 리사 출력
  
  // 리스트 길이 반환
  print(blackPink.length); // 4 출력

  // 인덱스를 통해 값 변경
  blackPink[3] = "홍규";
  print(blackPink); // ["지수", "제니", "로제", "홍규"] 출력
}
```

* 맵 (Map) : Map은 키-값 쌍을 저장합니다.

```
void main() {
  Map<String, int> dictionary = {
    "one": 1,
    "two": 2,
    "three": 3,
    "four": 4
  };

  // 키를 이용해 값 삭제
  dictionary.remove("one"); 
  print(dictionary); // {"two": 2, "three": 3, "four": 4} 출력

  // 모든 키 출력
  print(dictionary.keys); // (two, three, four)

  // 모든 값 출력
  print(dictionary.values); // (2, 3, 4)
}
```
* 세트 (Set) : Set은 중복을 허용하지 않는 자료구조입니다.

```
void main() {
  Set<String> blackPink = {"지수", "로제", "리사", "제니"};
  
  // 값이 있는지 확인
  print(blackPink.contains("지수")); // true 출력

  // 리스트로 변환
  print(blackPink.toList()); // ["지수", "로제", "리사", "제니"] 출력
}
```
* Null 허용 변수 선언 : ?를 사용해 null 값을 가질 수 있는 변수를 선언할 수 있습니다.

```
void main() {
  int? num1 = 1;
  int? num2 = null;
  
  print(num1); // 1 출력
  print(num2 ??= 4); // null인 경우 4 할당하고 출력, 결과: 4
}
```

* ?? 연산자 : 변수에 null이 할당된 경우 대체 값을 제공합니다.

```
int? num = null;
print(num ?? 10); // num이 null이므로 10이 출력됩니다.
```
* 타입 비교 연산자 : is 키워드를 사용해 변수의 타입을 확인할 수 있습니다.

```
print(num1 is int); // num1이 int 타입이면 true 출력
```

* 논리 연산자
AND (&&) 연산자: 양쪽 조건이 모두 참일 때 true.
OR (||) 연산자: 하나 이상의 조건이 참일 때 true.

```
print(num1 > 0 && num2 > 0); // false 출력
print(num1 > 0 || num2 > 0); // true 출력
```

* 제어문
1. if 문: 3의 배수인지 확인

```
void main() {
  int num = 3;
  if (num % 3 == 0) {
    print("3의 배수입니다.");
  } else {
    print("3의 배수가 아닙니다.");
  }
}
```
2. switch 문: 3으로 나눈 나머지에 따라 결과 출력

```
int num2 = 5;
switch (num2 % 3) {
  case 0:
    print("3의 배수입니다.");
    break;
  case 1:
    print("나머지가 1이고 3의 배수가 아님");
    break;
  case 2:
    print("나머지가 2이고 3의 배수가 아님");
    break;
}
```
3. for 문: 0, 1, 2 출력

```
for (int i = 0; i < 3; i++) {
  print(i); // 0, 1, 2 출력
}
```
4. for-each 문: 리스트의 요소를 하나씩 출력

```
List<int> numL = [3, 6, 9];
for (int x in numL) {
  print(x); // 3, 6, 9 출력
}
```

5. while 문: 0부터 10까지 출력

```
int num3 = 0;
while (num3 <= 10) {
  print(num3); // 0부터 10까지 출력
  num3++;
}
```

* 함수 (Function)
1. 매개변수 두 개를 받아 더하는 함수

```
int addNumTwo(int a, int b) {
  return a + b;
}

void main() {
  print(addNumTwo(3, 4)); // 7 출력
}
```
2. 네임드 파라미터 함수

```
int addNumTwo({
  required int a,
  required int b,
}) {
  return a + b;
}

void main() {
  print(addNumTwo(a: 1, b: 2)); // 3 출력
}
```
3. 옵셔널 파라미터 함수

```
int addNumTwo(int a, [int b = 2]) {
  return a + b;
}

void main() {
  print(addNumTwo(1)); // 3 출력
}
```

4. 포지셔널 및 네임드 파라미터 혼합 사용

```
int addThreeNum(
  int a, {
    required int b,
    int c = 4,
  }) {
  return a + b + c;
}

void main() {
  print(addThreeNum(1, b: 2, c: 4)); // 7 출력
}
```

* 커스텀 타입 정의 (typedef)와 사용자 정의 연산자
typedef: 사용자 정의 타입을 정의하여 반복되는 함수 타입을 간편하게 사용할 수 있습니다.

```
void add(int x, int y) {
  print("결과값: ${x + y}");
}

void sub(int x, int y) {
  print("결과값: ${x - y}");
}

typedef operation = void Function(int x, int y);

void main() {
  operation oper = add;
  oper(1, 2); // 결과값: 3 출력

  oper = sub;
  oper(5, 2); // 결과값: 3 출력
}
```