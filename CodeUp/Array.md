### 1405

<br/>

![image](https://user-images.githubusercontent.com/78454649/220094291-0c5c7037-5bde-4332-b73a-601a80e5bb9f.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int[] b = new int[a];

        for (int i = 0; i < b.length; i++) {
            b[i] = sc.nextInt();
        }

        for (int i = 0; i < b.length; i++) {

            for (int j = i; j < b.length; j++) {
                System.out.print(b[j]+ " ");
            }

            for (int j = 0; j < i; j++) {
                System.out.print(b[j] + " ");
            }

            System.out.println();
        }

    }
}

```

<br/>

---

<br/>

### 1410

<br/>

![image](https://user-images.githubusercontent.com/78454649/220098627-3790cd15-9a94-4f47-9f4d-4a6685bb9887.png)


<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        String a = sc.nextLine();

        int open = 0;
        int close = 0;

        for (int i = 0; i < a.length(); i++) {

            if(a.charAt(i) == '(') {
                open++;
            }else if(a.charAt(i) == ')'){
                close++;
            }

        }
        System.out.println(open + " " + close);

    }
}


```

<br/>

---

<br/>

### 1411

<br/>

![image](https://user-images.githubusercontent.com/78454649/220135711-4dd494a1-6219-472a-b016-df37df0a8b5f.png)


<br/>

```java

import java.util.Arrays;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int N = sc.nextInt();

        int[] arr = new int[50];

        for (int i = 0; i < N - 1; i++){
            arr[i] = sc.nextInt();
        }

        Arrays.sort(arr,0,N-1);

        for (int i = 0; i < N; i++){

            if (arr[i] != i + 1){
                System.out.println(i+1);
                break;
            }

        }

    }
}

```

+) Arrays.sort(arr, fromIndex, toIndex) // 부분 정렬

배열의 일부분만 정렬가능

다음과 같이 sort()의 인자로 처음 index와 마지막 index를 전달하여 정렬할 범위를 지정
아래 코드는 0과 4를 인자로 전달했는데, index 0에서 index 4를 포함하는 배열만 정렬하라는 의미이다

```java

int[] arr = {1, 26, 17, 25, 99, 44, 303};

Arrays.sort(arr, 0, 4);

System.out.println("Sorted arr[] : " + Arrays.toString(arr));

// 결과
// Sorted arr[] : [1, 17, 25, 26, 99, 44, 303] // 4번째까지만 정렬된 것을 볼 수 있다

```

<br/>

---

<br/>

### 1420

<br/>

![image](https://user-images.githubusercontent.com/78454649/220157788-22737f81-5c8d-4ac8-94b4-4a8347fbb5a1.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        String[] name = new String[n];
        int[] score = new int[n];
        String[] plus = new String[n];

        for (int i = 0; i < score.length; i++){
            name[i] = sc.next();
            score[i] = sc.nextInt();
            plus[i] = name[i] + " " + score[i];
        }

        int temp = 0;

        for (int i = 0; i < score.length; i++) {
            for (int j = 0; j < score.length; j++) {
                if(score[i] > score[j]) {
                    temp= score[i];
                    score[i] = score[j];
                    score[j]= temp;
                }
            }
        }

        for (int i = 0; i < plus.length; i++) {
            if(plus[i].contains(String.valueOf(score[2]))) {
                String[] result = plus[i].split(" ");
                System.out.println(result[0]);
            }
        }

    }
}

```

+) 배열위치바꾸기(temp)

![image](https://user-images.githubusercontent.com/78454649/220157905-9d5ba9cf-6c1f-48ed-84a7-dbf5ac5fc711.png)

1. temp라는 빈 공간에 a를 넣는다 // int temp = a;
2. a가 빠져나왔기에 그곳에 b를 넣는다(a값에 b를 복사하는 것) // a=b;
3. b가 빠져나왔기에 빈 공간에 temp를 넣어준다 // b = temp;

위에서는 a와 b가 빠져나왔다고 설명했지만 실제로는 값이 복사되는 것
만약 3번의 과정이 없다면 a=10, b=10 이 된다

```java

import java.util.Arrays;

public class Test {
    public static void main(String[] args) {

        int[] arr = {1,2,3};

        int temp = 0;

        temp = arr[0];
        arr[0] = arr[2]; // 만약 아래코드가 주석이라면 [3, 2, 3]
        arr[2] = temp; // 만약 옆의 코드가 주석이 아니라면 [3, 2, 1]

        System.out.println(Arrays.toString(arr));


    }
}

