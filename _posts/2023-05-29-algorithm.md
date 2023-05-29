---
layout: single
title: 알고리즘(Algorithm)
---

# 알고리즘(Algorithm)
- 알고리즘은 문제를 해결하기 위해 정의된 절차나 규칙의 집합이다. 
- 알고리즘은 입력(input)을 받아서 출력(output)을 생성하는 과정으로 구성된다.
- 컴퓨터 과학에서 알고리즘은 주어진 문제를 해결하기 위한 단계적인 절차를 설명하는 방법으로 사용된다.

# 알고리즘 예시


### 배열의 값 평균 내기 
- 배열의 값의 평균을 구하는 알고리즘은 이와 같다.
        - 배열의 모든 요소를 합산한다.
        - 합을 배열의 길이로 나눈다.
        - 나눈 결과를 평균값으로 사용한다.
- 간단한 예시 코드
```
public double calculateAverage(int[] array) {
    int sum = 0;
    for (int i = 0; i < array.length; i++) {
        sum += array[i];
    }
    return (double) sum / array.length;
}

```

### 정렬 알고리즘 
- 정렬 알고리즘은 주어진 데이터를 일정한 순서로 재배치하는 알고리즘이다.
- 대표적인 정렬 알고리즘으로는 이와 같다.
    - 버블 정렬(Bubble Sort) :
        - 인접한 두 요소를 비교하여 순서에 맞지 않는 경우 서로 교환한다.
        - 반복하여 정렬을 완료한다.
        - 예시 코드
            - temp는 임시적으로 값 저장하기 위한 변수
        ```
        public void bubbleSort(int[] array) {
            int n = array.length;

            // 배열의 모든 요소를 비교하기 위한 외부 루프
            for (int i = 0; i < n - 1; i++) {

                // 한 번의 외부 루프 실행마다 최대값이 배열의 끝으로 이동하므로
                // 내부 루프의 범위를 n-i-1로 제한합니다.
                for (int j = 0; j < n - i - 1; j++) {

                    // 현재 요소와 다음 요소를 비교하여 순서를 확인합니다.
                    if (array[j] > array[j + 1]) {

                        // 순서가 잘못되었을 경우 인접한 요소를 교환합니다.
                        int temp = array[j];
                        array[j] = array[j + 1];
                        array[j + 1] = temp;
                    }
                }
            }
        }
        ```
    - 삽입 정렬(Insertion Sort) :
        - 요소를 이미 정렬된 부분에 삽입하며, 전체 요소를 정렬한다.
        - 배열을 정렬하는 간단하면서도 효율적인 알고리즘이다.
            - 삽입 정렬은 두 번째 자료부터 시작하여 그 앞의 자료들과 비교하여 삽입할 위치를 지정한 후 자료를 뒤로 옮기고 지정한 자리에 자료를 삽입하여 정렬하는 알고리즘이다.
            - ![image](https://github.com/DJSon2/about-me/assets/124123956/587ba24f-fd87-44fd-90a4-f9f1a4d5de45)
        - 예시 코드
        ```
        public void insertionSort(int[] array) {
            int n = array.length;
            
            for (int i = 1; i < n; i++) {
                int key = array[i]; // 현재 값을 key 변수에 저장
                int j = i - 1;
                
                // key 값을 이전 요소와 비교하여 삽입할 위치를 찾음
                while (j >= 0 && array[j] > key) {
                    array[j + 1] = array[j]; // 이전 요소를 한 칸씩 뒤로 이동
                    j--;
                }
                
                array[j + 1] = key; // key 값을 삽입할 위치에 삽입
            }
        }

        ```
    - 퀵 정렬(Quick Sort) :
        - 피벗(pivot)을 기준으로 작은 값과 큰 값으로 분할하여 재귀적으로 정렬한다.
            - 피벗은 정렬 알고리즘에서 사용되는 개념으로 배열을 분할하는데 사용되는 기준값으로, 배열을 두 개의 부분으로 나누는 역할을 한다.
        - ![image](https://github.com/DJSon2/about-me/assets/124123956/c55ef8f9-2f6b-466b-8ca4-fe94168af6c5)
        - 예시 코드
        ```
        public void quickSort(int[] array, int low, int high) {
            if (low < high) {
                // 배열을 분할하고 피벗의 인덱스를 얻습니다.
                int pivotIndex = partition(array, low, high);
                
                // 피벗을 기준으로 분할된 두 개의 하위 배열을 재귀적으로 정렬합니다.
                quickSort(array, low, pivotIndex - 1);
                quickSort(array, pivotIndex + 1, high);
            }
        }

        private int partition(int[] array, int low, int high) {
            // 피벗을 마지막 요소로 선택합니다.
            int pivot = array[high];
            int i = low - 1;
            
            // 피벗보다 작은 요소를 왼쪽으로, 큰 요소를 오른쪽으로 이동시킵니다.
            for (int j = low; j < high; j++) {
                if (array[j] < pivot) {
                    i++;
                    swap(array, i, j);
                }
            }
            
            // 피벗을 올바른 위치로 이동시킵니다.
            swap(array, i + 1, high);
            
            return i + 1; // 피벗의 인덱스를 반환합니다.
        }

        private void swap(int[] array, int i, int j) {
            int temp = array[i];
            array[i] = array[j];
            array[j] = temp;
        }
        ```
![image](https://github.com/DJSon2/about-me/assets/124123956/2b61490a-56b3-4067-a108-d8ae7e37ae56)
        - quickSort 메서드:
            - 정렬할 배열과 배열의 시작 인덱스(low)와 인덱스(high)를 매개변수로 받는다.
            - 배열의 크기가 1보다 큰 경우에만 정렬을 수행한다.
            - 배열을 분할하고, 피벗을 기준으로 왼쪽과 오른쪽 하위 배열을 재귀적으로 정렬한다.
        - prtition 메서드 :
            - 배열을 분할하고 피벗의 인덱스를 반환하는 역할을 한다.
            - 피벗은 일반적으로 배열의 마지막 요소를 선택한다.
            - 배열을 순회하며 피벗보다 작은 요소는 왼쪽으로, 큰 요소를 선택한다.
            - 이 과정을 마치면 피벗은 올바른 위치로 이동하게 된다.
        - swap 메서드 :
            - 두 요소의 위치를 교환하는 역할을 한다.
            - 배열에서 요소의 위치를 교환하기 위해 사용된다.



### 검색 알고리즘
- 검색 알고리즘은 주어진 데이터에서 특정 값을 찾는 알고리즘이다.
- 대표적인 검색 알고리즘으로는 이와 같다.
    - 선형 검색(Linear Search) :
        - 순차적으로 요소를 비교하면서 값을 찾는다.
        - 예시 코드
```
public int linearSearch(int[] array, int target) {
    int n = array.length;
    
    for (int i = 0; i < n; i++) {
        if (array[i] == target) {
            return i; // 값을 찾으면 해당 인덱스를 반환
        }
    }
    
    return -1; // 값을 찾지 못한 경우 -1을 반환
}
```
    - 코드 설명 :
        - linearSearch 메서드 : 
            - 검색할 배열과 찾고자 하는 대상 값(target)을 매개변수로 받는다.
            - 배열을 처음부터 끝까지 순회하면서 대상 값과 요소를 비교하여 일치하는 요소를 찾는다.
            - 찾은 경우 해당 요소의 인덱스를 반환하고, 찾지 못한 경우 -1을 반환
        - for 루프 :
            - 배열을 처음부터 끝까지 순회하면서 요소를 하나씩 확인합니다.
            - 배열의 크기(n)만큼 반복하며, 각 요소를 대상 값과 비교
        - if 문 :
            - 현재 요소와 대상 값이 일치하는지 확인한다. 일치하면 해당 요소의 인덱스를 반환하고, 일치하지 않으면 다음 요소를 확인한다.

    - 이진 검색(Binary Search) :
        - 정렬된 배열에서 중간 요소와 비교하여 찾는 값을 반으로 나누어 검색 범위를 줄여나간다.
        - 예시 코드
```
public int binarySearch(int[] array, int target) {
    int low = 0;
    int high = array.length - 1;
    
    while (low <= high) {
        int mid = (low + high) / 2;
        if (array[mid] == target) {
            return mid; // 값을 찾았을 때 인덱스 반환
        } else if (array[mid] < target) {
            low = mid + 1; // 중간 값보다 큰 범위에서 검색
        } else {
            high = mid - 1; // 중간 값보다 작은 범위에서 검색
        }
    }
    
    return -1; // 값을 찾지 못한 경우 -1 반환
}
```

### 순환 알고리즘
- 순환 알고리즘은 자기 자신을 호출하여 문제를 해결하는 알고리즘이다.
- 대표적인 순환 알고리즘으로는 재귀 함수를 사용하는 것들이 있다.
    - 예를 들어, 팩토리얼 계산, 피보나치 수열 등이 있다.
    - 팩토리얼 간단 예시 코드
```
public int factorial(int n) {
    if (n == 0) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
}
```
관련, 참고 포스트
- [버블정렬](https://gmlwjd9405.github.io/2018/05/06/algorithm-bubble-sort.html)
- [삽입정렬](https://gmlwjd9405.github.io/2018/05/06/algorithm-insertion-sort.html)