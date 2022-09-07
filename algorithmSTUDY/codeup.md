
# 코드업 기초 100제
[코드업 기초 100제](https://codeup.kr/problemsetsol.php)
## 입출력 문제
### 1001
```java
import numpy as np
public class Main {

	public static void main(String[] args) {
		System.out.println("Hello");
	}
}
```
### 1002
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("Hello World");
	}
}
```
### 1003
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("Hello\nWorld");
	}
}
```
### 1004
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("'Hello'");
	}
}
```
### 1005
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("\"Hello World\"");
		
	}
}
```
### 1006
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("\"!@#$%^&*()\"");
		
	}
}
```
### 1007
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("\"C:\\Download\\hello.cpp\"");
		
	}
}
```
### 1008
```java
public class Main {

	public static void main(String[] args) {
		System.out.println("\u250C\u252C\u2510\n\u251C\u253C\u2524\n\u2514\u2534\u2518\n");
	
	}
}
```
### 1010
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
	
		int n;
		Scanner scanner=new Scanner(System.in);
		n=scanner.nextInt();
		System.out.println(n);
	
	}
}
```
### 1011
```java
import java.util.Scanner;

public class Main{
    
    public static void main(String[] args)
    {
        char x;
        Scanner scan=new Scanner(System.in);
        x=scan.next().charAt(0);
        System.out.println(x);
    }
}
```
### 1012
```java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        
        double f;
        Scanner scan=new Scanner(System.in);
        f=scan.nextDouble();
        System.out.printf("%f",f);
        
    }
    
}
```
### 1013
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
	
	  int a,b;
	  Scanner scan=new Scanner(System.in);
	  a=scan.nextInt();
	  b=scan.nextInt();
	  System.out.println(a+" "+b);
	  
	
	}
}
```
### 1014
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
	
	  char a,b;
	  Scanner scan=new Scanner(System.in);
	  a=scan.next().charAt(0);
	  b=scan.next().charAt(0);
	  System.out.println(b+" "+a);
	  
	
	}
}
```
### 1015
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
	
	  float a;
	  Scanner scan=new Scanner(System.in);
	  a=scan.nextFloat();
	  System.out.printf("%.2f",a);
	
	}
}
```
### 1017
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
	
             int a;
             Scanner scan=new Scanner(System.in);
             a=scan.nextInt();
             System.out.println(a+" "+a+" "+a);
	}
}
```
### 1019
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String input;
		Scanner scan=new Scanner(System.in);
		input=scan.next();
		String[] inputarr=input.split("\\.");
	    String yyyy= inputarr[0];
	    String mm=inputarr[1];
	    String dd=inputarr[2];
	    if(yyyy.length()<4)
	    {
	    	for(int i=yyyy.length();i<4;i++)
	    	{
	    		yyyy="0"+yyyy;
	    	}
	    }
	    if(mm.length()<2)
	    {
	    	mm="0"+mm;
	    }
	    if(dd.length()<2)
	    {
	    	dd="0"+dd;
	    }
	    System.out.println(yyyy+"."+mm+"."+dd);
	}
}
```
-다른풀이(이편이 코드도 짧고 간단하다)
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String input;
		Scanner scan=new Scanner(System.in);
		input=scan.next();
		String[] inputArr=input.split("\\.");

		int a=Integer.valueOf(inputArr[0]);
		int b=Integer.valueOf(inputArr[1]);
		int c=Integer.valueOf(inputArr[2]);
		System.out.printf("%04d.%02d.%02d",a,b,c);
	}
}

```
### 1020
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String input;
		Scanner scan=new Scanner(System.in);
		input=scan.next();
		String[] inputArr=input.split("-");

		System.out.println(inputArr[0]+inputArr[1]);
	}
}
```
### 1021
```java

import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String a;
		Scanner scan=new Scanner(System.in);
		a=scan.next();
		System.out.println(a);
	}
}

```
### 1022

```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String a;
		Scanner scan=new Scanner(System.in);
		a=scan.nextLine();
		System.out.println(a);
	}
}

```

java로 문제를 풀다보니 입출력문제 답이 비슷비슷하다..

###  1023
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String a;
		Scanner scan=new Scanner(System.in);
		a=scan.next();
		int b=Integer.parseInt(a.split("\\.")[0]);
		int c=Integer.parseInt(a.split("\\.")[1]);
		System.out.println(b+"\n"+c);
	}
}
```
### 1024
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String a;
		Scanner scan=new Scanner(System.in);
		a=scan.next();
		for(int i=0;i<a.length();i++)
		{
			System.out.printf("\'%c\'\n", a.charAt(i));
		}
	}
}
```
### 1025
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String input;
		Scanner scan=new Scanner(System.in);
		input=scan.next();
		String[] inputArr=input.split("");
		int count=4;
		for(int i=0;i<input.length();i++)
		{
		    int b=Integer.valueOf(inputArr[i]);
		    if(count>0)
		    {
		    	System.out.printf("[%d]\n",b*(int)Math.pow(10, count));	
		    }else
		    {
		    	System.out.printf("[%d]\n",b);	
		    }
			
			count=count-1;
		}
	}
}

