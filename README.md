using System;
					
public class Program
{
	public static void Main()
	{

		int myVariable;
		int j = 1;
		myVariable = j; 						
		bool lobby = true;
		Console.Write("Welcome to Rock Paper Scissors! "); //Game welcome
		while (lobby) 
		{
		  Console.WriteLine("Click E to exit");
		string ans = Console.ReadLine();
		if (ans == "E" || ans == "e") //Since C# is caps sensitive, this code detects caps and lowers
			lobby = false;
		}
		
		bool validans = false;
		int rounds = 0;
		while(!validans)
		{
		Console.WriteLine("How much rounds would you like to play?");
		 rounds = Convert.ToInt32(Console.ReadLine());
			if ( rounds < 0 || rounds == 0){
				Console.WriteLine("Invalid input Try again");
			}else{
				validans = true;
				Console.Clear();
			}
		
		}
		int points1 = 0;
		int points2 = 0;
		while (rounds > 0)
	{	
		rounds = rounds - 1;
		bool valid = false;
		while (!valid)
		{
		valid = false;
		Console.WriteLine("r for rock, s for scissors, p for paper"); //Asking for input
		string i = Console.ReadLine();
		if (i == "r" || i == "R"){
			Console.Clear();
			Console.WriteLine("Player chose rock");
			valid = true;
			myVariable = 0;
		}else if (i == "s" || i == "S"){
			Console.Clear();
			Console.WriteLine("Player chose scissors");
			valid = true;
			myVariable = 1;
		}else if (i == "p" || i == "P"){
			Console.Clear();
			Console.WriteLine("Player chose paper");
			valid = true;
			myVariable = 2;

			}
		}
		
		Random rand = new Random(); //Randomised move for opponent
		int randomValue = rand.Next(0,2);
		int sum = randomValue - myVariable;
		if (randomValue == 0){
			Console.WriteLine("Opponent chose rock");
		}else if (randomValue == 1){
			Console.WriteLine("Opponent chose scissors");
		}else if (randomValue == 2){
			Console.WriteLine("Opponent chose paper");
		} 
		if (sum == 2 || sum == -1){
			Console.WriteLine("You lost");  	  				    //Key: 0 = draw | 1 = win | 2 = lose | -1 = lose | -2 = win
			points2 = points2 + 1; //Point increase for computer
		}else if (sum == 1 || sum == -2){											//Rock = 0
			Console.WriteLine("You win!");											//Scissors = 1
			points1 = points1 + 1;	//Points increase for player
		}else if (sum == 0){															//Paper = 2		
				Console.WriteLine("It's a draw!");	 //Draw								//Results are subtracted
				
			
	}
			
		}Console.WriteLine("Round over! You have " + points1 + " points, your opponent has " + points2 + " points");
			Console.WriteLine("Thank you for playing!");
			
		
		}
}
