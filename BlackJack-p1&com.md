import java.util.Random;
import java.util.Scanner;
public class BlackJack{
  public static void main(String[] args){
    Scanner a = new Scanner(System.in);
    System.out.println("Push Y");
    while(true){
      String b = a.nextLine();
      while(b.equals("Y")){
        Scanner sc = new Scanner(System.in);
        System.out.println("What is your name?");
        String userName1 = sc.nextLine();
        System.out.println("Hello " + userName1);
        Player p1 = new Player(userName1);
        int human_total1 = play_human1();
        int computer_total = play_computer();
        calculate_winner(human_total1,  computer_total);
        int bet_total;
        Scanner z = new Scanner(System.in);
        System.out.println("Play again?");
        while(b.equals("Y")){String v = z.nextLine();
          while(v.equals("Y")){
            return;
          }
        }
      }
      return ;
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
    while(true){
      String x = s.nextLine();
      while(x.equals("Y")){
        human_total1 = human_total1 + (int)(Math.random()*11)+1;
        System.out.println("Player p1 "+ human_total1);
        System.out.println("Do you want another card (Y/N)");
        x = s.nextLine();
      }
      return human_total1;
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

  public static void calculate_winner(int human_total1, int computer_total){
    if(human_total1<=21 && computer_total<human_total1){
      System.out.println("Player p1 Wins");
    }
    else{
      System.out.println("Computer Wins");
    }
  }
  
}
