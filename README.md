using System;
					
public class Program
{
	public static void Main()
	{
		int myVariable;
		int j = 1;
		myVariable = j;
		bool lobby = true;
		while (lobby)
		{
		  Console.WriteLine("Click E to exit");
		string ans = Console.ReadLine();
		if (ans == "E" || ans == "e")
			lobby = false;
		}
		
		
		while (true)
	{	
		bool valid = false;
		while (!valid)
		{
		valid = false;
		Console.WriteLine("r for rock, s for scissors, p for paper");
		string i = Console.ReadLine();
		if (i == "r" || i == "R"){
			Console.WriteLine("Player chose rock");
			valid = true;
			myVariable = 0;
		}else if (i == "s" || i == "S"){
			Console.WriteLine("Player chose scissors");
			valid = true;
			myVariable = 1;
		}else if (i == "p" || i == "P"){
			Console.WriteLine("Player chose paper");
			valid = true;
			myVariable = 2;

			}
		}
		
		Random rand = new Random();
		int randomValue = rand.Next(0,2);
		int sum = randomValue - myVariable;
		if (randomValue == 0){
			Console.WriteLine("Opponent chose rock");
		}else if (randomValue == 1){
			Console.WriteLine("Opponent chose scissors");
		}else if (randomValue == 2){
			Console.WriteLine("Opponent chose paper");
		} 
		if (sum == 0){
			Console.WriteLine("It's a draw!");
		}else if (sum == 1 || sum == -2){
			Console.WriteLine("You win!");
		}else if (sum == 2 || sum == -1){
				Console.WriteLine("You lost");
			
	}
		}
	
		
		}
}
