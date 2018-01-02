---
layout: post
title:  "GameBase Class"
excerpt: "A series of board games including Tic-tac-toe, Gomoku, Ultimate Tic-tac-toe, and Sudoku created using 
inheritance from a base class, generic templates, and object-oriented design across files. "
project: true
comments: true
---

This project was created using C++ and can be run using power shell. All of the files and instructions on how to run it are linked below. 
The readme is in the text that follows. 

[GameBase Class](https://github.com/edwardbottom/GameBase)

copy control
	The use of copy control in the derived class is limited. 
	
	The copy construcor was not used in any of the derived classes because no copies of the class ever needed to be made. This is due to the fact that each derived class
	was only created once and that the smart pointer would self delete the object at the end of  the code and when a save game was loaded it was not done through a copy 
	constructor, but rather by reading in a file and using the default constructor to save space in memory and make use of the self deleting feature of the smart pointer. 

	The move constructor was not used in the derived classes as the data was never transfered between derived classes. Rather, the shared smart pointer
	replaced the only possible instance of the move constructor when data is moved from the base class to the derived class. After the data was moved to the derived
	class, it remained in that derived class and never needed to move back to the base class or to another derived class. 

	The copy-assignment operator overrides the instance of an existing object by copying the data. Again, this feature is not needed as there is only one existing instance of a derived class 
	and a base class. The use of writing to a file to save the game and the use of only one shared pointer serves the same purpose as this feature. 

	The move-assignment operator overides the instance of an existing object by moving the data from one object to another. This featur is not needed in this code 
	as at no point are there two instances of an object due to the use of a shared pointer which allows for the movement of the base object's features to another derived 
	objects features. 

	The destructor was not used in this code as the shared pointer automatically deletes itself when it is dereferneced, so creating and calling on a destructor 
	would be redundant. 


command line and testing
	Various tests were run to assess the the use of various error cases and exceptions. 

	The code was run with no inputs and with 3 inputs and the code returned the exception for the wrong number of inputs as expected. Intially, the usage message was not printed, 
	but thus was an easy fix. 

	The code was then run with typos in the input such as "Goku" or "TicTacTo" and the code returned a wrong inputs exceptions and the usage message as expected. 

	Next, each of the games, TicTacToe, Gomoku, and Sudoku were input with no save file present. In doing so, the user was able to begin the game without being prompted to 
	load a save file. 

	Then, the funcitonality of TicTacToe was tested by checking for all the possibile ways to win and the draw feature. It was found that all were working as previously expected,
	but one error did arise were the player was able to play at 4x4, but this was fixed  by simply changing a the values in the loop and ostream. Additionally, there was a
	problem with enetering in a piece that was too long like "3 3 0 0 0", but this was solved by adding in a conditional to check for extra information. 

	The funcitonality of Gomoku was then tested by checking all possible win patterns. All were funcitoning as expected and no problems occured while trying to load the game. 
	The error addressed previously in TicTacToe did occur, but was fixed at the same time as both Gomoku and TicTacToe use the same  prompt method. 

	Gomoku's done method was checked by modifying the constructor to fill the board with a combination of pieces that would warrant the game wass a draw. It worked as 
	expected and required to debugging. 

	The functionality of Sudoku was tested next. The first run of Sudoku did not yet have a way to delete the zeros that were read in by the code for blank space or to keep the 
	player from modifying the default values. This problem was addressed by creating a seperate constructor for the in the game_piece class that had a boolean value is modifiable. 
	The prompt method was then modified to acound for if a piece was modifiable. This worked on its first implementation. 

	Sudoku's done method was tested by loading in several files of completed Sudoku games from the internet into the constructor. This saved alot of time in actaully solving the 
	game. The first time a file was read in it did not work, so many print statements were added to find the error. It was found that the vertical and horizontal values were 
	working as expected, but the loops that checked if each box was working were not working. This was due to how the values were stored in the vector and how the vector was 
	checked. By properly resetting the vector and changing the values in the for loops, the problem was solved. 

	Sudoku was then also tested by using the other incomplete sudoku boards. Three were pulled from google and the fiels were greatly changed and varied based on spacing and line
	placement, but in every case, the code was able to read the values in as desired with no problems. 

	Sudoku was also tested for incorrect values by typing in a lot of invalid plays ranging from too fews, to too many, to blantantly wrong inputs. The prompt method handled every
	error ranging from incorrect words to too short and too long of inputs with no problem as expected because it was based on the prompt method of Gomoku and TicTacToe. 

	Next, the save features were tested in the code. At first, the game always asked if the user wanted to load their saved game even if a file was not saved. This isnt an error 
	per say given the game would still function and the user would be told no save was present, but it is annoying. By implementing a saveGame() and loadGame() method to 
	increase the modularity of the code and moving the placement of the methods slightly, the game would only ask the user if they wanted to load a saved game if the game was saved. 

	Just to make sure the save file was working perfectly, games were played with upwards of ten saves and for all three games functionality was maintined throughout the save 
	file and the interface worked as desired. 

	A problem did arise with the games not deleting their save files once the game was finished. This was solved by smply changing the order the construcotr read in the values and 
	have the code terminate the file after the game was finished. 



errors 
	A number of errors arose while creating this code before testing was actually done on the code. 

	One of the most problematic was that when a save file for gomoku and tictactoe was read in, the user was unable to play any other moves. This problem was difficult to pinpoint with
	print statements and my fist plan on solving it was to use the Sudoku prompt method was it did not have the problem. However, this did not work either and print states did not help 
	either as nothing was out of bounds. The error ended up coming from the >> operator as it was ignoring the blank space in a file for empty spaces. This was fixed by saveing a 0 for 
	each blank spot and adding a conditional to omit the 0 when the file was read in. 

	When the Sudoku ostream operator was being created, problems with the spacing of the board arose. Personally, I was very dissatisfied with the default loof of the ostream so 
	with the advice of a TA and the professor, I decreasaed the spacing of the board to make it easier on the eyes and added in more lines between squares to make it more obvious 
	were the distinctions between squares was. This solution, although different, I find to be significantly less straining on the eyes. 

	When the Sudoku board was first printed, the first set of squares had four squares in it instead of three. This was easily fixed by changing the bounads of the for loop so that each 
	square encompassed three squares instead of two, three and four squares each. 

	When the Sudoku file was first read in, the file actaully was read in upside down. This problem was easily fixed by reversing the order that the pieces were stored from the 
	file in the constructor. 

	It is also worth nothing that the way the files are saved in each game is different than the default files read in by the game. This was purely due to my preference of how to read 
	the files in. I found that reading them in CSV form and taking in inputs as the prompt method would to be more effiecent and intutive. This lead to a slight discrepency in the 
	Sukoku boards means of reading in files, but it in no way impacts how the code functions. 

	Some trouble arose while oringally implementing the shared pointer, but this ended up being due to syntax purposes and not correctly instantating and using
	the smart pointer. 

	There were some problems with reading in files into the Sudoku game, but this ended up stemming simply from the files not being placed in the debug folder with the code 
	that is actually run, so there was no way for the .exe to access the file. Simply moving the .txt file to the debug folder solved this problem. 


	Ultimate Tic-Tac-Toe 
	Ultimate Tic-Tac-Toe was completed using some variables as public. This is due to how the inheritance between the subclasses TicTacToe and gamke base worked and the inability to use friendship is this case. 
	All of the code minus the bonus will still run if they are set to private. Ultimate TicTacToe begins with a board of numbers, the player chooses a number and then plays a move in a sub board. The 
	next player then plays another move in a square based off that players move until the game is finished or the player quits. 
  
  Final Thoughts
  This project is one of the more lengthy assignments I have completed. The major takeaway from the assignment was how to use generic classes,
  templates, and copy control in the assignment. The code was significantly more modular than anything I have written so far and gave me 
  insight into how to structure code that spans multiple files and use generic templates. I ran into trouble with inheritance and actually
  had to delete a few files, but overall found this project to be every enjoyable to make and vital in understanding the foundations of code
  in C++. 



