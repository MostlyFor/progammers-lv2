24. 타겟 넘버
더 효율적인 풀이 있었던거 같다

25. 귤 고르기
map<int, int>에서 value 값으로 정렬해야하는 상황이 온다. 이때 map을 하나 더 만들면 키 값 중복으로 걸릴수도 있다. 그냥 vector<pair<int,int>>만들고 여기서 정렬하는게 낫다.

27. 더 맵게
우선순위 큐를 set 또는 multiset 대신 사용하는 이유는 연산이 2~4배 빠르다고 한다. 최솟값이나 최댓값을 여러번 얻어야할 땐 우선순위 큐에 접근하는게 낫다.
그리고 자료구조가 비는 경우가 언제인지 항상 생각하자. 거기서 오류가 나온다.

30. 스킬트리
비교를 어떻게 처음부터 할까 했는데 문자열 중에 필요한 부분만 남기고 비교는 맨 마지막에 하는게 핵심!

31. 주식가격
stack을 쓰는 문제는 매번 헷갈리는데 이전 정보들이 필요할 때, 그리고 조건만 충족하면 이전 정보들을 아예 신경쓰지 않아도 될 때! 사용한다고 생각하면 될거같다.

32. 방문길이
상당히 중복되는 부분이 많아 코드를 정리할 부분이 많지만 시험에선 빠르게 쓰는게 더 중요할 거 같다.