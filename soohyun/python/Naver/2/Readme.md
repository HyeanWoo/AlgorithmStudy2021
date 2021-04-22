# 1. 문제의 핵심
1. DP
2. 걸린시간 약 1시간
3. 시작위치(답이 나와있는 지점)로부터 **좌측** 이동 **우측** 이동으로 분리해줘야함
4. **좌**로 진행할때와 **우**로 진행할때 식이 다름!

# 2. 알고리즘
## 2.1 알고리즘
```python
1. for 블록 in 피라미드 입력값:
2.     피라미드[제시된 위치] = 값 # 제시된 피라미드에 값넣어주기
3.     for 제시된 위치에서 왼쪽으로 가기
4.      현재위치에서 피라미드 다음값은 = 현재의 위값 - 현재값
5.     for 제시된 위치에서 오른쪽으로 가기
6.      현재위치에서 피라미드 이전값은 = 이전의 위값 - 현재값 
```
## 2.2 code snippet
```python
    pyramid[i][j] = value
    for k in range(j, i):
        pyramid[i][k+1] = pyramid[i-1][k] - pyramid[i][k]
    for k in range(j, 0, -1):
        pyramid[i][k-1] = pyramid[i-1][k-1] - pyramid[i][k] 
        continue
```


# 3. 시간 복잡도 및 공간 복잡도
1. 시간복잡도: O(n^2)
   - O(n): 모든 블록 순회
   - O(n/2): 좌우로 한번더 순회(nxn에서 절반만 순회)
2. 공간복잡도: O(n^2)
   - nxn피라미드를 저장

# 4. 복기할것
1. 인덱싱 처리 잘할것
2. 어떤값을 나눠야하는지 확인할것