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



// TASK 2- STUDENT GRADE CALCULATOR

import java.util.Scanner;

public class gradecalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number of subjects:");
        int numSubjects = sc.nextInt();

        if(numSubjects <= 0){
            System.out.println("Please enter a valid number of the subjects:");
            return;
        }

        int totalMarks = 0;
        int maxMarksPerSubjects = 100;

        for(int i=1; i <= numSubjects; i++){
            System.out.println("Enter marks obtained in subjects " + i + "(out of 100):");
            int marks  = sc.nextInt();

     if(marks < 0 || marks > maxMarksPerSubjects){
    System.out.println("Marks should be in the range of 0 to 100 .Please enter valid marks.");
          i--;
            }
        else {
            totalMarks += marks;
        }
        }
    
      double averagePercentage  = (double) totalMarks / (numSubjects * maxMarksPerSubjects)*100;
      System.out.println("Total Marks:" + totalMarks);
      System.out.println("Average percentage: " + averagePercentage + "%" );

      String grade;

      if(averagePercentage >= 90){
        grade = "A+";
      }
      else if (averagePercentage >= 80){
        grade = "A";
      }
      else if(averagePercentage >= 70){
        grade = "B";
      }
      else if (averagePercentage >= 60){
        grade = "C";
      }
      else if (averagePercentage >= 50){
         grade = "D";
      }
      else {
        grade = "F";
      }

      System.out.println("Grade: " + grade);

      }

    }
