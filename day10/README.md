오늘은 제가 예전에 틀렸던 문제들이나 오래 걸렸던 문제들을 다시 풀어보는 시간을 가졌습니다.


# 1. 디펜스 게임
### 내가 생각한 풀이는 
1. 우선 먼저 목숨을 쓰고 통과할 수 있는 라운드 까지 감
2. 1번에 이어서 무적권까지 쓰고 갈 수 있는 라운드 까지 감
3. 2번까지 간 라운드에 대해 최댓값을 k개 뽑아서 거기에 무적권 배치
4. 3번까지 간 라운드에 대해 최댓값을 k개 뽑아서 거기에 무적권 배치
5. 이 과정 반복하다 보면 최대 라운드가 고정될텐게 거기가 최대로 갈 수 있는 라운드

근데 이 풀이는 구현이 상당히 까다롭다. 그리고 시간 복잡도 또한 꽤나 많이 걸린다.
나중에는 다른 사람의 풀이를 참고하여 다음과 같은 알고리즘으로 풀었다.

### 효율적인 풀이
1. 무적권을 사용하여 갈 수 있는 라운드만큼 최소힙에 넣음
2. (이제부턴 목숨만 사용)
2-1. 현재 도전하는 라운드 몬스터 수를 최소 힙에 넣음.
2-2. 최소 힙에서의 최솟값과 life를 비교하여 통과하면 현재 라운드 ++ 후 2 과정 반복, 실패하면 현재 라운드 값 return

힙의 개수에는 항상 k+1개가 남는데 1개는 더 이상 못가는 라운드의 값 그리고 k는 내가 클리어한 라운드 중 몬스터의 수가 최대인 k개이다.

### 내가 생각한 풀이와 다른 점
1. 목숨을 먼저 사용하지 않고 k를 먼저 사용했다.
2. 최댓값을 k번 뽑는 대신 최솟값을 n-k번 뽑았다. 
3. 큐의 역할은 내가 목숨으로 쓰지 않은 몬스터의 수이다.


### 앞으로 적용해보면 좋을 점
1. 목숨은 상황에 따라 쓰일 수 있는지 없는지가 다르지만 k는 고정된 수이다.
고정된 수를 먼저 고려하는게 좀 더 나은 풀이 같다.

2. 최댓값을 k번 뽑는게 복잡할 경우 최솟값을 n-k번 뽑는 방법을 생각해보자.

3. 구현이 복잡하면 자료구조의 역할을 명확히 정의해보자!


# 2. 체육복
### 내가 생각한 풀이
1. 체육복 없는 친구들을 모두 map에 저장
2. 체육복 여분이 있는 친구들 중 잃어버린 친구들은 여분을 가진 친구 목록에서 제거
3. 체육복 여분이 있는 친구들 번호를 정렬
4. 체육복 여분이 있는 친구들을 한명씩 보면서 자기보다 작은 친구한테 줄 수 있으면 주고 아니면 자기보다 큰 친구한테 줌 (친구한테 빌려줬으면 answer ++ )
5. return 총 학생 수 - 체육복 없는 친구 + answer++(빌려준 학생 수)

### 틀렸던 점
체육복 여분이 있는 친구들 중 여분을 잃어버린 친구들은 자기 체육복이 있는 상태인데 체육복 없는 친구로 계산됨.
ex) 총 학생 n = 3, 체육복 없거나 잃어버린 친구 [1], 체육복 여분이 있는 학생 [1] 일 경우 모두 자신의 체육복이 있는데 내 풀이로는 3-1+0이라 2가 나옴.

### 내가 생각한 풀이가 틀린 점
문제를 잃던 도중 코드를 짜기 시작해서 올바르게 문제를 이해하지 못함.


### 앞으로 적용해보면 좋을 점
문제를 다 읽고 제대로 이해했는지 확인하기 위해 edge 케이스를 확인해보자

# 다음 큰 숫자
### 내가 생각한 풀이
1. n을 이진수로 바꿔서 string에 저장
2. next_permutation(string)
3-1. 만약 값이 커졌으면 십진수로 바꿔서 return
3-2. 만약 값이 작거나 똑같으면 2배 한다음 1 하나 배치하고 0개수 만큼 배치하고 1개수만큼 배치함
ex) 1111 -> 11110 -> 10111

### 처음에 꼬였던 이유
1111만 생각했지 11100도 next_permutation 값이 작아질거라고 생각하지 못했음.

### 다른 사람의 풀이
1. n의 1의 개수를 세는 함수
2. n++을 해가면서 1의 개수가 똑같으면 return

### 앞으로 적용해볼 점
시간복잡도 컷이 넉넉한 문제였다. 이럴 경우엔 그냥 단순하게 가는게 실전에선 시간을 절약하는 방법인거 같다.