
# 풀이
```java
import java.io.BufferedReader;
import java.io.InputStreamReader;

import java.io.IOException; 

public class Main {

	public static char[] alphabe;
	public static void main(String[] args) throws IOException {

		

		BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
		String word=bf.readLine();
		alphabe=new char[word.split("").length];
		//비교를 위한 현재 단어 저장 변수
		char current=word.charAt(0);
		//위치 
		int position=0;
		//처음 단어 접속
		alphabe[position]=current;
	
		for(int i=0;i<alphabe.length;i++)
		{
			char next=word.charAt(i);
		     if(current!=next&& Character.toUpperCase(current)!=next)
		     {
		    	 boolean check=true;
		    	//배열에서 기존에 next값이 들어있는지 체크
		    	 for(int j=0;j<alphabe.length;j++)
		 		{
		    		 if(alphabe[j]==next || alphabe[j]==Character.toUpperCase(next))
		    		 {
		    			 check=true;
		    			 break;
		    		 }else {
		    			 check=false;
		    		 }
		    		 
		    		 
		 		}
		    	 if(check!=true)
		    	 {
		    		 position++;
			    	 alphabe[position]=next;
			    	 current=next; 
		    	 }
		    	 
		  
		     }
		}
		
		checkCount(word);
	}
	
	public static void checkCount(String a)
	{
		//비교할 count
		int currentCount=0;
		//제일 빈도수가 많은 카운드
		int TopCount=0;
		//빈도수가 많은 알파벳
		char TopAlphabe=' ';
		for(int i=0;i<alphabe.length;i++)
		{
			 for(int j=0;j<alphabe.length;j++)
			 {
				 //대문자나 소문자랑 같으면..
				 if(alphabe[i]==a.charAt(j) || Character.toUpperCase(alphabe[i])==a.charAt(j))
				 {
					 currentCount++;
				 }
			 }
			 //카운터랑 맥스카운터비교해서 지금 카운터가 크면 값을 넣어준다.
			 if(currentCount>TopCount)
			 {
				 TopCount=currentCount;
				 TopAlphabe=alphabe[i];

			 }else if(currentCount==TopCount)
			 {
				System.out.println("?"); 
				return;
			 }
			 
			 currentCount=0;
		}
		System.out.println(TopAlphabe);
		
	}
	

	
}

```
위에도 콘솔에서 예제 입력했을때는 잘 작동했는데 백준에서 시간초과가 떠버려서 풀이 방식을 수정했다.
아스키코드를 이용한 방식이다.
```java
import java.io.BufferedReader;
import java.io.InputStreamReader;

import java.io.IOException; 

public class Main {


	public static void main(String[] args) throws IOException {

		

		BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
		String word=bf.readLine();
		int max=0;
		int topAlphabe='?';
		//알파벳 개수 만큼 배열 길이 설정
	    int[] alphabe=new int[26];
		if(word.length()>1)
		{
			 //입력된 단어길이 만큼 반복해서 검사
			for(int i=0;i<word.length();i++)
			{
				if(word.charAt(i)<'a')
				{
					alphabe[word.charAt(i)-'A']++;
				}else {
					alphabe[word.charAt(i)-'a']++;
				}


			}

			for(int i=0;i<alphabe.length;i++)
			{
			
				if(alphabe[i]>max)
				{
					max=alphabe[i];
					topAlphabe=i+65;
				}else if(alphabe[i]==max)
				{
					topAlphabe='?';
				
				}

			}	
		}else
		{
			topAlphabe=word.charAt(0);
		}
		System.out.println((char)topAlphabe);

	}


	
}
```
->계속 100% 채점진행된 상태에서 틀렸다하는데 반례를 못찾겠어서 일단 여기까지 하고 내일 다시 풀기로 함
