**Big-O 표기법** : 알고리즘의 성능을 수학적으로 설명해주는 표기법

![escape](../img/escape.png)

상수 : 1

1. O(1) : 데이터가 증가함에 따른 성능 변화가 없다.

   ```python
   n = list(input())
   if n[0] == 0:
   	print(true)
   ```

   - 기울기가 0인 그래프

2. O(n) : 입력 데이터 크기와 비례하여 처리 시간이 증가한다.

   ```python
   n = int(input())
   for i in range(n):
   	print(i)
   ```

   - 그래프가 선형 그래프

3. O(n^2)

   ```python
   n = int(input())
   for i in range(n):
   	for j in range(n):
   		print(i+j)
   ```

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/187b440e-f6b1-447c-a8e8-9ca165fb9686/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/187b440e-f6b1-447c-a8e8-9ca165fb9686/Untitled.png)

   - n이 하나 늘어날 때마다 가로, 세로 한 줄씩 늘어남.
   - 그래프가 x≥0 인 2차함수의 형태

4. O(n^3)

   ```python
   n = int(input())
   for i in range(n):
   	for j in range(n):
   		for k in range(n):
   			print(i+j+k)
   ```

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d9d7c9b7-dd39-4630-9563-9070d8628ed2/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d9d7c9b7-dd39-4630-9563-9070d8628ed2/Untitled.png)

   - n이 하나 늘어날 때마다 가로, 세로, 높이 한 칸씩 늘어남.
   - O(n^2)와 같은 형태이지만 n이 증가함에 따라 더 급격히 증가.

5. O(2^n)

   - Fobonacci Numbers
   - 한 숫자를 호출하기 위해서 그 전단계의 2개의 수를 호출해야 한다. 이를 n번 반복

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2296d29f-8621-4833-9977-f19440fc8685/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2296d29f-8621-4833-9977-f19440fc8685/Untitled.png)

6. O(log n)

   - binary search(이진검색) 이 대표적이다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/55bc7dab-433b-418e-9720-94642f4c4791/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/55bc7dab-433b-418e-9720-94642f4c4791/Untitled.png)

   - key 값을 찾기 위해 배열의 중간값과 key값을 비교한다.
   - 한번 처리가 진행될 때마다 검색해야할 데이터 양이 1/2이 된다.

O(2n) ⇒ O(n)

- 실제 알고리즘의 러닝타임이 아니라, 장기적으로 데이터가 증가함에 따른 처리시간의 증가율을 예측한다.
- 상수는 고정된 숫자이기 때문에 증가하지 않는 숫자는 신경쓰지 않기 위해 상수 생략
- 이와 같이 O(n^2 + n^2) ⇒ O(n^2) 으로 표기한다.
