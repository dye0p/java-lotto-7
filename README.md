# java-lotto-precourse

---

## 프로그램 소개

로또를 구입해 당첨번호와 비교하여 당첨내역을 확인하고 수익률을 계산하는
간단한 로또 발매기 프로그램 입니다.

## 프로그램 사용 가이드

아래는 프로그램의 사용 예시 입니다. (입력값은 예시 입니다.)
기능에 대한 사항은 구현 기능 목록을 통해서 확인하실 수 있습니다.

1. 로또 구입 금액을 입력 합니다. (구입 금액은 1,000원 단위로 입력해야 합니다.)

```
구입금액을 입력해 주세요.
8000
```

구입 금액을 입력했다면 다음과 같이 구입한 금액만큼 로또 번호가 발행되어 안내됩니다.

```
8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]
```

2. 당첨 번호를 입력 합니다. (번호는 쉼표(,)로 구분해야 합니다.)

``` 
당첨 번호를 입력해 주세요.
1,2,3,4,5,6
```

3. 보너스 번호를 입력 합니다.

```
보너스 번호를 입력해 주세요.
7
```

4. 보너스 번호까지 입력을 마쳤다면 당첨 통계와 총 수익률을 확인할 수 있습니다.
   (수익률은 소수점 첫재짜리까지 표시됩니다.)

```
당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```

## 구현 기능 목록

---

### 입력 기능

- [x] 로또 구입 금액을 입력 받는 기능
    - 구입 금액은 1000원 단위로 입력 받을수 있어야 한다.
- [x] 당첨 번호를 입력 받는 기능
    - 당첨 번호는 쉼표(,)를 기준으로 구분하여 입력 받을 수 있어야 한다.
- [x] 보너스 번호를 입력 받는 기능

### 핵심 기능

- [x] 구입한 금액을 1000원 단위로 나누어 수량을 계산하는 기능
- [x] 구입한 수량 만큼 로또를 발행하는 기능
- [x] 발행된 로또를 오름차순으로 정렬하는 기능
- [x] 입력한 당첨 번호와 보너스 번호로 로또 번호를 맞추는 기능
- [x] 1등부터 5등까지 당첨 내역을 집계하는 기능
- [x] 총 수익률을 계산하는 기능
- [x] 잘못된 입력을 할 경우 `IllegalArgumentException`을 발생시키고, "[ERROR]"로 시작하는 에러 메세지를 출력 후 그 부분부터 다시 입력을 받는 기능
    - `Exception`이 아닌 `llegalArgumentException`, `IllegalStateException` 등과 같은 명확한 유형으로 처리해야 한다.

### 출력 기능

- [x] 발행한 로또 수량 및 로또 번호를 출력하는 기능
    - 로또 번호는 오름차순으로 정렬하여 보여줄 수 있어야 한다.
- [x] 당첨 내역을 출력하는 기능
- [ ] 총 수익률을 출력하는 기능
    - 수익률은 소수점 둘째 자리에서 반올림하여 보여줄 수 있어야 한다.
- [x] 예외 상황 시 에러 문구를 출력하는 기능
    - 에러 문구는 "[ERROR]"로 시작해야 한다.

### 예외 상황

잘못된 입력으로 인해 예외가 발생할 경우 `IllegalArgumentException` 을 발생시키고, 예외 메세지를 출력한 후, 그 부분부터 다시 입력 받을 수 있다.

예외 메세지 출력 예시

```
[ERROR] 로또 번호는 1부터 45 사이의 숫자여야 합니다.
```

공통 예외 상황

- [x] 공백을 입력한 경우
- [x] null 또는 빈 값을 입력한 경우

잘못된 금액 입력에 대한 예외 상황

- [x] 구입 금액이 1000원 단위로 나누어 떨어지지 않는 경우
- [x] 숫자가 아닌 문자를 입력한 경우

잘못된 당첨 번호(로또 번호) 입력에 대한 예외 상황

- [x] 1~45의 범위가 아닌 당첨 번호(로또 번호)를 입력한 경우
- [x] 입력한 당첨 번호(로또 번호)가 6개가 아닌 경우
- [x] 중복된 당첨 번호(로또 번호)를 입력한 경우
- [x] 당첨 번호(로또 번호)를 쉼표(,)로 구분하지 않은 경우
- [x] 숫자가 아닌 문자를 입력한 경우
- [x] 쉼표(,)를 연속해서 입력한 경우

잘못된 보너스 번호 입력에 대한 예외 상황

- [x] 1~45의 범위가 아닌 보너스 번호를 입력한 경우
- [x] 입력한 보너스 번호가 1개가 아닐때
- [x] 입력한 당첨 번호와 중복되는 보너스 번호를 입력한 경우

## 프로그램 흐름도

---

1. 구입 금액을 입력 받는다.
2. 구입한 수량과 발행된 로또 번호를 출력한다.
2. 당첨 번호를 입력 받는다.
3. 보너스 번호를 입력 받는다.
4. 당첨 번호와 보너스 번호를 이용해 로또 번호를 맞춘다.
5. 1등부터 5등까지 당첨 내역을 집계한다.
6. 당첨 통계를 출력한다.
7. 총 수익률을 계산하여 출력한다.