```


<br/>

---

<br/>

### 1425

<br/>

![image](https://user-images.githubusercontent.com/78454649/220278468-94cfbee3-a45c-4e6b-8ff1-130070ad4859.png)

<br/>


```java

import java.util.Arrays;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[] arr = new int[n];

        for (int i = 0; i < arr.length; i++){
            arr[i] = sc.nextInt();
        }

        Arrays.sort(arr);

        for (int i = 1; i <= n; i++){

            System.out.print(arr[i-1] + " ");

            if(i % m == 0){
                System.out.println();
            }

        }

    }
}

```

for문에서 출력시 i값을 1로주고 arr[i-1]을 한 이유는 i가 0일때 6 % 0 == 0 을 만족하므로 하기에 i를 1로 주었다

<br/>

---

<br/>

### 2차원 배열

<br/>

### 1460

![image](https://user-images.githubusercontent.com/78454649/220412359-c21eedd8-c460-4fd6-add0-e454f39877ee.png)

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        int[][] arr = new int[n][n];

        int cnt = 1;

        for (int i = 0; i < arr.length; i++){
            for (int j = 0; j < arr.length; j++){
                arr[i][j] = cnt++;
            }
        }

        int[][] rev = new int[n][n];

        for (int i = 0; i < n; i++){
            for (int j = 0; j < n; j++){
                rev[i][j] = arr[i][n-j-1];
            }
        }

        for (int i = 0; i < n; i++){
            for (int j = 0; j < n; j++){
                System.out.print(rev[i][j] + " ");
            }
            System.out.println();
        }

    }
}

```

+) 2차원 배열 회전

```java

// 시게방향으로 90도 회전, 오른쪽으로 90도 회전

        for(int i=0; i<n; i++){
            for(int j=0; j<n; j++){
                B[i][j] = A[n-j-1][i];
            }
        }

// 반시계 방향으로 90도 회전, 270도, -90도, 왼쪽으로 90도

       for(int i=0; i<n; i++){
            for(int j=0; j<n; j++){
                B[i][j] = A[j][n-i-1];
            }
        }
        
// 위, 아래로 뒤집기

        for(int i=0; i<n; i++){
            for(int j=0; j<n; j++){
                B[i][j] = A[n-i-1][j];
            }
        }
        
        
// 좌우로 뒤집기 회전

        for(int i=0; i<n; i++){
            for(int j=0; j<n; j++){
                B[i][j] = A[i][n-j-1];
            }
        }


```

정리를 하긴 했지만 사실 배열을 뒤집을 때는 

```java

for (int i = 0; i < n; i++){
            for (int j = 0; j < n; j++){
                rev[i][j] = arr[i][n-j-1];
            }
        }

```

위 코드에서 볼 수 있듯이 새로운 배열에 기존 배열을 하나씩 넣는 방식인데
새로운 배열을 통해 나온 출력값을 보고 기존 배열에서 어떤 수가 들어 갈지를 고민한다면 보다 쉽게 풀 수 있을 것이다.

<br/>

---


<br/>

### 1465

<br/>

![image](https://user-images.githubusercontent.com/78454649/220606454-e9764e0a-23b1-4d64-9ff0-1b331aafa803.png)


<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[][] arr = new int[n][m];

        int cnt = 1;

        for (int i = 0; i < n; i++){
            for (int j = 0; j < m; j++){
                arr[i][j] = cnt++;
            }
        }

        int[][] rev = new int[n][m];

        for (int i = 0; i < n; i++){
            for (int j = 0; j < m; j++){
                rev[i][j] = arr[n-i-1][j];// 1,2
            }
        }

        for (int i = 0; i < n; i++){
            for (int j = 0; j < m; j++){
                System.out.print(rev[i][j] + " ");
            }
            System.out.println();
        }

    }
}

``

<br/>

---


<br/>

### 1468

<br/>

![image](https://user-images.githubusercontent.com/78454649/220606617-20c2fb91-b36e-4dc7-8b38-c2dc08fb5ae9.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        int[][] arr = new int[n][n];

        int cnt = 1;

        for (int i = 0; i < n; i++){
            for (int j = 0; j < n; j++){
                arr[i][j] = cnt++;
            }
        }

        int[][] rev = new int[n][n];

        for (int i = 0; i < n; i++){
            for (int j = 0; j < n; j++){

                if (i % 2 == 0){
                    rev[i][j] = arr[i][j];
                }
                else {
                    rev[i][j] = arr[i][n-j-1];
                }


            }
        }

        for (int i = 0; i < n; i++){
            for (int j = 0; j < n; j++){
                System.out.print(rev[i][j] + " ");
            }
            System.out.println();
        }

    }
}


