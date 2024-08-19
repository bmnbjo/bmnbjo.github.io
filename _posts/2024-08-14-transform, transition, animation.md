`transform`은 요소의 상태를 변경하는 기능적 속성으로, 요소의 위치, 크기, 회전 등을 조절합니다.

`transition`은 요소의 상태 변화에 애니메이션을 추가하여 변화를 시각적으로 부드럽게 만들어주는 속성입니다.



# Transform

### 1. 이동 (Translation)

- **개념**: 요소를 X, Y, Z 축을 기준으로 이동시키는 것입니다.

- 속성

  - `translateX(n)`: X축 방향으로 `n`만큼 이동합니다.

  - `translateY(n)`: Y축 방향으로 `n`만큼 이동합니다.

  - `translateZ(n)`: Z축 방향으로 `n`만큼 이동합니다.

  - `translate(x, y)`: X축과 Y축을 기준으로 이동합니다.

  - `translate3d(x, y, z)`: X, Y, Z축을 기준으로 이동합니다.

  - 예시

    ```
    transform: translateX(100px);
    transform: translateY(-150px);
    transform: translate(250px, -200px);
    transform: translate3d(-150px, -100px, 100px);
    ```

### 2. 회전 (Rotation)

- **개념**: 요소를 특정 축을 기준으로 회전시키는 것입니다.

- 속성

  - `rotateZ(angle)`: Z축을 기준으로 회전합니다.

  - `rotateX(angle)`: X축을 기준으로 회전합니다.

  - `rotateY(angle)`: Y축을 기준으로 회전합니다.

  - `rotate3d(x, y, z, angle)`: (x, y, z) 벡터를 기준으로 `angle`만큼 회전합니다.

  - 예시

    ```
    transform: rotateZ(30deg);
    transform: rotateX(60deg);
    transform: rotateY(60deg);
    transform: rotate3d(1,0,0,60deg);
    ```

### 3. 확대/축소 (Scaling)

- **개념**: 요소의 크기를 변경합니다.

- 속성

  - `scaleX(n)`: X축 방향으로 `n`배 확대/축소합니다.

  - `scaleY(n)`: Y축 방향으로 `n`배 확대/축소합니다.

  - `scaleZ(n)`: Z축 방향으로 `n`배 확대/축소합니다.

  - `scale3d(x, y, z)`: X, Y, Z 축을 기준으로 확대/축소합니다.

  - `scale(x, y)`: X, Y 축을 기준으로 확대/축소합니다.

  - 예시

    ```
    transform: scaleX(2);
    transform: scale(2, 0.3);
    ```

### 4. 비틀기 (Skew)

- **개념**: 요소를 특정 축을 기준으로 기울이는 것입니다.

- 속성

  - `skewX(angle)`: X축 방향으로 기울입니다.

  - `skewY(angle)`: Y축 방향으로 기울입니다.

  - `skew(x-angle, y-angle)`: X축과 Y축을 기준으로 기울입니다.

  - 예시

    ```
    transform: skewX(30deg);
    transform: skewY(30deg);
    transform: skew(30deg, 15deg);
    ```

### 5. 복합 변형

- **개념**: 여러 변형을 조합하여 적용할 수 있습니다.

- 속성

  - 변형은 공백으로 구분하여 나열할 수 있습니다.

  - 예시

    ```
    transform: translate(200px, -100px); rotate(45deg) scale(0.7, 2);
    ```

### 6. 원근감 (Perspective)

- **개념**: 3D 공간에서 깊이감을 부여하는 속성입니다.
- 속성
  - `perspective(n)`: 원근감을 설정합니다. `n` 값이 작을수록 더 강한 원근감을 제공합니다.
  - `transform: perspective(100px) rotateX(60deg);`







# transition

### 1. `transition`

- **개념**: `transition` 속성은 CSS 속성이 변경될 때 애니메이션 효과를 추가합니다. 여러 트랜지션 속성을 한 번에 설정할 수 있는 축약형 문법입니다.

- 구문

  ```
  transition: [property] [duration] [timing-function] [delay];
  ```

- 예시

  ```
  div {
    transition: all 2s ease-in-out;
  }
  ```

### 2. `transition-property`

- **개념**: 애니메이션 효과를 적용할 CSS 속성을 지정합니다. `all`을 지정하면 모든 변경 가능한 속성에 트랜지션이 적용됩니다.

- 주요 값

  - `all`: 모든 속성에 대해 트랜지션을 적용합니다.
  - 특정 속성: 예를 들어, `width`, `left` 등.

- 예시

  ```
  div {
    transition-property: width, height;
  }
  ```

### 3. `transition-duration`

- **개념**: 트랜지션이 완료되기까지의 시간을 설정합니다. `s` (초) 또는 `ms` (밀리초) 단위를 사용합니다.

