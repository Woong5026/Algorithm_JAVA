### 1165

<br/>

![image](https://user-images.githubusercontent.com/78454649/219935854-2055f9e4-5ebc-41ae-a22b-545eb810bfd6.png)

<br/>

```java

import java.util.Scanner;

public class Main {

    static int[] arr = new int[50];

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int time = sc.nextInt();
        int goal = sc.nextInt();

        int count = 0;

        for (int i = time; i < 90; i++){

            int rest = i - time;

            if (rest % 5 == 0){
                count++;
            }

        }
        System.out.println(count + goal);


    }
}

```

<br/>

---

<br/>

### 1173

<br/>


![image](https://user-images.githubusercontent.com/78454649/219935895-b1a9c091-9a6a-4129-91ae-73e22b2084b9.png)

<br/>

```java

import java.util.Scanner;

public class Main {

    static int[] arr = new int[50];

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int h = sc.nextInt();
        int m = sc.nextInt();

        // 0 10 > 23 40

        if(h > 0 && m >= 30){
            System.out.println(h + " " + (m - 30));
        }else if(h > 0 && m <= 30){
            System.out.println((h-1) + " " + (m + 30));
        }else if(h == 0 && m >= 30){
            System.out.println(0 + " " + (m - 30));
        }else if(h == 0 && m <= 30){
            System.out.println(23 + " " + (m + 30));
        }

    }
}

```

---

<br/>

### 1214

<br/>

![image](https://user-images.githubusercontent.com/78454649/219936586-408b8bd0-6628-49b3-b773-d8b5b521cd42.png)

<br/>


```java

import java.util.Scanner;

public class Main {

    static int[] arr = new int[50];

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int y = sc.nextInt();
        int m = sc.nextInt();

        int[] arr = {0,31,28,31,30,31,30,31,31,30,31,30,31,29};

        // 0 10 > 23 40

        if (y % 4 == 0 && y % 100 != 0 || y % 400 == 0){
            System.out.println(arr[13]);
        }else {
            System.out.println(arr[m]);
        }

    }
}

```

+) 윤년

4로 나누어 떨어지면 윤년
4로 나우어 떨어지나 100으로 떨어지면 평년
4로 나우어 떨어지나 100으로 떨어지나, 400으로 나누어 떨어지면 윤년

한마디로 100으로 나누어 떨어지면 평년이지만 그 수가 400의 배수라면 윤년이다

---

<br/>

### 1214

<br/>

![image](https://user-images.githubusercontent.com/78454649/219939887-03022b6a-fea9-454c-91fd-998e4f798f8c.png)

<br/>

```java

import java.util.Arrays;
import java.util.Scanner;
import java.util.SortedMap;

public class Main {

    static int[] arr = new int[50];

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int[] arr = new int[7];


        for (int i = 0; i < arr.length; i++){
            arr[i] = sc.nextInt();
        }

        int correct = 0;
        int bonus_correct = 0;
        String s = "";

        for(int i=0;i<6;i++){
            int n = sc.nextInt();     //주희번호 6번 입력(for문)
            for(int j=0;j<7;j++){
                if(arr[j]==n){      //로또번호 = 주희번호
                    if(j==6) bonus_correct++;   //마지막로또번호 = 주희번호  보너스카운트+1
                    else correct++;     //아니면 맞은 카운트+1
                }
            }
        }

        if(correct<=2) s = "0";             //당첨 조건
        else if(correct==3) s = "5";
        else if(correct==4) s = "4";
        else if(correct==5&&bonus_correct==0) s = "3";
        else if(correct==5&&bonus_correct==1) s = "2";
        else if(correct==6) s = "1";
        System.out.printf(""+s);

    }
}

```





