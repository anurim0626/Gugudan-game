# Gugudan-game
Gugudan game 을 실행합니다.
import java.util.*;
import java.io.*;

public class Gugudan_Game
{
  public static void main(String[] args) throws IOException
  {
    int x, y;                                                         //사용자가 입력하는 인수(x, 구구단), 컴퓨터가 발생하는 난수(y, 곱해지는수)
    Random r= new Random();                            //Random 인스턴스 선언

    if(args.length==1){                                                   //사용자가 입력하는 arguments 배열에 데이터가 1개 있는 경우, 
                                                                                       //사용자가 1개 데이터 입력한 경우
      x= Integer.valueOf(args[0]).intValue();          
                                                         //입력한 문자형 데이터를 랩퍼클래스(Integer)를 이용하여 정수형으로 변환하여 저장
    }else{                                                                    //사용자가 인수를 입력하지 않았거나, 2개 이상 입력한 경우
      x= Math.abs(r.nextInt() % 9) + 1;                  //1~9까지의 난수를 발생시킴
    }

    y= Math.abs(r.nextInt() % 9) + 1;                //곱해지는 수 1~9까지 난수발생
   
    int num= x*y;                                          //사용자 입력 수(구구단) * 난수(1~9) 값 저장

    System.out.println();
    System.out.println("* 구구단 "+ x + "단에 대한 문제입니다");
    System.out.println();


    System.out.print(x +" * "+ y +" = ");
 
    BufferedReader in= new BufferedReader(new InputStreamReader(System.in));    
    //데이터를 읽어들여 임시저장하는 BufferedReader() 인스턴스 in 생성
                                          
    String user;
    user= in.readLine();                                                             //문자형변수 user 에 사용자가 입력한 값을 받아들여 저장

    int inputNum= new Integer(user).intValue();                  
                                                           //사용자가 입력한 값을 랩퍼클래스(Integer) 이용하여 정수형으로 변환 후 저장

    if(num==inputNum){                 
      System.out.println("맞았습니다!");                                   //사용자가 입력한 값(inputnum)과 x*y값 num이 같은 경우
    }else{
      System.out.println("틀렸습니다. 정답은 "+ num +"입니다.");           // 틀린 경우
    }
  }
}