- 주요 값

  - `2s`: 2초
  - `500ms`: 500밀리초

- 예시

  ```
  div {
    transition-duration: 2s;
  }
  ```

### 4. `transition-timing-function`

- **개념**: 트랜지션의 속도 곡선을 설정합니다. 이 속성은 트랜지션의 진행 속도를 제어하여 애니메이션의 느낌을 조절합니다.

- 주요 값

  - `ease`: 시작은 느리고 끝은 느린 기본값
  - `linear`: 일정한 속도로 진행
  - `ease-in`: 시작이 느리고 끝은 빠름
  - `ease-out`: 시작이 빠르고 끝은 느림
  - `ease-in-out`: 시작과 끝이 느리고 중간이 빠름
  - `cubic-bezier(x1, y1, x2, y2)`: 커스텀 속도 곡선
  - `steps(n, [start|end])`: n 단계의 구간을 정해 애니메이션을 분할

- 예시

  ```
  div {
    transition-timing-function: ease-in-out;
  }
  ```

### 5. `transition-delay`

- **개념**: 트랜지션이 시작되기 전 대기할 시간을 설정합니다. `s` (초) 또는 `ms` (밀리초) 단위를 사용합니다.

- 주요 값

  - `1s`: 1초 대기
  - `0s`: 즉시 시작

- 예시

  ```
  div {
    transition-delay: 1s;
  }
  ```

### 

# animation

### 1. `@keyframes` 정의

- `@keyframes`는 애니메이션의 각 단계에서 스타일 변화를 정의하는 규칙입니다.

- `from`과 `to` 또는 `0%`에서 `100%`까지의 중간 단계를 정의할 수 있습니다.

- 예시:

  ```
  @keyframes leftToRight {
      from {
          left: 100px;
      }
      to {
          left: 300px;
      }
  }
  ```

### 2. `animation-name` & `animation-duration`

- `animation-name` 속성은 적용할 애니메이션의 이름을 지정합니다.

- `animation-duration` 속성은 애니메이션이 한 번 실행되는 데 걸리는 시간을 설정합니다.

- 예시:

  ```
  wrapper:nth-of-type(1) > div:nth-child(1){
      animation-name: leftToRight;
      animation-duration: 3s;
  }
  ```

### 3. `animation-iteration-count`

- 애니메이션이 몇 번 반복될지를 지정하는 속성입니다.

- `infinite` 값으로 설정하면 무한히 반복됩니다.

- 예시:

  ```
  wrapper:nth-of-type(2) > div:nth-child(3){
      animation-name: leftToRight;
      animation-duration: 3s;
      animation-iteration-count: infinite;
  }
  ```

### 4. `animation-direction`

- 애니메이션의 재생 방향을 설정합니다.

  - `normal`: 기본 방향.
  - `reverse`: 역방향.
  - `alternate`: 번갈아 가며 방향을 전환 (홀수는 정방향, 짝수는 역방향).
  - `alternate-reverse`: `alternate`와 비슷하나 홀수는 역방향, 짝수는 정방향.

- 예시:

  ```
  wrapper:nth-of-type(3) > div:nth-child(3){
      animation-name: leftToRight;
      animation-duration: 3s;
      animation-direction: alternate;
      animation-iteration-count: 3;
  }
  ```

### 5. `animation-play-state`

- 애니메이션의 재생 상태를 제어합니다.

  - `running`: 실행 중 (기본값).
  - `paused`: 일시 정지.

- 예시:

  ```
  wrapper:nth-of-type(4) > div:nth-of-type(1):hover{
      animation-play-state: paused; /* 마우스 오버 시 일시 정지 */
  }
  ```

### 6. `animation-fill-mode`

- 애니메이션이 시작 전이나 끝난 후에 어떤 스타일을 적용할지를 결정합니다.

  - `none`: 아무 것도 적용하지 않음 (기본값).
  - `forwards`: 애니메이션이 끝난 후 마지막 프레임의 스타일 유지.
  - `backwards`: 애니메이션 시작 전 첫 번째 프레임의 스타일을 적용.
  - `both`: `forwards`와 `backwards`를 모두 적용.

- 예시:

  ```
  wrapper:nth-of-type(5) > div:nth-of-type(2){
      animation-fill-mode: forwards;
  }
  ```

### 7. `animation` (단축 속성)

- `animation` 속성은 애니메이션에 관련된 모든 속성을 한 번에 설정할 수 있는 단축 속성입니다.

- 구성 요소:

  - `animation-name`: 애니메이션 이름.
  - `animation-duration`: 지속 시간.
  - `animation-timing-function`: 타이밍 함수.
  - `animation-delay`: 지연 시간.
  - `animation-iteration-count`: 반복 횟수.
  - `animation-direction`: 재생 방향.
  - `animation-fill-mode`: 필 모드.
  - `animation-play-state`: 재생 상태.

  