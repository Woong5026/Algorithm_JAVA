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



















