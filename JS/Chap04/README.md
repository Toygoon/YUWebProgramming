# Chapter 04. 반복문

<details>
<summary>Table of Contents</summary>

- [04-1 배열](#04-1-배열)
- [04-2-반복문](#04-2-반복문)

</details>

---

# 04-1 배열

## 배열 뒷부분에 요소 추가하기

- 배열 뒷부분에 요소를 추가할 때는 `push() 메소드를 사용합니다.

```
array.push(element);
```

## 인덱스를 사용해 배열 뒷부분에 요소 추가하기

- JavaScript에서 배열의 길이는 고정되어 있지 않다.
- 다음과 같이 3개 요소를 가진 배열을 만든 뒤, 10번째 인덱스에 요소를 강제로 추가할 수 있다.
- 이때, 4~9번째 인덱스는 아무 것도 없는 empty가 된다.

```
> const fruitsA = ['사과', '배', '바나나'];
< undefined

> fruitsA[10] = '귤';
< "귤"

> fruitsA
< (11) ["사과", "배", "바나나", empty * 7, "귤"]
```

## 배열 요소 제거하기

- 배열의 특정 인덱스에 있는 요소를 제거할 때는 `splice()` 메소드를 사용한다.
- 메소드는 `array.splice(index, number of elements to splice)` 형식으로 사용할 수 있다.
- 첫 번째 파라미터의 인덱스부터 두 번째 파라미터의 개수만큼 제거한다.

```
> const itemsA = ['사과', '배', '바나나'];
< undefined

> itemsA.splice(2, 1);
< ["바나나"]

> itemsA
< (2) ["사과", "배"]
```

## 배열의 특정 위치에 요소 추가하기

- 배열의 특정 위치에 요소를 추가할 때는 `splice()` 메소드를 사용한다.
- `splice()` 메소드의 2번째 매게변수에 0을 입력하면 `splice()` 메소드는 아무 것도 제거하지 않으며, 3번째 매개변수에 추가하고 싶은 요소를 입력할 수 있다.
- `array.splice(index, 0, element)`와 같이 사용할 수 있다.

```
> const itemsD = ['사과', '귤', '바나나', '오렌지'];
< undefined

> itemsD.splice(1, 0, "양파");
< []

> itemsD
< (5) ['사과', '양파', '귤', '바나나', '오렌지'];
```

## 4가지 키워드로 정리하는 핵심 포인트

- 여러 개의 변수를 한 번에 선언해 다룰 수 있는 자료형을 `배열`이라고 합니다.
- 배열 내부에 있는 값을 `요소`라고 합니다.
- `비파괴적 처리`란 처리 직후에 원본 내용이 변경되지 않는 처리를 의미합니다.
- `파괴적 처리`란 처리 후에 원본 내용이 변경되는 처리를 의미합니다.

## 확인 문제

### 1. 다음 배열들의 2번째 인덱스에 있는 값을 찾아보세요.

- (작성자) `두 번째 요소`면 [1]이고, `2번 인덱스`면 [2]인데, `2번째 인덱스`는 두 번째 요소인지? 2번 인덱스인지? 이는 결코 좋은 표기법이 아님.
- (작성자) `2번째 인덱스`를 인덱스가 가질 수 있는 숫자 중 두 번째 숫자로 간주하고, [1]의 요소를 찾아보도록 하겠음.

1. `["1", "2", "3", "4"]` : 2
2. `["사과", "배", "바나나", "귤", "감"]` : "배"
3. `[52, 273, 32, 103, 57]` : 273

### 2. 다음 코드의 실행 결과를 예측해보세요.

```
<script>
    const array = [1, 2, 3, 4];

    console.log(array.length);
    console.log(array.push(5));
</script>
```

- `const` 자료형은 수정이 불가하다.

### 3. 다음에 표시된 함수들이 파과적 처리를 하는지 비파괴적 처리를 하는지 구분해 맞는 것을 고르세요.

- (작성자) 아래에는 함수가 없습니다.

1. 비파괴적 처리

```
const strA = "사과,배,바나나,귤";
strA.split(",");
strA;
```

2. 파괴적 처리

```
const arrayB = ["사과", "배", "바나나", "귤"];
arrayB.push("감");
arrayB;
```

3. 비파괴적 처리

```
const arrayC = [1, 2, 3, 4, 5];
arrayC.map((x) => x * x);
arrayC
```

4. 비파괴적 처리

```
const strD = "  여백이 포함된 메시지   ";
strD.trim();
strD;
```

---

# 04-2 반복문

## for in 반복문

- 배열과 함께 사용할 수 있는 반복문은 `for in` 반복문이다.
- `for in` 반복문은 인덱스가 들어간다.

```
for (const INDEX in OBJECT) {
    statement;
}
```

## for of 반복문

- `for in` 반복문은 배열 요소를 하나하나 꺼내서 `Iterable` 객체를 `Iterate` 할 때 사용한다.

```
for (const VARIABLE of OBJECT) {
    statementt;
}
```

## 6가지 키워드로 정리하는 핵심 포인트

- `for in 반복문`은 배열의 인덱스를 기반으로 할 때 사용합니다.
- `for of 반복문`은 배열의 값을 기반으로 반복할 때 사용합니다.
- `for 반복문`은 횟수를 기반으로 반복할 때 사용합니다.
- `while 반복문`은 조건을 기반으로 반복할 때 사용합니다.
- `break` 키워드는 `switch` 조건문이나 반복문을 벗어날 때 사용합니다.
- `continue` 키워드는 반복문 안의 반복 작업을 멈추고 반복문의 처음으로 돌아가 다음 반복 작업을 진행합니다.

## 확인 문제

### 1. 다음 코드가 어떤 형태로 실행될지 예측해보세요.

```
<script>
    const array = ['사과', '배', '귤', '바나나'];

    console.log('# for in 반복문');
    for (const i in array) {
        console.log(i);
    }

    console.log('# for of 반복문');
    for (const i of array) {
        console.log(i);
    }
</script>
```

```
# for in 반복문
0
1
2
3
# for of 반복문
사과
배
귤
바나나
```

### 2. 다음 프로그램의 실행 결과를 예측해보세요. 혹시 오류가 발생한다면 어디를 수정해야 할까요?

```
<script>
    const array = [];

    for (const i = 0; i < 3; i++) {
        array.push((i + 1) * 3);
    }

    console.log(array);
</script>
```

- `for (const i = 0; i < 3; i++) {` 부분에서, `i` 값을 `const` 에 할당하고 있으므로 오류가 발생한다. `const`를 `let`으로 바꿔주어야 한다.

```
[3, 6, 9]
```

### 3. 1부터 100까지의 숫자를 곱한 값을 계산하는 프로그램을 만들어보세요. 그리고 코드를 실행해 나온 결과를 확인해 보세요.

```
<script>
    let output = 1;

    for (let i = 2; i < 101; i++) {
        output *= i;
    }

    console.log(`1~100의 숫자를 모두 곱하면, ${output}입니다.`);
</script>
```

```
1~100의 숫자를 모두 곱하면, 9332621544394415268169923885626670049071596826438162146859296389521759999322991560894146397615651828625369792082722375825118521091686400000000000000000000000입니다.
```

### 4. 활용 예제의 피라미드를 활용해서 다음과 같은 피라미드를 만들어보세요.

```
<script>
    let output = '';
    const size = 5;

    let tmp = 0, stars = [];
    const len = size * 2 - 1;
    for (let i = 1; i < size; i++) {
        stars.push(i + tmp);
        tmp++;
    }

    for (let i = size - 2; i >= 0; i--)
        stars.push(stars[i]);

    stars.splice(size - 1, 0, len);

    for (const i of stars) {
        output = '';
        const spaces = len - i;

        for (let j = 0; j < spaces / 2; j++)
            output += ' ';

        for (let j = 0; j < i; j++)
            output += '*';
        
        for (let j = 0; j < spaces / 2; j++)
            output += ' ';

        console.log(output);
    }
</script>
```

```
     *    
    ***   
   *****  
  ******* 
 *********
  ******* 
   *****  
    ***   
     *
```