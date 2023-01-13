목적부터 말하자면, 빠른 입력과 빠른 출력이다. 가끔씩 Input Data를 몇십만, 몇백만건씩 받을 때가 있는데, <br/>
기존에 사용하던 Scanner 나 System.out.print를 사용하면 시간초과가 발생할 수 있다.

![image](https://user-images.githubusercontent.com/78454649/156710468-e27572e6-8f52-417c-8894-27c4eafc6533.png)

Scanner와System.out.print로 입출력을 했을 때 흐름도이다.

![image](https://user-images.githubusercontent.com/78454649/156710505-b94f4e26-8b1d-4e6f-9f85-1b619dae6157.png)

BufferedReader, BufferedWriter를 사용했을 때 흐름도이다. 중간에 과정이 추가됐는데 왜 더 빠를까?

<br/>

디스크IO 와 문맥 교환, 입출력은 생각보다 느린 작업이다. 당신이 키보드로 입력할 때마다 프로그램에 전달된다면, 오버헤드가 상당히 크게 발생 <br/>
But 키보드 입력을 끝낸 뒤에 한번에 전달되는게 더 빠를 것이다.

Input방식만 바꿔도 두배가 넘는 시간 차이가 발생한다.

<br/>

그러나 BufferedReader에도 단점이 있다.
1. IOException의 예외처리가 필수적이다.
2. 입력받은 모든 데이터가 String으로 반환된다.
3. 줄마다 입력받아서, **따로 split하여 데이터를 처리**해주어야 한다.
4. 숫자형식으로 받기 위해서는 형변환이 필요하다.

<br/>

이게 어떤 말이냐면, Input Data에 1 2 3이 들어왔다고 하자. <br/>
Scanner의 nextInt()로 받으면, [1, 2, 3]을 차례대로 받을 수 있다. 하지만 BufferedReader의 readLine()으로 받으면,  <br/>
"1 2 3"이라는 문자열 자체로 받으며, split(' ')로 띄어쓰기를 구분하여 Integer.parseInt() 과정이 필요해진다는 말이다.

<br/>

```java

import java.io.*;

public class Main {
    public static void main(String[] args) throws IOException{

        BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        int n = Integer.parseInt(bf.readLine());

        for(int i =0; i < n; i++){
            String s = bf.readLine();
            int a = Integer.parseInt(s.split(" ")[0]);
            int b = Integer.parseInt(s.split(" ")[1]);
            bw.write(a+b+"\n");
        }
        bw.flush();
    }
}

```

1. import는 java.io.*로 한다. (Scanner는 java.util 클래스이다.)
2. main함수 우측에 throws IOException을 통해 예외를 처리한다. (메소드 선언부에 throws를 명시하면, 해당 메소드 내에서 exception이 발생하는 경우 해당 메소드를 호출한 곳에서 예외가 발생한다.)
3. BufferedReader, BufferedWriter를 선언한다.
4. n을 입력받고, n만큼 loop를 돈다.
4-1. 해당 줄 전체를 String으로 입력받아, 스페이스로 구분하여 형변환하여 덧셈을 수행한다.
5. BufferedWriter에 써준다.
6. Buffer를 비워준다.

<br/>

여기서, bw.write()는 버퍼에 쓰는것이지, 화면에 출력되는 것이 아니다. 화면에 출력하는 역할은 bw.flush()가 수행한다. <br/>
bw.flush()는 출력이 필요할 때 한 번만 수행해주면 된다. 만약 for문 안에 bw.flush()를 쓰면, <br/>
버퍼에 쓰고 바로 출력하므로 System.out.print와 다를바가 없다

<br/>

#### BufferedReader 사용법

<br/>

```java

BufferedReader br = new BufferedReader(new InputStreamReader(System.in)); // 선언
String s = br.readLine();
int i = Integer.parseInt(br.readLine());

```

선언의 위의 사용법과 같이 하면된다.

입력은 readLine();이라는 메소드를 사용한다. <br/>
String으로 리턴 값이 고정되어 있기 때문에, 다른 타입으로 입력을 받고자 한다면 **반드시 형변환이 필요**하다. <br/>
그리고, 예외처리를 반드시 필요로 한다. readLine()시 마다 try/catch문으로 감싸주어도 되고, <br/>
throws IOException 을 통한 예외처리를 해도 된다.(대부분의 경우에 후자를 사용한다.)

bw.flush() 를 통해 버퍼를 초기화해야 한다 (안하면 출력이 진행되지 않았음)

실제로 사용하면 System.out.println()메소드가 매우 느림 함수라는것을 알게 된다

<br/>

#### BufferedWriter 사용법

<br/>

```java

BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out)); // 선언
String str = "abcdef"; // 출력할 문자열
bw.write(s); // 출력
bw.newLine(); // 줄바꿈
bw.flush(); // 남아있는 데이터 모두 출력
bw.close();

```

BufferedWriter는 System.out.println(""); 처럼 출력과 개행을 동시해 해주지 않기 때문에 <br/>
개행을 위해선 따로 newLine(); 혹은 bw.write("\n");을 사용해야한다. <br/>
그리고 BufferedWriter의 경우 버퍼를 잡아 놓았기 때문에 반드시 사용한 후에,flush()/ close()를 해주어야 한다. <br/>
close()를 하게되면, 출력 스트림을 아예 닫아버리기 때문에 한번 출력후, 다른 것도 출력하고자 한다면 flush()를 사용하면 된다.



