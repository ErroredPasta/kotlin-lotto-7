# kotlin-lotto-precourse

## 프로젝트 개요

이 프로젝트는 간단한 로또 발매기를 구현한 것입니다. 사용자가 입력한 금액에 따라 로또 번호를 발행하고, 당첨 번호를 입력받아 당첨 결과와 수익률을 계산합니다.

---

## 기능 요구 사항

1. **금액 입력**
    - 금액을 정수형으로 입력하지 않으면 예외 발생
    - 금액이 1000원으로 나누어떨어지지 않으면 예외 발생
    - 금액이 0 이하일 경우 예외 발생
2. **금액에 따른 로또 번호 생성**
    - 금액을 1000원으로 나눈만큼 랜덤으로 로또 번호를 생성
    - 하나의 로또 번호는 중복 없이 랜덤으로 6개 생성
        - 유효한 로또 번호는 1부터 45 사이의 숫자
3. **로또 당첨 번호 입력**
    - 로또 당첨 번호는 쉼표(,)로 구분된 6개의 숫자
    - 위의 양식을 지키지 않는 경우 예외 발생
    - 당첨 번호 중 1부터 45 사이의 숫자가 아닌 것이 있으면 예외 발생
4. **보너스 번호 입력**
    - 당첨 번호와 마찬가지로 1부터 45 사이의 숫자가 아닌 것이 있으면 예외 발생
5. **결과 출력**
    - 생성된 로또와 당첨 번호로 당첨 결과 출력
6. **수익률 출력**
    - `당첨 금액 / 로또 구매 금액 * 100`으로 수익률을 계산하여 출력
        - 수익률은 소수점 둘째 자리에서 반올림
7. **예외 처리**
    - 사용자가 잘못된 값을 입력시 알맞은 예외를 발생시키고 에러 메시지 출력 후 입력을 다시 받음
        - 에러 메시지는 "[ERROR]"로 시작

---

## 입출력 요구 사항

### 입력

- **구입 금액** : 1,000원 단위로 입력, 1,000으로 나누어 떨어지지 않는 경우 예외 처리
  ```plaintext
  14000
  ```

- **당첨 번호** : 쉼표(,)로 구분된 6개의 숫자 입력

   ```plaintext
   1,2,3,4,5,6
   ```

- **보너스 번호** : 하나의 숫자 입력

   ```plaintext
   7
   ```

### 출력

- **발행 로또 번호** : 구매한 로또 수량과 각 번호를 오름차순으로 출력

    ```plaintext
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

- **당첨 내역 및 수익률**: 각 당첨 등수별 일치 개수와 수익률 출력

    ```plaintext
    3개 일치 (5,000원) - 1개
    4개 일치 (50,000원) - 0개
    5개 일치 (1,500,000원) - 0개
    5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
    6개 일치 (2,000,000,000원) - 0개
    총 수익률은 62.5%입니다.
    ```

- 에러 메시지: 유효하지 않은 값 입력 시 에러 메시지 출력

   ```plaintext
   [ERROR] 로또 번호는 1부터 45 사이의 숫자여야 합니다.
   ```

### 실행 예시

```plaintext
구입금액을 입력해 주세요.
8000

8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]

당첨 번호를 입력해 주세요.
1,2,3,4,5,6

보너스 번호를 입력해 주세요.
7

당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```