# 백준 1036번 그룹단어체커

## 문제
그룹 단어란 단어에 존재하는 모든 문자에 대해서, 각 문자가 연속해서 나타나는 경우만을 말한다. 예를 들면, ccazzzzbb는 c, a, z, b가 모두 연속해서 나타나고, kin도 k, i, n이 연속해서 나타나기 때문에 그룹 단어이지만, aabbbccb는 b가 떨어져서 나타나기 때문에 그룹 단어가 아니다.

단어 N개를 입력으로 받아 그룹 단어의 개수를 출력하는 프로그램을 작성하시오.

## 입력
첫째 줄에 단어의 개수 N이 들어온다. N은 100보다 작거나 같은 자연수이다. 둘째 줄부터 N개의 줄에 단어가 들어온다. 단어는 알파벳 소문자로만 되어있고 중복되지 않으며, 길이는 최대 100이다.

## 출력
첫째 줄에 그룹 단어의 개수를 출력한다.

## 답
```java

import java.util.*;

public class Main {

	public static void main(String[] args) {
	
		Scanner scan =new Scanner(System.in);
		//입력횟수
		int count=scan.nextInt();
		String[] inputArr= new String[count];

		//nextInt를 입력받고 친 개행문자를 읽는 용도
		scan.nextLine();
		//그룹 단어 카운트
		int groupWord=0;
		//count 수만큼 문자입력 
		for(int i=0;i<count;i++)
		{
			String input=scan.nextLine();

			inputArr[i]=input;
		}
		//단어 체크
		for(int i=0;i<inputArr.length;i++)
		{
			groupWord+=checkWord(inputArr[i]);
		}
		System.out.println(groupWord);
	}
	//그룹 단어 체크 함수
	public static int checkWord(String str)
	{
		//리턴할 int값 그룹단어면 1 아니면 0
		int result=1;
		//str를 분해해 char를 담을 배열 선언
		ArrayList<Character> inputArr_char=new ArrayList<Character>();
		//기존에 문자가 있을경우 체크할 boolean형
		boolean same=false;
		//현재 단어 
		char current=str.charAt(0);;
	
		    //단어수만큼 체크
			for(int i=0;i<str.length()-1;i++)
			{
				//다음 단어 세팅
				char next=str.charAt(i+1);
				//현재 문자와 다음문자가 다른경우
				if(current!=next)
				{
					//기존 배열에 값이 있는지 체크
					for(int j=0;j<inputArr_char.size();j++)
					{
						//기존배열에 값이 이있는경우 break;
						if(inputArr_char.get(j)==current)
						{
							same=true;
							break;
						}else
						{
							same=false;
							
						}
					
					}
					
                    //기존배열에 값이 없어야 배열에 추가
					if(same==false)
					{
						inputArr_char.add(current);
					}
					
					//기존에 배열에 들어간 char값과 비교
					for(int j=0;j<inputArr_char.size();j++)
					{
						//배열에 같은 값이 존재하는 경우 break
						if(inputArr_char.get(j)==next)
						{
							result=0;
							break;
						}
					}
				
				   //current에 next값 넣기
				   current=next;
				}
				
				
			}

	

		return result;
	}
	
	
	
}

```

## 참고 사항
- 문자열이 하나일때 고려
- 기존에 문자열이 있는지 고려
- 문자열을 받을때 Scanner의 scanLine()을 사용할경우 개행문자를 신경써야한다.

## 기타
-2번 틀림 
-풀이 중 반례
```

```
