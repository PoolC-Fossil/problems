# 2024-02 동아리박람회용 제비뽑기 문제

![image](https://poolc.org/assets/main-banner-DAW2HCpy.png)

> [!NOTE]
> 일부 문제는 교육적이기보다 단순 재미를 주기 위한 용도가 더 크다는 점을 알립니다. 대표적으로 전공자 [4번](https://github.com/PoolC-Fossil/problems?tab=readme-ov-file#4-c17-%ED%91%9C%EC%A4%80%ED%95%98%EC%97%90%EC%84%9C-%EC%95%84%EB%9E%98-%EC%BD%94%EB%93%9C%EA%B0%80-%EC%84%B1%EA%B3%B5%EC%A0%81%EC%9C%BC%EB%A1%9C-%EC%BB%B4%ED%8C%8C%EC%9D%BC%EB%90%98%EA%B8%B0-%EC%9C%84%ED%95%B4-%EB%B9%88%EC%B9%B8%EC%97%90-%EB%93%A4%EC%96%B4%EA%B0%88-%EC%95%8C%EB%A7%9E%EC%9D%80-%EC%BD%94%EB%93%9C-%EC%A1%B0%ED%95%A9%EC%9D%802) 문제...

## 비전공자용 문제

> 비전공자: 프로그래밍 관련해서 어느 정도의 교양은 있지만 잘은 모르는 수준. 아직 실력이 부족한 신입부원을 모으는 것이 목적이므로, "동아리에 들어오면 이런 것을 배울 수 있다!"를 알려줄 수 있는 기본적인 문제들 위주. ~~어렵다...~~

### 1. 다음 Python 코드의 출력 결과는?

```python
a = [1, 2, 3]
b = a
a[0] = 10
print(b)
```

- 정답: [10, 2, 3]

<br>

### 2. 다음 Python 코드의 출력 결과는?

```python
a = [[1], [2, 3]]
b = a.copy()`
a[0][0] = 0
print(b)
```

- 정답: [[0], [2, 3]]

<br>

### 3. 다음 Python 코드의 출력 결과는?

```python
a = [1, 2, 3]
b = a
a = [4, 5, 6]
print(b)
```

- 정답: [1, 2, 3]

<br>

### 4. 다음 Python 코드의 출력 결과는?

```python
a = "Hello, World!"
print(a[:4])
```

- 정답: Hell

<br>

### 5. 다음 Python 코드의 실행 결과는?

```python
a = "Hello, World!"
a[1] = "a"
print(a)
```

- 보기

  1. 런타임 에러
  2. "Hallo, World!"가 출력됨

- 정답: 런타임 에러

<br>

## 전공자용 문제

> 전공자: 프로그래밍 및 컴퓨터 관련 내공이 어느 정도 쌓인 상태. 코테 문제를 풀리는 것도 괜찮을 듯[^1]. "동아리에 가입하면 확실히 취업, 실력 성장 관련해서 도움이 될수 있다"를 어필. ~~어렵네...~~

### 1. 다음 C 코드의 실행 결과는?

```c
#include <stdio.h>

int main() {
    int a[3] = {4, 5, 6};
    int (*p)[3] = &a;
    printf("%d\n", (*p)[0]);
    return 0;
}
```

- 보기

  1. 컴파일 에러
  2. Segmentation Fault
  3. 4가 출력됨

- 정답: 4가 출력됨

<br>

### 2. 다음 C 코드의 실행 결과는?

```c
#include <stdio.h>

int main() {
    int a[3] = {4, 5, 6};
    printf("%d\n", *(a + 1));
    return 0;
}
```

- 보기

  1. 컴파일 에러
  2. Segmentation Fault
  3. 4가 출력됨
  4. 5가 출력됨
  5. 6이 출력됨

- 정답: 5가 출력됨

<br>

### 3. 다음 C 코드의 실행 결과는?

```c
#include <stdio.h>

int main() {
    int a[3] = {4, 5, 6};
    printf("%d\n", 0[a]);
    return 0;
}
```

- 보기

  1. 컴파일 에러
  2. Segmentation Fault
  3. 4가 출력됨

- 정답: 4가 출력됨

<br>

### 4. C++17 표준하에서 아래 코드가 성공적으로 컴파일되기 위해 빈칸에 들어갈 알맞은 코드 조합은?[^2]

```c++
void (*signal(int _, void (*)(int)))(int) {
    return SECRET; // This macro expands to a right return value
}

int main() {
    ____ = signal(____);
    return 0;
}
```

- 보기 (C++17 기준)
  ||첫 번째 빈칸|두 번째 빈칸|
  |:---:|:---:|:---:|
  |(a)|`void fp`|`0, [] { return 0; }`|
  |(b)|`void *fp`|`0, [](int x) { return; }`|
  |(c)|`void (*fp)(int)`|`&(int){0}, [](int x) { return; }`|
  |(d)|`void *(*fp)(int)`|`0, [](int x) { return &(int){0}; }`|

  - 기타 (위 보기와는 전혀 다른 형태의 정답을 떠올리셨다면?)

- 정답:

  1. 첫 번째 빈칸: (c), 두 번째 빈칸: (b)
  2. 기타 선택 후, 첫 번째 빈칸: `//`, 두 번째 빈칸: 어떤 걸 적냐에 상관 없이 정답 처리

<br>

[^1]: 코테 문제를 풀리려면 적어도 타자를 칠 수 있는 환경이어야 하는데, 동박 부스에서 이게 가능할지 잘 모르겠음. 또 기본적으로 문제 명세가 짧지 않기 때문에, 빈칸 뚫기 형식으로도 적합할지는 잘 모르겠음.
[^2]: ~~출제자가 자리를 비울 경우 주관식으로 서술한 "기타" 내용에 대한 채점이 어려울 것으로 예상됨. 일부 문제에 한해서는 노트북을 준비해두고, 직접 실행시켜 컴파일 에러 시 실패, 이외의 경우 성공으로 하는 것이 나을 수도 있을 것이라 생각됨. 회의 필요.~~ 지나치게 귀찮은 일이 많아질 듯함.
