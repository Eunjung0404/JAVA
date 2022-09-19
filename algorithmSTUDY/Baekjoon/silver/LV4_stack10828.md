# 스택의 개념

\-한 쪽 끝에서만 자료를 넣거나 뺄수있는 선형구조의 자료구조
# 문제
정수를 저장하는 스택을 구현한 다음, 입력으로 주어지는 명령을 처리하는 프로그램을 작성하시오.

명령은 총 다섯 가지이다.

push X: 정수 X를 스택에 넣는 연산이다.
pop: 스택에서 가장 위에 있는 정수를 빼고, 그 수를 출력한다. 만약 스택에 들어있는 정수가 없는 경우에는 -1을 출력한다.
size: 스택에 들어있는 정수의 개수를 출력한다.
empty: 스택이 비어있으면 1, 아니면 0을 출력한다.
top: 스택의 가장 위에 있는 정수를 출력한다. 만약 스택에 들어있는 정수가 없는 경우에는 -1을 출력한다.
# 입력
첫째 줄에 주어지는 명령의 수 N (1 ≤ N ≤ 10,000)이 주어진다. 둘째 줄부터 N개의 줄에는 명령이 하나씩 주어진다. 주어지는 정수는 1보다 크거나 같고, 100,000보다 작거나 같다. 문제에 나와있지 않은 명령이 주어지는 경우는 없다.
# 출력
출력해야하는 명령이 주어질 때마다, 한 줄에 하나씩 출력한다.
# 풀이

```java
import java.util.*;

public class Main {
	
	static Scanner scan=new Scanner(System.in);
	
	public static void main(String[] args) {

		int[] stack=new int[0];
		Scanner scan=new Scanner(System.in);
		int count=Integer.parseInt(scan.nextLine());
		String[] inputArr=new String[count];
		for(int i=0;i<count;i++)
		{
			inputArr[i]=scan.nextLine();
		}
		for(int i=0;i<count;i++)
		{
			if(inputArr[i].contains("push"))
			{
				int num=Integer.parseInt(inputArr[i].replaceAll("push ", ""));
				//스택의 길이를 늘린다.
				stack=new int[stack.length+1];
				//늘린 스택의 마지막 위치에 값을 넣어준다.
				stack[stack.length]=num;
				System.out.println(Arrays.toString(stack));
			}else
			{
				switch (inputArr[i]) {
				case "pop": pop(stack);
					break;
				case "top": top(stack);
				break;
				case "size": size(stack);
				break;
				case "empty": empty(stack);
				break;
				}
			}
		
		}
	}
	
	//정수 x를 스택에 넣는 연산 함수
	public static void push(int x,int[] stackArr)
	{
		System.out.println("push");
		
		//스택의 길이를 늘린다.
		stackArr=new int[stackArr.length+1];
		//늘린 스택의 마지막 위치에 값을 넣어준다.
		stackArr[stackArr.length]=x;
		System.out.println(Arrays.toString(stackArr));
		
	}
	//스택에서 가장위에 있는 정수를 빼고, 그 수를 출력한다.
	public static void pop(int[] stackArr)
	{
	
		if(stackArr.length==0)
		{
			System.out.println(-1);
			
		}else
		{
		//맨위값 출력
		System.out.println(stackArr[stackArr.length]);
		//배열 크기를 줄인다.
		stackArr= new int[stackArr.length-1];
		}
	}
	//스택의 정수 개수를 출력한다.
	public static void size(int[] stackArr)
	{
		//사이즈값 출력
		System.out.println(stackArr.length);

	} 
	//스택이 비어있으면 1 아니면 0을 출력한다.
	public static void empty(int[] stackArr)
	{
		if(stackArr.length==0)
		{
			System.out.println(1);
			
		}else
		{
			System.out.println(0);
		}
		//배열이 빈경우 체크 ->length로 체크한다. 헷갈린부분 배열은 [0]부터 시작해서 헷갈렸음.
		//length는 요소의 개수를 반환하니까 상관없다. 

	} 
	//스택의 가장 위에 있는 정수를 출력한다.
	public static void top(int[] stackArr)
	{
		if(stackArr.length==0)
		{
			System.out.println(-1);
			
		}else
		{
			//맨위값 출력
			System.out.println(stackArr[stackArr.length]);
		}
	}
	
}
```

