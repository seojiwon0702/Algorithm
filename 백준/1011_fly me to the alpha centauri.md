# 문제
![flat me to the alphacentauri](https://user-images.githubusercontent.com/78357979/135806052-ae7ddfbf-7c92-4e93-b855-2fce658fbced.jpg)
# 코드
```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class Main {

	public static void main(String[] args) throws NumberFormatException, IOException {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = null;
		StringBuilder sb = new StringBuilder();
		
		int T = Integer.parseInt(br.readLine());
		
		while(T-->0) {
			st = new StringTokenizer(br.readLine());
			int x = Integer.parseInt(st.nextToken());
			int y = Integer.parseInt(st.nextToken());
			
			int dist = y-x; // 구해야하는 거리
			long n=1; // 확인하는 거리
			int m=1; // 증가값
			int answer=1; // 최소 이동횟수
			boolean flag = false;
			while(n<dist) {
				n+=m;
				answer+=1;
				if(flag) m++;
				flag = !flag;
			}
			if(dist<n) answer--;
			sb.append(answer+"\n");
		}
		System.out.println(sb.toString());
	}

}
```