```

<br/>

---


<br/>

### 달팽이

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        int[][] arr = new int[n][n];

        int right = -1; // 열
        int bottom = 0; // 행
        int k = 1; // 배열에 저장되는 값
        int top = 1; // 행열을 바꿔주는 수(방향의 반전)
        int print = n; // 한 줄마다 입력될 값의 수

        for (int i = 0; i < n; i--){
            for (int j = 0; j < print; j++){
                right += top;
                arr[bottom][right] = k;
                k++;
            }
            print--;
            
            for (int j = 0; j < print; j++){
                bottom += top;
                arr[bottom][right] = k;
                k++;
            }
            top *= -1; // 값을 반전시켜 행열을 바꿔줄지 결정(방향의 반전)
        }

        for (int i = 0; i < n; i++){
            for (int j = 0; j < n; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}


```

![image](https://user-images.githubusercontent.com/78454649/220853570-61542352-6b92-4e90-9346-23004ab0aecc.png)


<br/>

---


<br/>

### 1484

<br/>

![image](https://user-images.githubusercontent.com/78454649/220899985-370fba66-e458-45dc-a396-29d7327f6368.png)

<br/>

달팽이를 활용한 문제이다 <br/>
하지만 아래처럼 풀면 인텔리제이에서는 답이 나오긴 하지만 코드업에서는 시간초과가 난다

```java

import java.util.Scanner;

public class Test {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[][] arr = new int[n][m];

        int right = -1; // 열
        int bottom = 0; // 행
        int k = 1; // 배열에 저장되는 값
        int num = 1; // 행열을 바꿔주는 수
        int cnt = n; // 한 줄마다 입력될 값의 수
        int rcnt = m;

        for (int i = 0; i < n; i--){
            for (int j = 0; j < rcnt; j++){
                right += num;
                arr[bottom][right] = k;
                k++;
            }

            rcnt--;
            cnt--;

            if(rcnt == 1){
                rcnt = 0;
            }


            for (int j = 0; j < cnt; j++){
                bottom += num;
                arr[bottom][right] = k;
                k++;
            }
            num *= -1; // 값을 반전시켜 행열을 바꿔줄지 결정

            if(cnt == 1){
                cnt = 0;
            }

        }

//        System.out.println(Arrays.toString(arr));

        for (int i = 0; i < n; i++){
            for (int j = 0; j < m; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}

```

<br/>

그렇기에 아래처럼 풀어보았다

```java

import java.util.Scanner;

public class Test {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[][] arr = new int[n][m];

        int right = -1; // 열
        int bottom = 0; // 행
        int k = 1; // 배열에 저장되는 값
        int num = 1; // 행열을 바꿔주는 수
        int cnt = n; // 한 줄마다 입력될 값의 수
        int rcnt = m;

        while (true){
            for (int j = 0; j < m; j++){
                right += num;
                arr[bottom][right] = k;
                k++;
            }

            n--;
            m--;

            for (int j = 0; j < n; j++){
                bottom += num;
                arr[bottom][right] = k;
                k++;
            }
            num *= -1;

            if(n<=0||m<=0) break; //while 탈출조건
        }

        for (int i = 0; i < cnt; i++){
            for (int j = 0; j < rcnt; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}

```

<br/>

---


<br/>

### 1485

<br/>

![image](https://user-images.githubusercontent.com/78454649/221156873-fdfc2ffa-a74d-4c81-b7cc-83f4d144ff6b.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[][] arr = new int[n][m];

        int right = -1; // 열
        int bottom = 0; // 행
        int k = n*m; // 배열에 저장되는 값
        int num = 1; // 행열을 바꿔주는 수
        int cnt = n; // 한 줄마다 입력될 값의 수
        int rcnt = m;

        while (true){
            for (int j = 0; j < m; j++){
                right += num;
                arr[bottom][right] = k;
                k--;
            }

            n--;
            m--;

            for (int j = 0; j < n; j++){
                bottom += num;
                arr[bottom][right] = k;
                k--;
            }
            num *= -1;

            if(n<=0||m<=0) break; //while 탈출조건
        }

        for (int i = 0; i < cnt; i++){
            for (int j = 0; j < rcnt; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}


```

<br/>

---


<br/>

### 1486

<br/>

![image](https://user-images.githubusercontent.com/78454649/221157073-41efe2d0-19f2-44db-8ed3-efa1c46bf25d.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[][] arr = new int[n][m];

        int right = m-1; // 열
        int bottom = -1; // 행
        int k = 1; // 배열에 저장되는 값
        int num = 1; // 행열을 바꿔주는 수
        int cnt = n; // 한 줄마다 입력될 값의 수
        int rcnt = m;

        while (true){

            for (int j = 0; j < n; j++){
                bottom += num;
                arr[bottom][right] = k;
                k++;
            }
            n--;
            m--;

            num *= -1;

            for (int j = 0; j < m; j++){
                right += num;
                arr[bottom][right] = k;
                k++;
            }

            if(n<=0||m<=0) break; //while 탈출조건
        }

        for (int i = 0; i < cnt; i++){
            for (int j = 0; j < rcnt; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}

```

<br/>

---


<br/>

### 1487

<br/>

![image](https://user-images.githubusercontent.com/78454649/221157291-b88d3955-d101-4133-a1fb-49ee7e187cbf.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[][] arr = new int[n][m];

        int right = m-1; // 열
        int bottom = -1; // 행
        int k = n*m; // 배열에 저장되는 값
        int num = 1; // 행열을 바꿔주는 수
        int cnt = n; // 한 줄마다 입력될 값의 수
        int rcnt = m;

        while (true){

            for (int j = 0; j < n; j++){
                bottom += num;
                arr[bottom][right] = k;
                k--;
            }

            num *= -1;

            n--;
            m--;

            for (int j = 0; j < m; j++){
                right += num;
                arr[bottom][right] = k;
                k--;
            }

            if(n<=0||m<=0) break; //while 탈출조건
        }

        for (int i = 0; i < cnt; i++){
            for (int j = 0; j < rcnt; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}


```

<br/>

---


<br/>

### 1488

<br/>

![image](https://user-images.githubusercontent.com/78454649/221157426-7d335494-c1be-4f65-bd1d-0fe859169baa.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int m = sc.nextInt();

        int[][] arr = new int[n][m];

        int right = m; // 열
        int bottom = n-1; // 행
        int k = 1; // 배열에 저장되는 값
        int num = 1; // 행열을 바꿔주는 수
        int cnt = n; // 한 줄마다 입력될 값의 수
        int rcnt = m;

        while (true){

            num *= -1;

            for (int j = 0; j < m; j++){
                right += num;
                arr[bottom][right] = k;
                k++;
            }

            n--;
            m--;

            for (int j = 0; j < n; j++){
                bottom += num;
                arr[bottom][right] = k;
                k++;
            }

            if(n<=0||m<=0) break; //while 탈출조건
        }

        for (int i = 0; i < cnt; i++){
            for (int j = 0; j < rcnt; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

    }
}

```

<br/>

---


<br/>

### 1508

<br/>

![image](https://user-images.githubusercontent.com/78454649/221586541-c7ef84e6-0762-4238-b128-e9fef119e03c.png)

<br/>

```java

import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int a = sc.nextInt();
		int[][] b = new int[51][51];
		for (int i = 0; i < a; i++) {
			b[i][0] =sc.nextInt();
			for (int j = 1; j <= i; j++) {
				b[i][j] = (b[i][j-1])-(b[i-1][j-1]);
			}
		}
		for (int i = 0; i < a; i++) {
			for (int j = 0; j <= i; j++) {
				System.out.print(b[i][j]+" ");
			}
			System.out.println();
		}
	}
}

```

<br/>

---


<br/>

### 1509

<br/>

![image](https://user-images.githubusercontent.com/78454649/221858318-3f9b86f1-aa1e-4046-973f-a9e90e58e068.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

//        int n = sc.nextInt();

        int[][] arr = new int[11][10];

        for (int i = 0; i < 11; i++) {
            for (int j = 0; j < 10; j++) {
                arr[i][j] = sc.nextInt();
            }

        }

        int cnt = 0;

        for (int i = 0; i < 10; i++){
            for (int j = 9; j >= 0; j--){
            if (arr[10][i] == 1){


                    if (arr[j][i] > 0){
                        System.out.println((i + 1) + " " + "crash");
                        break;
                    }else if (arr[j][i] < 0){
                        System.out.println(i + 1 + " " + "fall");
                        break;
                    }else if(arr[j][i] == 0) {
                        //j가 0까지 무사히 다다르고 0일 경우 safe
                        if(j == 0) {
                            System.out.println((i+1) + " safe");
                        }
                    }

                }
            }

        }
    }
}

```

