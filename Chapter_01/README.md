﻿# Chapter_01 컴퓨터 구조

컴퓨터 구조는 컴퓨터 시스템이 어떻게 동작하고, 하드웨어와 소프트웨어가 상호작용하여
데이터를 처리하는지 설명하는 학문입니다. 컴퓨터는 **중앙 처리 장치(CPU), 메모리**, **입출력 장치(I/O Devices)** 
의 협력을 통해 작업을 수행하며, 이들 구성 요소는 시스템 버스를 통해 연결됩니다.

## 컴퓨터가 이해하는 정보
컴퓨터는 **디지털 전자 장치**로, 모든 정보를 **0과 1로 표현되는 이진법(Binary System)** 형태로
처리합니다. 컴퓨터는 우리가 사용하는 문자, 숫자, 이미지, 소리와 같은 데이터를 **이진 코드(Binary Code)** 로
변환하여 저장하고 처리합니다. 이 과정에서 데이터를 이해하고 처리하기 위한 다양한 **인코딩 방식과 변환 기술**이 사용됩니다.

### 1-1 컴퓨터가 데이터를 이해하는 방식

컴퓨터는 기본적으로 전자의 두 가지 상태(켜짐과 꺼짐,1과 0)를 사용하여 데이터를 표현합니다.
여기서 1과 0을 나타내는 가장 작은 정보의 단위를 비트라고 합니다. 1비트는 0 또는 1, 2개의 정보를 표현할 수 있고
2비트는 4개의 정보, 3비트는 8개의 정보를 표현할 수 있습니다. 즉, N비트는 2^n개의 정보를 표현할 수 있습니다.

**바이트**는 여덟 비트를 뭈은 단위를 말하므로 하나의 바이트로 표현할 수 있는 정보는 2^8= 256개입니다.
킬로바이트, 메가바이트, 기가바이트, 테라바이트 단위는 모두 이전 단위 1,024개를 묵은 단위를 말합니다.
CPU 관점에서의 정보 단위로는 워드가 있습니다. **워드(Word)** 란 CPU가 한 번에 처리할 수 있는 데이터의 크기를 의미합니다.
프로그램의 크기가 2GB라고 해서 CPU도 한번에 2GB의 데이터를 처리하는 것이 아니라 프로그램을 워드 단위로 읽어드리고 처리합니다.
워드에 크기는 CPU마다 다르지만 현대 컴퓨터 대부분의 워드 크기는 32비트, 64비트입니다.

| 구분     | 비트         |
|--------|------------|
| 1 byte | 8비트        |
| 1 kB   | 1024 바이트   |
| 1 MB   | 1024 킬로바이트 |
| 1 GB   | 1024 메가바이트 |
| 1 TB   | 1024 기가바이트 |              

### 1-2 데이터 - 0과 1로 숫자 표현하기

컴퓨터에서는 **2진법**을 사용해 2 이상, 0 이하의 수를 이해합니다. 우기라 일상적으로 사용하는 **10진법**이
**숫자 9를 넘어가는 시점에 자리올림**해서 0부터 9까지 10개의 숫자만으로 모든 수를 표현하듯, 컴퓨터가 사용하는 2진법 또한 
**숫자 1을 넘어가는 시점에 자리올림**해서 0과 1, 2개의 숫자만으로 모든 수를 표현합니다.
2진수로 표현된 수는 숫자 뒤에 아래첨자로 (2)를 붙이거나 2진수 앞에 0b를 붙입니다.

이번에는 컴퓨터 내부에서 2진수로 **소수를 나타내는 방법**을 알아봅시다. 컴퓨터의 소수 표현을 학습할 때 
가장 중요한 핵심은 표현하고자 하는 소수와 실제로 저장된 소수 간에 오차가 존재할 수 있다는 점입니다.
이는 매우 단순한 코드 실행을 통해서 확인할 수 있는데 Python 코드를 예로 설명하겠습니다.

```python
a = 0.1
b = 0.2
c = 0.3

if a + b == c:
    print("Equal")
else:
    print("Not Equal")
```

제시된 코드의 결과는 당연히 "Equal"일 것이라고 생각할 수 있지만, 결과는 "Not Equal"입니다.
이러한 오차가 발생하는 이유는 컴퓨터 내부에서는 소수점을 나타내기 위해 대표적으로 **부동 소수점** 표현 방식을 
이용하는데, 이 방식의 정밀도에 한계가 있기 때문입니다. **부동 소수점**은 소수점이 고정되어 있지 않은 소수 표현 방식으로, 필요에 따라 소수점의
위치가 이동할 수 있고 유동적(Floating)이라는 의미에서 부동 소수점이라는 이름을 붙혔습니다.

