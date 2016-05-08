import java.util.Scanner;
public class BlackJack{
  public static void main(String[] args){
    Player p1 = new Player("Mark");
    int human_total1 = play_human1();
    Player p2 = new Player("maria");
    int human_total2 = play_human2();
    int computer_total = play_computer();
    calculate_winner(human_total1,human_total2,computer_total);
  }
  
  public static int play_human1(){
    int[] cards;
    Scanner in = new Scanner(System.in);
    cards = new int [10];
    cards[0] = (int)(Math.random()*11)+1;
    cards[1] = (int)(Math.random()*11)+1;
    int human_total1 = cards[0] + cards[1];
    System.out.println("Mrak got");
    System.out.println(cards[0]+" and "+cards[1]);
    System.out.println(cards[0]+cards[1]);
    System.out.println("Do you want another card (Y/N)");
    String s = in.nextLine();
    while(s.equals("Y")){
      human_total1 = human_total1 + (int)(Math.random()*11)+1;
      System.out.println("Mark "+ human_total1);
      System.out.println("Do you want another card (Y/N)");
      s = in.nextLine();
    }
    return human_total1;
  }
  
  public static int play_human2(){
    int[] cards;
    Scanner in = new Scanner(System.in);
    cards = new int [10];
    cards[0] = (int)(Math.random()*11)+1;
    cards[1] = (int)(Math.random()*11)+1;
    int human_total2 = cards[0] + cards[1];
    System.out.println("Maria got");
    System.out.println(cards[0]+" and "+cards[1]);
    System.out.println(cards[0]+cards[1]);
    System.out.println("Do you want another card (Y/N)");
    String s = in.nextLine();
    while(s.equals("Y")){
      human_total2 = human_total2 + (int)(Math.random()*11)+1;
      System.out.println("Maira "+ human_total2);
      System.out.println("Do you want another card (Y/N)");
      s = in.nextLine();
    }
    return human_total2;
  }
  
  public static int play_computer(){
    int computer_card1 = (int)(Math.random()*11)+1;
    int computer_card2 = (int)(Math.random()*11)+1;
    int computer_total = computer_card1 + computer_card2;
    System.out.println("Computer player got");
    System.out.println(computer_card1+" and "+computer_card2);
    System.out.println(computer_total);
    return computer_total; 
  }
  
  public static void calculate_winner(int human_total1, int human_total2, int computer_total){
    if(human_total1<=21 && computer_total<human_total1 && human_total2<human_total1){
      System.out.println("Mark Wins");
    }
    else if(human_total2<=21 && computer_total<human_total2 && human_total1<human_total2){
      System.out.println("Maria Wins");
    }
    else{
      System.out.println("Computer Wins");
    }
  }
  
}
