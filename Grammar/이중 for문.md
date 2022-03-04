```java

public class Prac {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++){ // 0 ~ 9까지 아래 구간이 실행될 것
            for (int j = 0; j < 10; j++){
                System.out.println(i + " " + j); // 00 ~ 99 까지 출력
            }
        }
    }
}

```

![image](https://user-images.githubusercontent.com/78454649/156732180-96ca0103-f578-4922-addd-1876372abe37.png)

1. 사진처럼 각 for문 모두 1~9까지를 실행한다
2. 첫 번째 for문이 0부터 시작하고 j 로 넘어간다 
3. j에서도 0부터 for문이 시작되고 10을 만날때 까지 계속 돈다 여기서 i 의 for문은 끝나지 않았기 때문에 i는 0으로 계속 유지된다
4. j가 10을 만나는 순간 j의 for문을 빠져나오게 되고 i는 1이 시작된다
5. i가 1이 시작된 채로 j로 넘어가고 여기서도 j는 0 ~ 9를 반복하고 또 i 로 넘어가는 순환을 계속하게 된다



