## Addition Game V- 3.0

## Introduction
This is the addition game but accomplished using method calls and for loops and now adding arrays.

## Outline
1. 	Define the variables we will use
2.	 Create a loop that loops through the desired number of rounds.
3.	If the user answers correctly award them points and increase the difficulty; if not do not award 	points, display the correct answer and decrease the difficulty. 
4. 	Once the game is over display the users final score.

## Reference and Literature
* Liang, Y. (2014). *Introduction to Java programming: Comprehensive version* (Tenth ed.).
* Dr. Evert and the class work posted on git hub.
* Previous work done on the addition game.

## Code
``` java

import java.util.Scanner;
public class MathGameV2 {
	public static void main(String[] args) {

	// call the addition game.
	AdditionGameMethod();

	    }
	public static void AdditionGameMethod() {
	System.out.println("Hello, let's play a game.");
	        
	int [] gameVariables = new int[3];
	gameVariables[0]=5;
	int roundCount = 4;
	// int hardness = gameVariables[0];
	gameVariables[1] = 5;
	gameVariables[2] = 0;
	boolean isAnswerCorrect;

	for(int counter = 1; counter <= roundCount; counter=counter+1){
	System.out.println("Round: " + counter);


	// Call the get and check answer method
	isAnswerCorrect = getAndCheckAnswerMethod(gameVariables);

	if(isAnswerCorrect){
	System.out.print("Your score was " + gameVariables[2]);
	gameVariables[2] = gameVariables[2] + gameVariables[0];
	System.out.println(" and is now " + gameVariables[2]);
	if(counter < roundCount){
	System.out.print("Your hardness was " + gameVariables[0]);
	gameVariables[0] = gameVariables[0] * gameVariables[1];
	System.out.println(" and is now " + gameVariables[0]);
	                }
	}else{
	if((gameVariables[0] > 5) && (counter < roundCount)){
	System.out.println("Your hardness was " + gameVariables[0]);
	gameVariables[0] = gameVariables[0] / gameVariables[1];
	System.out.println(" and is now " + gameVariables[0]);
	                }
	            }
	        }
	System.out.print("\nThe game is complete.");
	System.out.println(" Your final score is: " + gameVariables[2]);
	    }

	public static boolean getAndCheckAnswerMethod(int gameVariables[]) {

	int randomNumber1 = (int)(Math.random()*gameVariables[0]);
	int randomNumber2 = (int)(Math.random()*gameVariables[0]);
	System.out.println("\nWhat is " + randomNumber1 + " plus " + randomNumber2 + "?");
	Scanner input = new Scanner(System.in);
	int studentAnswer = input.nextInt();
	int correctAnswer = randomNumber1 + randomNumber2;
	if (studentAnswer == correctAnswer){
	System.out.println("Good work, your answer was correct.");
	return true;
	        }else {
System.out.println("Good try, but the correct answer was " + correctAnswer);
	            return false;
	        }

	    }
}
```

## Console Output
```
Hello, let's play a game.
Round: 1

What is 2 plus 4?
6
Good work, your answer was correct.
Your score was 0 and is now 5
Your hardness was 5 and is now 25
Round: 2

What is 8 plus 7?
15
Good work, your answer was correct.
Your score was 5 and is now 30
Your hardness was 25 and is now 125
Round: 3

What is 75 plus 115?
190
Good work, your answer was correct.
Your score was 30 and is now 155
Your hardness was 125 and is now 625
Round: 4

What is 607 plus 219?
226
Good try, but the correct answer was 826

The game is complete. Your final score is: 155
```

## Summary
We have now added arrays into the addition game and I am curious what more we will do with it to make it better. When we started I was unsure how we were going to implement arrays into this but after doing it in class with Dr Evert I understand better.  We used the array to store all of the game variables together so they could be transported in and out of methods something I never would have thought to do.  This showed how versatile arrays can be in coding and how they make things so much easier.