예를 들어 10진수 123.123이라는 수를 **m*10^n**의 꼴로 나타내면 1.23123 * 10^2으로 표현할 수도 있고,
1231.23 * 10^-1으로 표현할 수도 있습니다. 여기서 제곱으로 표현된 2와 -1을 **지수**, 1.23123과 1231.23을 **가수**라고 합니다.
이로써 소수점의 위치를 고정하지 않고도 같은 소수를 다양하게 표현할 수 있다는 사실을 알 수 있습니다.

2진수 체계에서는 소수를 이와 유사하게 m * 2^n의 꼴로 나타냅니다. 가령 107.6640625라는 수를 2진수로 나타내면
1101011.1010101입니다. 이 2진수의 소수는 1.1010111010101 * 2^6으로 표현할 수도 있고, 110101110.10101 * 2^-2으로 표현할 수도 있습니다.
2의 지수가 양수일 때는 **2^(소수점을 왼쫀으로 이동한 횟수)**, 2의 지수가 음수일 때는 **2^(소수점을 오른쪽으로 이동한 횟수)** 라고 생각해도 됩니다.

오늘날 대부분의 컴퓨터는 2진수의 지수와 가수를 다음과 같은 형식으로 저장합니다. 이를 **IEEE 754**라고 합니다.
![image_001.png](../asset/image_001.png)

그림과 같은 형태로 소수가 저장된다고 할 때, 가수의 정수부에는 1로 통일된 **정규화한 수**가 저장됩니다. 즉, 가수는 1.****의 형태를 띄고 있습니다.
앞서 예로 들었던 2진수 1101011.1010101의 경우 110101110.10101 * 2^-2이 아닌 1.1010111010101 * 2^6으로 저장되는 셈입니다.

그럼 2^지수 * 1.**** 형태의 소수를 저장할 때는 **지수**에 해당하는 값과 *****에 해당하는 소수 부분만 저장하면 됩니다.
따라서 컴퓨터가 1.1010111010101 * 2^6의 가수를 저장할 때는 1010111010101이 저장되는 것입니다.

컴퓨터가 지수를 저장할 대는 **바이어스** 값이 더해져서 저장되며, 이때 바이어스 값은 2^k-1 - 1(k는 지수의 비트 수)입니다.
지수를 표현하기 위해 8비트가 사용되었다면 바이어스 값은 2^7-1인 127이고, 11비트가 사용되었다면 바이어스 값은 2^10-1인 1.023입니다.
즉, 1.1010111010101 * 2^6이 32비트로 저장될 때는 127+6인 133(2진수 10000101)으로 저장되는 셈입니다.

여기서 유의할 점은 **10진수 소수를 2진수로 표현할 때, 10진수 소수와 2진수 소수의 표현이 딱 맞아떨어지지 않을 수 있다**는 점입니다.
예를 들어 1/3이라는 분수를 **m * 3^n**의 꼴로 나타내고 싶다면 간단하게 1 * 3^-1으로 표현하면 됩니다. 
하지만 이 분수를 10진수로 표현하기 위해 m * 10^n의 꼴로 나타내기는 어렵습니다.
1/ 3이라는 분수를 10진수로 표현하려면 0.33333.... 처럼 무한히 많은 소수점이 필요하기 떄문입니다.
컴퓨터의 저장 공간은 한정적이기 때문에 무한히 많은 소수점을 저장할 수는 없습니다. 그래서 딱 맞아 떨어지지지 않는 
소수를 표현할 때는 일부 소수점을 생략하여 저장합니다. 그래서 앞에서와 같은 오차가 발생하는 것입니다.


### 1-3 데이터 - 0과 1로 문자 표현하기

컴퓨터가 이해할 수 있는문자들의 집합을 **문자 집합**이라고 합니다. 그리고 문자 집합에 속한 문자를 컴퓨터가 이해하는 
0과 1로 이루어진 문자 코드로 변환하는 과정을 **문자 인코딩**이라고 합니다. 동일한 문자 집합이라고 다양한 문자 인코딩 방법이 있을 수 있습니다.
반대로, 0과 1로 표현된 문자를 사람이 이해하는 문자로 변환하는 과정은 **문자 디코딩**이라고 합니다.