![에러메세지](https://blog.kakaocdn.net/dn/Pi7xG/btrMvsIEHXy/eAHscCDcfsDNvELh2e6r4k/img.png)

**java.lang.ArrayIndexOutOfBoundsException**  에러 발생

배열에 마지막 인덱스에 값을 넣어줘야하는데  배열\[배열.length\]=값;

이렇게 넣어서 에러가 난 것이였다.배열\[배열.length-1\]=값; 이렇게 변경해주고

push랑 pop은 배열의 길이와 값을 변경하는등의 기능이기 때문에  배열을 리턴하도록 void-> int\[\] 로 변경하였다.

\*push가 제대로 작동 되지않는다..!<br>
![실행화면](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FwAGly%2FbtrMkSbtguk%2FyOHn6BcwJe77skCdYnKmeK%2Fimg.png)


자꾸 배열이 초기화 되는데... 바보같이 기존에 배열에 길이를 늘리기위해 초기화를 해주고 

기존배열의 요소를 다시 넣어주는 과정이 필요한데 그 부분을 구현하지 않았다..

수정코드

```java
import java.util.*;

public class Main {
	
	static Scanner scan=new Scanner(System.in);
	
	public static void main(String[] args) {

		int[] stack=new int[0];
		Scanner scan=new Scanner(System.in);
		int count=Integer.parseInt(scan.nextLine());
		String[] inputArr=new String[count];
		for(int i=0;i<count;i++)
		{
			inputArr[i]=scan.nextLine();
		}
		for(int i=0;i<count;i++)
		{
			if(inputArr[i].contains("push"))
			{
				int num=Integer.parseInt(inputArr[i].replaceAll("push ", ""));
				//스택의 길이를 늘린다.
				 stack=push(num, stack);
			}else if(inputArr[i].contains("pop"))
			{
				stack=pop(stack);
			}
			else if(inputArr[i].contains("top"))
			{
				top(stack);
			}
			else if(inputArr[i].contains("empty"))
			{
				empty(stack);
			}
			else if(inputArr[i].contains("size"))
			{
				size(stack);
			}
		
		}
	
	}
	
	//정수 x를 스택에 넣는 연산 함수
	public static int[] push(int x,int[] stackArr)
	{
		//기존에 배열값을 카피한다(기존 요소를 유지하기 위함)
		int[] copyArr= stackArr;
		//스택의 길이를 늘린다.
        stackArr=new int[stackArr.length+1];
        //기존에 배열에 있는 값을 넣어준다.
        for(int i=0;i<copyArr.length;i++)
        {
        	stackArr[i]=copyArr[i];
        }
		//늘린 스택의 마지막 위치에 값을 넣어준다.
		stackArr[stackArr.length-1]=x;
		return stackArr;
		
	}
	//스택에서 가장위에 있는 정수를 빼고, 그 수를 출력한다.
	public static int[] pop(int[] stackArr)
	{
	
		if(stackArr.length==0)
		{
			System.out.println(-1);
			
		}else
		{
		//맨위값 출력
		System.out.println(stackArr[stackArr.length-1]);
		//기존에 배열값을 카피한다(기존 요소를 유지하기 위함)
		int[] copyArr= stackArr;
		//배열 크기를 줄인다.
		stackArr= new int[stackArr.length-1];
		//기존 배열의 값을 넣어준다.
		for(int i=0;i<copyArr.length-1;i++)
		{
			stackArr[i]=copyArr[i];
		}
		
		
		}
		
		return stackArr;
	}
	//스택의 정수 개수를 출력한다.
	public static void size(int[] stackArr)
	{
		//사이즈값 출력
		System.out.println(stackArr.length);

	} 
	//스택이 비어있으면 1 아니면 0을 출력한다.
	public static void empty(int[] stackArr)
	{
		if(stackArr.length==0)
		{
			System.out.println(1);
			
		}else
		{
			System.out.println(0);
		}
		//배열이 빈경우 체크 ->length로 체크한다. 헷갈린부분 배열은 [0]부터 시작해서 헷갈렸음.
		//length는 요소의 개수를 반환하니까 상관없다. 

	} 
	//스택의 가장 위에 있는 정수를 출력한다.
	public static void top(int[] stackArr)
	{
		if(stackArr.length==0)
		{
			System.out.println(-1);
			
		}else
		{
			//맨위값 출력
			System.out.println(stackArr[stackArr.length-1]);
		}
	}
	
}
```

드디어 끝이구나 했는데..



??? 시간초과?

#### **시간초과 해결 과정(메모리 최적화)**

**Scanner가 속도가 느리다고 해서 BufferedReader로 변경해봤다.**

(BufferedReader가 데이터가 버퍼를 거쳐 전달되서 데이터 처리 효율성을 높인다고 한다.)

Scanner는 즉시 데이터가 전달되는데 왜 한번 버퍼를 거치는 BufferedReader가 빠른가? 하면

하드디스크, 키보드나 모니터와 같은 외부장치는 속도가 느리기 때문에 키보드가 눌릴때 마다 정보를 바로 전달하는것보다 버퍼에 한번에 묶어서 전달하는것이 더 빠르게 되는것이다.

**switch문도 if문으로 변경함**

switch문 같은 경우 jump table생성에 오버헤드 발생가능성이 있어서 case가 4개 이하인경우 if문을 사용하는것이 낫다고 한다.

\* 오버헤드란 -> 어떤 처리를 하기 위해 들어가는 간접적인 처리시간, 메모리등을 말한다.

\* jump table -> switch문에서 내부적으로 생성하는것  jump table의 크기는 case 값의 개수에 따라 달라진다. 


[switch문의 실행 순서에 대한 문서(C언어)](https://modoocode.com/16)

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.IOException; 

public class Main{

	
	public static void main(String[] args) throws IOException {

		int[] stack=new int[0];
		//Scanner scan=new Scanner(System.in);
		BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
		int count=Integer.parseInt(bf.readLine());
		String[] inputArr=new String[count];
		for(int i=0;i<count;i++)
		{
			inputArr[i]=bf.readLine();
		}
		for(int i=0;i<count;i++)
		{
			if(inputArr[i].contains("push"))
			{
				int num=Integer.parseInt(inputArr[i].replaceAll("push ", ""));
				//스택의 길이를 늘린다.
				 stack=push(num, stack);
			}else if(inputArr[i].contains("pop"))
			{
				stack=pop(stack);
			}
			else if(inputArr[i].contains("top"))
			{
				top(stack);
			}
			else if(inputArr[i].contains("empty"))
			{
				empty(stack);
			}
			else if(inputArr[i].contains("size"))
			{
				size(stack);
			}
		
		}
	
	}
	
	//정수 x를 스택에 넣는 연산 함수
	public static int[] push(int x,int[] stackArr)
	{
		//기존에 배열값을 카피한다(기존 요소를 유지하기 위함)
		int[] copyArr= stackArr;
		//스택의 길이를 늘린다.
        stackArr=new int[stackArr.length+1];
        //기존에 배열에 있는 값을 넣어준다.
        for(int i=0;i<copyArr.length;i++)
        {
        	stackArr[i]=copyArr[i];
        }
		//늘린 스택의 마지막 위치에 값을 넣어준다.
		stackArr[stackArr.length-1]=x;
		return stackArr;
		
	}
	//스택에서 가장위에 있는 정수를 빼고, 그 수를 출력한다.
	public static int[] pop(int[] stackArr)
	{
	
		if(stackArr.length==0)
		{
			System.out.println(-1);
			
		}else
		{
		//맨위값 출력
		System.out.println(stackArr[stackArr.length-1]);
		//기존에 배열값을 카피한다(기존 요소를 유지하기 위함)
		int[] copyArr= stackArr;
		//배열 크기를 줄인다.
		stackArr= new int[stackArr.length-1];
		//기존 배열의 값을 넣어준다.
		for(int i=0;i<copyArr.length-1;i++)
		{
			stackArr[i]=copyArr[i];
		}
		
		
		}
		
		return stackArr;
	}
	//스택의 정수 개수를 출력한다.
	public static void size(int[] stackArr)
	{
		//사이즈값 출력
		System.out.println(stackArr.length);

	} 
	//스택이 비어있으면 1 아니면 0을 출력한다.
	public static void empty(int[] stackArr)
	{
		if(stackArr.length==0)
		{
			System.out.println(1);
			
		}else
		{
			System.out.println(0);
		}
		//배열이 빈경우 체크 ->length로 체크한다. 헷갈린부분 배열은 [0]부터 시작해서 헷갈렸음.
		//length는 요소의 개수를 반환하니까 상관없다. 

	} 
	//스택의 가장 위에 있는 정수를 출력한다.
	public static void top(int[] stackArr)
	{
		if(stackArr.length==0)
		{
			System.out.println(-1);
			
		}else
		{
			//맨위값 출력
			System.out.println(stackArr[stackArr.length-1]);
		}
	}
	
}
```


뭐가 문제인가....

도저히 모르겠어서 풀이를 찾아봄.

[참고 풀이 링크](https://st-lab.tistory.com/175)

배열길이를 동적으로 하려다보니 사이즈를 정해 놓지않고 만들었는데

이 풀이에서는 명령어 개수로 미리 배열 사이즈를 잡아 놓고 푸는 방식이였다.

위 방법으로 만들어봤다.

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.IOException; 

public class Main{

//배열을 public static으로 생성
	public static int[] stack;
	public static int length=0;
	public static void main(String[] args) throws IOException {

		
		//Scanner scan=new Scanner(System.in);
		BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
		int count=Integer.parseInt(bf.readLine());
		String[] inputArr=new String[count];
        //count만큼 배열길이설정
		stack=new int[count];
		for(int i=0;i<count;i++)
		{
        //입력
			inputArr[i]=bf.readLine();
		}
		for(int i=0;i<count;i++)
		{
			if(inputArr[i].contains("push"))
			{
				int num=Integer.parseInt(inputArr[i].replaceAll("push ", ""));
				push(num);
			
				
			}else if(inputArr[i].equals("pop"))
			{
				System.out.println(pop());
			
			}
			else if(inputArr[i].equals("top"))
			{
			
				System.out.println(top());
			}
			else if(inputArr[i].equals("empty"))
			{

				System.out.println(empty());
			}
			else if(inputArr[i].equals("size"))
			{
				System.out.println(size());
				
			}
			
		

		}

	}
	
	//정수 x를 스택에 넣는 연산 함수
	public static void push(int x)
  {

		stack[length]=x;
		length++;
		
	}
	//스택에서 가장위에 있는 정수를 빼고, 그 수를 출력한다.
	public static int pop()
	{
		if(length==0)
		{
			return-1;
			
		}else
		{
		//맨위값 출력
	    int result=stack[length-1];
		//배열 크기를 줄인다.
	    length--;
		return result;


		}
	
	}
	//스택의 정수 개수를 출력한다.
	public static int size() 
	{

		 return length;
	} 
	//스택이 비어있으면 1 아니면 0을 출력한다.
	public static int empty() 
	{
		if(length==0)
		{
			return 1;
			
		}else
		{
			return 0;
		} 
		   
		  

	} 
	//스택의 가장 위에 있는 정수를 출력한다.
	public static int top() 
	{
		
	
		if(length==0)
		{
			return -1;
			
		}else
		{
			//맨위값 출력
			return stack[length-1];
		}

		 
	}
	
}
```

동적으로 배열길이를 늘렸다 줄였다 할수있게 구현해야하는줄 알았는데 이런식으로 해도 되는걸 알고 좀 허무했음..ㅜ


삽질의 흔적..