```
### 1027
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String input;
		Scanner scan=new Scanner(System.in);
		input=scan.next();
		String[] inputArr=input.split("\\.");
		int yyyy=Integer.valueOf(inputArr[0]);
		int mm=Integer.valueOf(inputArr[1]);
		int dd=Integer.valueOf(inputArr[2]);
		
		System.out.printf("%02d-%02d-%04d",dd,mm,yyyy);
		
		
	}
}
```
### 1026
```java 
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		String input;
		Scanner scan=new Scanner(System.in);
		input=scan.next();
		String[] inputArr=input.split(":");
		
		if(Integer.valueOf(inputArr[1])>0)
		{
			System.out.println(inputArr[1]);	
		}else
		{
			System.out.println("0");
		}
		
		
	}
}
```
분을 출력하는 문제였는데 입력값이 0이면 00으로 출력해야해서 if문으로 처리했다.
### 1028
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		long a;
		Scanner scan=new Scanner(System.in);
		a=scan.nextLong();
		System.out.println(a);

	}
	
}
```
### 1029
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	

		double d;
		Scanner scan=new Scanner(System.in);
		d=scan.nextDouble();
		System.out.printf("%.11f", d);
		}
	
}
```
### 1030
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	

		long a;
		Scanner scan=new Scanner(System.in);
		a=scan.nextLong();
		System.out.println(a);
		
	}
	
}
```
### 1031 - 1033
 10진수를 8진수로 출력하는문제
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		int input;
		Scanner scan=new Scanner(System.in);
		input=scan.nextInt();
		System.out.printf("%o",input);
		
	}
	
}

```
 서식문자로 변환해서 출력하면되는 간단한 문제였으나 초반에 코드로 변환을하려고 하니까 잘안풀렸다.
 몫과 나머지를 따로 저장해서 합치면 되지않을까했는데 변환이 잘 안되서 고민했다
 
 인터넷에서 찾은 해결방법
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		System.out.println(changeNumber(100, 8));
	}
	
	public static String changeNumber(int num,int i)
	{
	     //항상 변수 초기화를 하는 습관을 들일것
		String answer="";
		int remainder=0;
		
		while(num !=0)
		{
			remainder=num%i;
			//10진수니까 조건들어감
			if(num%i<10)
			{
				answer =remainder+answer;
			}else
			{
			        //16진수 변환을 위한 코드
				answer=(char)(remainder+55)+answer;
			}
			num /=i;
		}
		
		return answer;
	}
	
}

```

### 1034
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan=new Scanner(System.in);
		int a=Integer.valueOf(scan.next(),8);
		System.out.println(a);
	}
	
	
}
```
- 방법1 valueOf로 변환한다.
- 방법2 parseInt로 변환한다.
- 방법3 Scanner로 입력받을때 nextInt(n)을 사용한다. n의 값에따라 n진수로 받는다.

### 1035
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan=new Scanner(System.in);
		int a=scan.nextInt(16);
		System.out.printf("%o",a);
	}
	
	
}

```
### 1036
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan=new Scanner(System.in);
		char a=scan.next().charAt(0);
		System.out.printf("%d",Integer.valueOf(a));
	}
	
	
}
```
### 1037
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan=new Scanner(System.in);
		int a=scan.nextInt();
		System.out.println((char)a);
	}
	
	
}

```
### 1038 - 1039
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan=new Scanner(System.in);
		String input=scan.nextLine();
		String[] inputArr=input.split("\\s");
		long a= Long.parseLong(inputArr[0]);
	    long b= Long.parseLong(inputArr[1]);
		System.out.println(a+b);
	}
	
	
}
```
*참고 int와 long의 범위(계산의 결과가 int범위를 넘어가는지 확인할것!
 -   int: -2,147,483,648 ~ 2,147,483,647
 -   long: -9223372036854775808 ~ 9223372036854775807
### 1010
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan= new Scanner(System.in);
		int a=scan.nextInt();
		System.out.println(-a);
	}
	
	
}
```
### 1041
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan= new Scanner(System.in);
		char a=scan.next().charAt(0);
		System.out.println((char)(a+1));
	}
	
	
}
```
### 1042
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan= new Scanner(System.in);
		String input= scan.nextLine();
		String[] inputArr=input.split("\\s");
		int a=Integer.valueOf(inputArr[0]);
		int b=Integer.valueOf(inputArr[1]);
		System.out.println(a/b);
	}
	
	
}
```
- 묵시적 (데이터)형변환 : 자동으로 값의 자료형이 바뀌는 것
- 명시적 (데이터)형변환 : 어떤 값이나 결과의 자료형을 강제로 바꾸는 것
### 1043
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan= new Scanner(System.in);
		String input= scan.nextLine();
		String[] inputArr=input.split("\\s");
		int a=Integer.valueOf(inputArr[0]);
		int b=Integer.valueOf(inputArr[1]);
		System.out.println(a%b);
	}
	
	
}
```
### 1044
 - 증감연산자 활용
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan= new Scanner(System.in);
		long a=scan.nextInt();
		System.out.println(++a);
	}
	
	
}
```
### 1045
```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan= new Scanner(System.in);
		String input= scan.nextLine();
		String[] inputArr=input.split("\\s");
		int a=Integer.valueOf(inputArr[0]);
		int b=Integer.valueOf(inputArr[1]);
		long plus=a+b;
		System.out.println(plus);
		System.out.println(a-b);
		long multi=a*b;
		System.out.println(multi);
		System.out.println(a/b);
		System.out.println(a%b);
		System.out.printf("%.2f",(float)a/b);
	}
	
	
}

```
