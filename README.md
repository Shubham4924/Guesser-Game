# Guesser-Game
Using core java concept create Game

import java.util.Scanner;

class Launchgame {
	int guessNum;

	public int guessNumber() {
		Scanner sc = new Scanner(System.in);
		System.out.println("Guesser kindly guess the number");
		guessNum = sc.nextInt();
		return guessNum;
	}

}

class Player {
	int pguessNum;

	public int guessNumber() {
		Scanner sc = new Scanner(System.in);
		System.out.println("Player Kindly guess the number");
		pguessNum = sc.nextInt();
		return pguessNum;
	}
}

 //Umpire 
 
class Umpire {
	int numFromLaunchgame;
	int numFromPlayer1;
	int numFromPlayer2;
	int numFromPlayer3;

	public void collectNumFromLaunchgame() {
		Launchgame l = new Launchgame();
		numFromLaunchgame = l.guessNumber();

	}
	public void collectNumFromPlayer(){
		Player p1 = new Player();
		Player p2 = new Player();
		Player p3 = new Player();
		
		numFromPlayer1 = p1.guessNumber();
		numFromPlayer2 = p2.guessNumber();
		numFromPlayer3 = p3.guessNumber();
	}
  
	//comparison
  
 void compare(){
	if(numFromLaunchgame == numFromPlayer1) {
		if (numFromLaunchgame == numFromPlayer2 && numFromLaunchgame == numFromPlayer3) {
			System.out.println("Game tied all three players guessed correctly");
			
		}
		else if (numFromLaunchgame == numFromPlayer2) {
			System.out.println("Player 1 and Player 2 won the game");
		}
		else if (numFromLaunchgame == numFromPlayer3) {
			System.out.println("Player 1 and player 3 won");
		}
		else {
			System.out.println("Player 1 won the game");
		}
		
	}
	else if (numFromLaunchgame==numFromPlayer2) {
		if (numFromLaunchgame == numFromPlayer3) {
			System.out.println("Player 2 and player 3 won the game");
		}
		else {
			System.out.println("Player 2 won the game");
		}
		
	}
	else if (numFromLaunchgame==numFromPlayer3){
		System.out.println("Player 3 won the game");
	}
	else {
		System.out.println("Game Lost try Again");
	}
}
}

public class Guesser {

	public static void main(String[] args) {
		Umpire u = new Umpire();
		u.collectNumFromLaunchgame();
		u.collectNumFromPlayer();
		u.compare();
		

	}

}
