### 01

설명

한 개의 문자열을 입력받고, 특정 문자를 입력받아 해당 특정문자가 입력받은 문자열에 몇 개 존재하는지 알아내는 프로그램을 작성하세요.

대소문자를 구분하지 않습니다.문자열의 길이는 100을 넘지 않습니다.


입력
첫 줄에 문자열이 주어지고, 두 번째 줄에 문자가 주어진다.

문자열은 영어 알파벳으로만 구성되어 있습니다.


```java

import java.util.Scanner;

public class Main {

    public int solution(String str, char t){
        int answer = 0;

        str = str.toUpperCase();
        t = Character.toUpperCase(t);
        System.out.println(str);

        for(int i = 0; i < str.length(); i++){
            if (str.charAt(i)==t){
                answer ++;
            }
        }

        return answer;
    }

    public static void main(String[] args) {
        Main T = new Main(); // static에서 인스턴스 메소드를 호출하기 위함
        Scanner sc = new Scanner(System.in);
        String str = sc.next();

        // next는 문자열이지만 문자 하나만 가져와야 하기에 charAt 사용, String을 인덱스로 접근
        char c = sc.next().charAt(0);
        System.out.println(T.solution(str,c));
    }
}

```
