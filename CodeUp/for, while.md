### 1261

<br/>

![image](https://user-images.githubusercontent.com/78454649/220023733-c925e5de-90c4-4bd6-82e4-f2c967df7df9.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int[] arr = new int[10];

        int b = 0;

        for (int i = 0; i < arr.length; i++){

            b = sc.nextInt();

            if(b % 5 == 0){
                System.out.println(b);
                break;
            }
        }

        if(b%5 != 0) {
            System.out.println(0);
        }

    }
}


```

<br/>

---

<br/>

### 1272

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int[] arr = new int[10000000];

        int count = 1;

        for (int i = 1; i < arr.length; i = i + 2){
            arr[i] = count++;
        }

        int tencnt = 10;

        for (int i = 2; i < arr.length; i = i + 2){
            arr[i] = tencnt;
            tencnt += 10;
        }

        int a = sc.nextInt();
        int b = sc.nextInt();

        System.out.println(arr[a] + arr[b]);

    }
}

```

이 문제는 범위가 안 주어져서 당황한 문제이다. <br/>
그래서 범위를 1000정도 배열을 잡아서 해결 하려 했으나 배열 크기로 인하여 실패하였다. 그래서 두번째로 배열의 크기를 매우 늘려서 시도하였다

먼저 배열을 채워야 한다. 보통이라면 나는 배열을 0부터 시작하지만 이러한 문제는 1부터 시작하는것이 문제에 접근하기가 쉬워진다. <br/>
규칙을 2가지로 나눠서 홀수의 인덱스 번호일 때는 1씩 더해주고 짝수의 인덱스 번호일때는 10씩 더해주면 쉽게 해결 할 수 있는 문제이다.


<br/>

---

<br/>

### 1380

<br/>

![image](https://user-images.githubusercontent.com/78454649/220044458-b08859c4-96b7-48a5-b048-a27809babdd0.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int a = sc.nextInt();

        for (int i = 1; i <= 6; i++){
            for (int j = 1; j <= 6; j++){

                if (i + j == a){
                    System.out.println(i + " " + j);
                }

            }

        }
    }
}

```

<br/>

---

<br/>

### 1370

<br/>

![image](https://user-images.githubusercontent.com/78454649/220057097-7cdffe30-fdf1-40b4-9a65-4e539b7c05a4.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int a = sc.nextInt();
        int b = sc.nextInt();

        for (int k = 0; k < b; k++){

            for (int i = 0; i < a; i++){
                for (int j = 0; j < i; j++){
                    System.out.print(" ");
                }
                System.out.print("*");
                System.out.println();
            }

            for (int i = a-2; i >= 0; i--){ // 직전 a부터 1칸씩 내려와야 하지만 끝이 0과 크거나 같기에 a-2
                for (int j = 0; j < i; j++){
                    System.out.print(" ");
                }
                System.out.print("*");
                System.out.println();
            }

        }

    }
}


```





















