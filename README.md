# code-soft

// TASK 1 - NUMBER GAME 

import java.util.Random;
import java.util.Scanner;
class game_1{
    public int number;
    public int inputNumber;
    public int noOfGuesses = 0;

    public int getNoOfGuesses(){
        return noOfGuesses;
    }
    public void setNoOfGuesses(int noOfGuesses){
        this.noOfGuesses = noOfGuesses;
    }

// CONSTRUCTOR generate random number
     game_1(){
    Random ran = new Random();

      this.number = ran.nextInt(100);
    }
    void takeUserInput(){
        System.out.println("Guess the number");
        Scanner sc = new Scanner(System.in);
        inputNumber = sc.nextInt();
    }
    boolean isCorrectNumber(){
        noOfGuesses++;
        if (inputNumber == number){
System.out.format("Yes you guessed it right,it was %d\n You guessed it in %d attemps "
, number,noOfGuesses);
            return true;
        }
        else if(inputNumber < number){
            System.out.println("Too low..");
        }
        else if(inputNumber > number){
            System.out.println("To high..");
        }
         return false;
        }

    }
public class gamenum{
    public static void main(String[] args) {
        game_1 g = new game_1();
        boolean b = false;
        while(!b){  
        g.takeUserInput();
        g.isCorrectNumber();
        
    }
}
}

