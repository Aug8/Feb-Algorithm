## 투 포인터

정렬된 배열이나 리스트에서 두 개의 포인터를 사용하여 특정 조건을 만족하는 부분을 찾는 알고리즘

투 포인터를 활용하면 시간 복잡도가 O(N)이므로, O($N^2$)보다 더 빠름

### 투 포인터가 사용되는 경우

- 정렬된 배열에서 두 수의 합 찾기(Two sum)
    - 왼쪽 포인터는 처음, 오른쪽 포인터는 마지막부터 시작함
    - target 값을 기준으로 두 수를 합친 값이 target보다 작다면 left 증가(값 증가)
    - target 값을 기준으로 두 수를 합친 값이 target보다 크다면 right 감소(값 감소)
    - 두 수의 합이 target과 같다면 정답 반환
- 특정 합 이상이 되는 최소 길이의 연속 부분 배열
    - 두 개의 포인터(start, end)를 사용하여 연속 부분 배열을 탐색함
    - end를 증가시키면서 부분합을 증가시키고, sum이 S이상 되는 순간 start를 증가시키면서 최소 길이를 증가시킴.
    - 최적의 길이를 찾을 때까지 start와 end를 조정함
    
- 두 개의 정렬된 배열을 병합(Merge Sort의 병합 과정)
    - 두 개의 포인터(i,j)를 사용하여 각각 arr1과 arr2를 탐색
    - 더 작은 값을 리스트에 추가하고 해당 포인터 증가
    - 한쪽 배열이 먼저 끝나면, 나머지는 순서대로 추가
- 회문(Palindrome) 검사
    - 문자열의 양 끝에서 두 개의 포인터(left, right)를 시작함
    - left++, right—를 통해 뽑은 문자가 서로 다르면 회문이 아님
    - 문자가 같으면 양쪽 포인터를 안쪽으로 이동
- 정렬된 배열에서 중복된 원소 제거
    - 두 개의 포인터(i,j)를 활용하여 중복되지 않은 요소를 유지
    - j포인터를 이동하면서 중복되지 않은 원소를 i위치에 덮어쓰기
    - 중복 원소는 무시하고, 마지막에 i+1을 반환하여 유효한 원소의 개수 반환

## 슬라이딩 윈도우

배열이나 문자열 같은 연속된 데이터에서 특정 구간을 빠르게 탐색하기 위해 사용하는 알고리즘 기법

- 윈도우 크기만큼의 범위를 유지하며 다음 인덱스로 이동하면서 값을 갱신하는 방식
- 불필요한 연산을 줄일 수 있어 시간 복잡도를 획기적으로 개선함

### 슬라이딩 윈도우가 사용되는 경우

- 최대/최소 합, 평균을 구하는 문제
    
    
- 최소 길이의 부분 배열 찾기(배열에서 합이 S이상 되는 최소 길이의 연속 부분 배열(윈도우)를 찾기)
    - start와 end 포인터를 이용함
    - end를 증가시키면서 부분합을 증가시키고, sum이 S이상이 되는 순간 start를 증가시키면서 최소 길이 갱신
- 고정된 길이의 윈도우에서 최댓값/최솟값 찾기
    - 첫 번째 윈도우의 합을 구함(초기 값 설정)
    - 이후부터 윈도우를 오른쪽으로 한 칸씩 이동하며, 왼쪽 값을 빼고 오른쪽 값을 더하여 새로운 합을 구함
    - 모든 윈도우에서 최대 합을 찾음
- 문자열에서 고유한 문자 개수 찾기
    - 윈도우를 확장하면서 고유 문자 개수를 카운트
    - 고유 문자가 k개를 초과하면 왼쪽 포인터를 이동하여 조건을 맞춤
    - 최대 길이 갱신