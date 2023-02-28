### 1420

<br/>

![image](https://user-images.githubusercontent.com/78454649/221861889-ee9ad9d2-ebee-4d5b-bc98-d8d0938454b2.png)

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







<br/>

---

<br/>

### 1442

<br/>

![image](https://user-images.githubusercontent.com/78454649/221862215-71c9a935-4273-451d-a9eb-7aaaabaa6159.png)

<br/>

```java

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] arr = new int[n];

        for (int i = 0; i < n; i++){
            arr[i] = sc.nextInt();
        }

        for (int i = 0; i < n-1; i++){
            for (int j = i+1; j < n; j++){
                if (arr[i] > arr[j]){
                    int temp = arr[j];
                    arr[j] = arr[i];
                    arr[i] = temp;
                }
            }
        }

        

        for (int i = 0; i < n; i++){
            System.out.print(arr[i] + " ");
        }

    }
}


```

<br/>

---

<br/>

### 1709 

<br/>

![image](https://user-images.githubusercontent.com/78454649/221862619-f0b43266-3028-41da-aba2-c3ef3068cc02.png)

<br/>

```java

import java.util.Arrays;
import java.util.Collection;
import java.util.Collections;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        int[] arr = new int[n];

        for (int i = 0; i < n; i++){
            arr[i] = sc.nextInt();
        }

        Integer[] arr3 = Arrays.stream(arr).boxed().toArray(Integer[]::new);
        Arrays.sort(arr3, Collections.reverseOrder());

        for (int i = 0; i < n; i++){
            System.out.print(arr3[i] + " ");
        }

    }
}


```
