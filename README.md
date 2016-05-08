import java.util.Random;
import java.util.Scanner;
public class BlackJack{
  public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    System.out.println("What is your name?");
    String userName1 = sc.nextLine();
    System.out.println("Hello " + userName1);
    Player p1 = new Player(userName1);
    int human_total1 = play_human1();
    System.out.println("What is your name?");
    String userName2 = sc.nextLine();
    System.out.println("Hello " + userName2);
    Player p2 = new Player(userName2);
    int human_total2 = play_human2();
    int computer_total = play_computer();
    calculate_winner(human_total1, human_total2, computer_total);
    Scanner z = new Scanner(System.in);
    System.out.println("Play again?");
    while(true){String v = z.nextLine();
    while(v.equals("Y")){
      
    }
    continue;
    }
  }
  
  public static int play_human1(){
    int[] cards;
    Scanner in = new Scanner(System.in);
    cards = new int [10];
    cards[0] = (int)(Math.random()*11)+1;
    cards[1] = (int)(Math.random()*11)+1;
    int human_total1 = cards[0] + cards[1];
    System.out.println("Player p1 got");
    System.out.println(cards[0] + " and "+ cards[1]+"   p1 total is " + (cards[0]+cards[1]));
    int money1;
    int bet1;
    money1 = 100;
    System.out.println("You have "+money1+"dollar.");
    System.out.println("How many money do you want to bet?");
    bet1 = in.nextInt();
    money1 = (money1 - bet1);
    System.out.println("Player1 bet "+ bet1 + "dollar.");
    System.out.println("Do you want another card (Y/N)");
    Scanner s = new Scanner(System.in);
    while(true){String x = s.nextLine();
    while(x.equals("Y")){
      human_total1 = human_total1 + (int)(Math.random()*11)+1;
      System.out.println("Player p1 "+ human_total1);
      System.out.println("Do you want another card (Y/N)");
      x = s.nextLine();
    }
    return human_total1;
    }
  }
  
  public static int play_human2(){
    int[] cards;
    Scanner in = new Scanner(System.in);
    cards = new int [10];
    cards[0] = (int)(Math.random()*11)+1;
    cards[1] = (int)(Math.random()*11)+1;
    int human_total2 = cards[0] + cards[1];
    System.out.println("Player p2 got");
    System.out.println(cards[0] + " and "+ cards[1]+"   p2 total is " + (cards[0]+cards[1]));
    int money2;
    int bet2;
    money2 = 100;
    System.out.println("You have "+money2+"dollar.");
    System.out.println("How many money do you want to bet?");
    bet2 = in.nextInt();
    money2 = (money2 - bet2);
    System.out.println("Player2 bet "+ bet2 + "dollar.");
    System.out.println("Do you want another card (Y/N)");
    Scanner c = new Scanner(System.in);
    while(true){String d = c.nextLine();
      while(d.equals("Y")){
        human_total2 = human_total2 + (int)(Math.random()*11)+1;
        System.out.println("Player p2 "+ human_total2);
        System.out.println("Do you want another card (Y/N)");
        d = c.nextLine();
      }
      return human_total2;
    }
   }
  
  public static int play_computer(){
    int computer_card1 = (int)(Math.random()*11)+1;
    int computer_card2 = (int)(Math.random()*11)+1;
    int computer_total = computer_card1 + computer_card2;
    System.out.println("Computer player got");
    System.out.println(computer_card1 + " and "+ computer_card2 + "   computer total is " + (computer_total));
    int money3;
    money3 = 100;
    Random random = new Random();
    int bet3 = random.nextInt(100);
    money3 = (money3 - bet3);
    System.out.println("comput bet "+ bet3 +"dollar.");
    return computer_total; 
  }
  
  public static void calculate_winner(int human_total1, int human_total2, int computer_total){
    if(human_total1<=21 && computer_total<human_total1 && human_total2<human_total1){
      System.out.println("Player p1 Wins");
      if(human_total1<=22){
        System.out.println("Player p1 got total betting money");
      }
    }
    else if(human_total2<=21 && computer_total<human_total2 && human_total1<human_total2){
      System.out.println("Player p2 Wins");
      if(human_total2<22){
        System.out.println("Player p2 got total betting money");
      }
    }
      else {
      System.out.println("Computer Wins");
      if(computer_total<21){
        System.out.println("Computer got total betting money");
      }
    }
  }

}
