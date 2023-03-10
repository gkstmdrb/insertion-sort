# insertion-sort

### 삽입정렬
은 자료 배열의 모든 요소를 앞에서부터 차례대로 이미 정렬된 배열 부분과 비교하여, 자신의 위치를 찾아 삽입함으로써 정렬을 완성하는 알고리즘이다. 또한 배열이 길어질수록 효율이 떨어진다. 다만, 구현이 간단하다는 장점이 있다.

### pass 1

{4,"2",5,6,1,3}
삽입정렬은 두번째 Index부터 시작된다. 제일 앞의 원소는 원소가 하나이기 때문에, 그 자체로 정렬된 상태이기 때문이다.
우선, 4 와 2 의 크기를 비교해, 4 > 2 이므로, 2의 위치를 찾아 삽입해준다.

### pass 2

{2,4,"5",6,1,3}
두번째로 5 가 선택된다. 5 앞의 정렬된 데이터의 최대값 4 보다 5 가 크므로, 현위치에 둔다.

### pass 3

{2,4,5,"6",1,3}
PASS 2와 같은 경우다. 선택된 데이터인 6 이 앞서 정렬된 데이터의 최대값 5 보다 크므로, 현위치에 둔다.

### pass 4

{2,4,5,6,"1",3}
4번째로, 데이터 1 이 선택되었다.
1 의 위치를 찾는 방법은 우선 6 과 비교한다. 6 보다 1 이 작기 때문에 두 데이터의 위치를 바꾼다. 다음으로 1 과 5 를 비교한다. 마찬가지로, 5 보다 1 이 작기 때문에, 또 위치를 바꾼다.

### pass 5

{1,2,4,5,6,"3"}

마지막으로 데이터 3 이 선택되었다.
3 의 위치도 PASS 4의 방법과 동일하게 찾는다. 그런 과정을 거치면 아래와 같이 완벽하게 정렬된 데이터를 얻을 수 있다.

### pass 6

{1,2,3,4,5,6}


	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		int i, j, temp;
		
		int arr [] = {4,2,5,6,1,3} ;
		
		for(i=0; i<arr.length; i++) {
		
			temp = arr[i];
			
			for(j=i-1; j>0 && arr[j] > temp; j--)
				arr[j+1] = arr[j];
					arr[j+1] = temp;
						
		}
		
		System.out.println(Arrays.toString(arr));
		
	}


### 버블 정렬(bubble sort) 알고리즘의 개념 요약
서로 인접한 두 원소를 검사하여 정렬하는 알고리즘
인접한 2개의 레코드를 비교하여 크기가 순서대로 되어 있지 않으면 서로 교환한다.
선택 정렬과 기본 개념이 유사하다.

<img src ="https://github.com/GimunLee/tech-refrigerator/blob/master/Algorithm/resources/bubble-sort-001.gif">

### JAVA 코드

	public static void main(String[] args) {
		
		int[] arr = {4,5,7,1,2,6,3};
		int temp = 0;
		for(int i = 0; i < arr.length - 1; i++) {
			for(int j= 1 ; j < arr.length-i; j++) {
				if(arr[j]<arr[j-1]) {
					temp = arr[j-1];
					arr[j-1] = arr[j];
					arr[j] = temp;
				}
			}
		}
	System.out.println(Arrays.toString(arr));
	}

### 실행 결과
![image](https://user-images.githubusercontent.com/114748816/223307014-989728f0-4074-4eaa-a488-bcc9ce5ab193.png)
