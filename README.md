Download Link: https://assignmentchef.com/product/solved-solvedpig-game-full-project
<br>
FULL PROJECT. IF IN NEED OF SINGLE PARTS PLEASE CONTACT : <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="147271787b702061547379757d783a777b79">[email protected]</a>

Overview

Pig is a folk jeopardy dice game described by John Scarne in 1945, and was an ancestor of the modern game Pass the Pigs® (originally Called PigMania®).

Here are the rules: two players race to reach 100 points. Each turn, a player repeatedly rolls a die until either a 1 is rolled or the player holds and scores the sum of the rolls (i.e. the turn total). At any time during a player’s turn, the player is faced with a choice: roll or hold.

Roll – If the player rolls a

1: the player scores nothing and it becomes the opponent’s turn.2 – 6: the number is added to the player’s turn total and the player’s turn continues.

Hold – The turn total is addedto the player’s score and it becomes the opponent’s turn.

In Part 1 – your program will consist of the following classes:

Die – has a static method to roll a diePigPlayer – an abstract class representing the player’s name, current score, and win record.UserPigPlayer – a class that asks the user if they want toroll or holdPigGame – plays Pig

For Part 2 – you will add the following classes:

SimpleHoldPlayer – a computer player that uses a strategy to roll until a value is reached (the first of four computer strategies)PigGame – plays Pig (updated for the computer player)Simulations – runs several simulations to find out whichstrategies work wellFourTurnsPlayer – the second of four computer strategiesWatchOpponentPlayer – the third of four computer strategiesStrategicPlayer – the fourth of four computer strategiesPigGameGUI – a graphical user interface for the PigGame. I have written this class for you, but you will need to make sure you write your classes exactly to specifications for your code to work with my interface.When you have finished, you will have two ways of running your program. The text program will be run by running themain() method in PigGame. You will also be able to run a graphical version, by running the main method inPigGameGUI.You will write three separate classes that will “have” each other as instance variables or local variables: Die, PigGameand Simulations.A PigGame “has” two PigPlayer objects, and a Simulations “has a”PigGame. These three classes will not be related to each other through inheritance. You will also writean abstract PigPlayer class that has five child classes:

This is the first 2 weeks of a 4 week project. I would suggest using the following deadlines to keep yourself on track. (Completing the class includes testing and debugging! Don’t wait until the last week to test and debug!)

Week 1: complete the Die, PigPlayer, and UserPigPlayer classesWeek 2: completethe PigGame class to allow two users to play against each other

Die

You should begin by writing the Die class. It should have an instance variable sides, which you can initialize to 6. You should then write four methods (plus anyconstructors you find useful):public static int roll()public void setSides(int numberOfSides)public int getSides()public int rollDie()

The static roll() method will assume a six sided die, whereas the non static rollDie() method will allow you to create special die with as many sides as you like (positive numbers only). Write the static roll()method first! In the static roll() method, youcan call the static Math.random (Links to an external site.) to help you get random numbers. Math.random returns a random number between 0 and 1 (including 0 but not 1). Math.random() returns a random floating point number (a double) between 0 and 1, possibly 0 but never 1, which is sometimes described as the range [0, 1). First think about what math would be required to convert the range [0, 1) to [0, 6), or a floating point number between 0 and 6. Write your static roll() method so it calls Math.random(), converts to the range [0, 6) and then returns an int that is 0,1,2,3,4 or 5.You should then write a main() method that checks that your die will roll numbers 0 – 5.This main() method should be inside of the Die class. Write a loop that calls the static roll() method several times and make sure all six numbers show up (approximately the same number of times). For example, if you run the roll() method 600 times, you hope to have all six numbers appear between 90-110 times (although occasionally you’ll have a number appear only 80 times). Once you’re sure everything works, go back andmodify the roll method so it returns a number between 1-6 (instead of 0-5).After your static roll() method return numbers between 1 to 6, generalize your algorithm in the non-static rollDie() method so the Die class works for more sides.

PigGame

First create an empty PigGame class. Then add a static constant to this class:a GOAL that represents the winning score (usually 100, but you could change itto something smaller for debugging). Static constants and class variables aredescribed in Section 6.2 of your textbook (pages 390-391).

PigPlayer

Next write the PigPlayer class.It should have one String instance variable (the player’s name) and at leasttwo int instance variables (current score and total number of games won). Weneed to keep track of the number of games won to run our simulations later.

This PigPlayer class should have the following methods:

a constructor that takes a name as a String

public void setName(String) and public StringgetName()

public void reset() – should get the player ready for anew game by setting the score to 0

public void addPoints(int turnTotal) – should add the turntotal to the player’s score. It should also increment the numberof wins if the player’s score is now greater than or equal to thegoal.

public boolean won() – returns true if this player has wonthe game (reached the GOAL)

public int getScore() – returns the player’s current score

public int getWinRecord() – returns the number of gamesthis player has won

public String toString() – returns a String with the player’sname and score

Your methods should not have 100 hard-coded, but use the GOAL constant from the PigGame. This will make it easier to debug your code later.

You should write a short main() method in the PigPlayer class to check thatall your methods work correctly.

Then add an abstract method:

public abstract boolean isRolling(int turnTotal, int opponentScore);

This abstract method will return whether or not the player wants to roll the die. You’ll need to comment out your main method once you make the PigPlayer class abstract. But don’t delete the method – it will be a good start for testing the UserPigPlayer class.

UserPigPlayer

Next write the UserPigPlayer class. This class should be a child of the PigPlayerclass, which means you’ll need to write a constructor and the isRolling() method:

The constructor should take a String argument (the name of the player).

The isRolling() method in the UserPigPlayer class should print out the turn total andprompt the user if they want to roll or hold. You’ll want to print from the screen and read from the keyboard. Since the user will be rolling more often than holding, use the Enter key (empty input) to indicate the user wants to roll. Any other input (a line of non-zero length) will indicate the user wants to hold. Don’t worry about not usingthe opponentScore parameter – this is information that will be used by futurePigPlayer classes, but not this one.

The code below shows you how you can check if the user presses the Enterkey, or enters another character: (This assumes a Scanner object has beencreated in the constructor for the UserPigPlayer class.)

System.out.println(“Press enter to roll again, anythingelse to hold.”);

String ch = keyboard.nextLine();

if (ch.length() == 0) {

return true;

}

else {

return false;

}

If the user presses the Enter key, the nextLine() method returns an emptyString which is length 0. If the user presses anything other than Enter,the nextLine() method will return a String that has a length 0.

You should be able to write a main methodthat calls isRolling(). Put this main method in the UserPigPlayer class.Test and comment the class before continuing.

At this point, you will be able to testyour Die, UserPigPlayer and PigPlayer classes with PigPlayerTest (Links to an external site.) unittests. Don’t forget to set PigGame.GOAL to 100, or your code willfail this unit test.

Your code should pass PigPlayerTestbefore proceeding.

PigGame

Write the PigGame class. Itshould have two instance variables: two PigPlayers. There should be at leastthree constructors:

a default constructor that creates two UserPigPlayers (Player 1and Player 2)

a constructor that takes two Strings, and creates twoUserPigPlayers with those two Strings as the names

a constructor that takes two PigPlayers

You should write the following methods:

public void reset() – reset the two PigPlayers, when your players are ready to start a new game.

public static int playTurn(PigPlayer player, PigPlayer opponent) – You should allow “player” to roll the die (or hold) until the turn is over, by calling the isRolling method. The playTurn method returns the turn total rolled (0 if 1 was rolled, or the turn total if the player chose to stop rolling).

public void playGame() – plays an entire game of Pig, where each PigPlayer gets a turn (calling playTurn) until one player wins. Your code should always have the same PigPlayer instance variable go first.

public static void userVsUser() – this method should be similar to a main method. Print the rules and prompt the users for their names. Decide randomly (using Math.random) which player will go first. Then create a PigGame and call playGame to run the game. Here is an example of my userVsUser program running (Links to an external site.). In this example, I’ve underlined the users’ input.

your main method will be one line, calling userVsUser () method.Test each method as you write it. Then run the game and debug it. Have fun!

These classes will be used as part of the larger project.

PIG – PART 2

Add a computer player

Pig (Linksto an external site.) is a folk jeopardy dice game described by JohnScarne in 1945, and was an ancestor of the modern game Pass the Pigs® (originallycalled PigMania®).

Here are the rules: two players race toreach 100 points. Each turn, a player repeatedly rolls a die until either a 1is rolled or the player holds and scores the sum of the rolls (i.e. the turntotal). At any time during a player’s turn, the player is faced with achoice: roll or hold.

Roll – If the player rolls a

1: the player scores nothing andit becomes the opponent’s turn.

2 – 6: the number is added to theplayer’s turn total and the player’s turn continues.

Hold – The turn total is addedto the player’s score and it becomes the opponent’s turn.

Your program should already consist ofthe following classes:

Die – has a static method to roll a die

PigPlayer – an abstract class representing the player’sname, current score, and win record.

UserPigPlayer – a class that asks the user if they want toroll or hold

SimpleHoldPlayer – a computer player that uses a strategyto roll until a value is reached (the first of four computer strategies)

PigGame – plays Pig

In this part you will add:

Simulations – runs several simulations to find out whichstrategies work well

FourTurnsPlayer – the second of four computer strategies

WatchOpponentPlayer – the third of four computerstrategies

StrategicPlayer – the fourth of four computer strategies

PigGameGUI – a graphical user interface forthe PigGame. I have written this class for you, but you will need tomake sure you write your classes exactly to specifications for your codeto work with my interface.

When you have finished, you will have twoways of running your program. The text program will be run by runningthemain() method in PigGame. You will also be able to run a graphicalversion, by running the main method inPigGameGUI.

You will write three separate classes thatwill “have” each other as instance variables or localvariables: Die, PigGameand Simulations.A PigGame “has” two PigPlayer objects, anda Simulations “has a”PigGame. These three classes willnot be related to each other through inheritance. You will also write an abstract PigPlayer classthat has five child classes:

This is the last 2 weeks of your fourweek project. I would suggest using the following deadlines to keep yourself ontrack. (Completing the class includes testing and debugging! Don’t wait untilthe last week to test and debug!)

Week 1: complete the SimpleHoldPlayer andPigGame classes to allow the computer to play (against a user or against aplayer), and run your first Simulation. Make sure your code works withPigGameGUI

Week 2: complete and debug the threeremaining computer strategy classes and Simulations

If you prefer, you can write the classes inanother order, by using stub methods and classes instead.

SimpleHoldPlayer

Writethe SimpleHoldPlayer class. This class should have one instancevariable (the hold value). It should have three constructors andthe isRolling() method. The three constructors are:

a default constructor – sets the hold value to 20

a constructor that takes a String (the name of the player)

a constructor that takes a String and an int (the name and thehold value)

The isRolling() method should beautomated. It will NOT need to prompt the user or print anything to to thescreen. Instead, it will return true if the die should be rolled, by checkingif the game is not yet won and if the turn total has not yet reached the holdvalue.

Test this code before continuing to thenext step.

PigGame: Allow a User to Play Against aComputer

Now go back tothe PigGame and add two methods:

public static void userVsComputer() – allows the user toplay against the computer. This method should use Math.random to decidewhich player gets to go first.

public static void computerVsComputer() – plays thecomputer against itself. Name the two computer players “Player1” and “Player 2”.

Call each of these methods from the mainmethod in PigGame to make sure everything works correctly.

Simulations

Now you are ready for your firstsimulation! We want to answer the question:

How much of an advantage does the first player have?

We will use a MonteCarlo method (Links to an external site.) to find the answer tothis question. You should run the same computer strategy against itself,thousands of times, to see what percentage of games are won by the firstplayer. If there is no advantage, the first player would win approximately halfthe time. The more simulations you run, the more accurate your simulation willbe.

Create a Simulations class.Eventually, it will have several static methods, the first of which is:

public static void firstAdvantage(long simulations)

This method should take the number ofsimulations to be run as an argument. In the method, you should create twoSimpleHoldPlayer objects. Run simulations where these two players repeatedlyplay against each other (with the same player as the first player) by callingthe playGame method from PigGame. At the end, calculate the advantage that thefirst player has over the second (by printing out the percentage of games wonby the first player).

To debug this, you’ll want to first run theprogram with a small number of simulations (four works well). Check that thecorrect number of wins are being reported by each player.

Once you are sure the simulation is runningcorrectly, you’ll want to remove the printing in PigGame. But you don’t want tocompletely remove the printing, because sometimes you’ll still want it toprint. Instead, create a new static boolean variable in the PigGame class:verbose. Then all throughout the PigGame class, add an if-statement in front ofall System.out.println calls. (You don’t need to add verbose to userVsUser oruserVsComputer.) For example:

if (verbose) {

System.out.println(“Roll:” + roll);`

}

You should add a mutator method for verbose(a set method) to the PigGame class.

Then increase the number of simulations todetermine what advantage the player who rolls first has over the other player.You’ll want to run at least 10,000 simulations, although it doesn’t hurt to runmore.

Find the Best Hold Value

The next question we want to answer is:

What is the best hold value to use for the SimpleHoldPlayer?

You should begin by writing a method in theSimulation class:

public static double comparePlayers(long simulations, PigPlayer first,PigPlayer second)

This method should run half the simulationswith “first” PigPlayer first, and half the simulations with“second” PigPlayer first. This removes the bias favoring the playerwho rolls first.

The comparePlayers method should return thefraction of games won by the first PigPlayer. So if the “first”PigPlayer is better, it will return a number greater than 0.5, and if the“second” PigPlayer is better, it will return a number less than 0.5.

Write another static method that callscomparePlayers multiple times using different SimpleHoldPlayers. Ideally youshould use a loop to find the best hold value, but if you need to run the codemultiple times instead, you may. Record your findings in your ReadMe,explaining what code you ran (don’t delete the code when you’re done) and howyou decided on the best hold value.

A New Strategy: Win in Four Turns

The SimpleHoldPlayer has a very simplestrategy. Write a new PigPlayer child class that will try to win in fourscoring turns.

The FourTurnsPlayer should keep track ofthe number of turns in which it has held so far (not rolled a 1). At the startof the game (or as long as this player has not yet “held” a turn),the player will use a hold value that is the GOAL / 4. After one scoring turn,the player will use a hold value that is the number of points it needs to win /3, and so on. Using this strategy, this player will win on its fourth SCORINGturn (although rolling a 1 too many times may mean their opponent will winfirst).

To test this method, go back to PigGame.Modify the userVsComputer method in PigGame so the user is playing againstFourTurnsPlayer. Check that your new strategy works correctly. Don’t forget toturn verbose on again!

Once you are confident FourTurnsPlayerworks, go back to the Simulation class. Write another static methodthat compares FourTurnsPlayer to SimpleHoldPlayer (with the best hold value youfound in the previous simulation). This should be a very simple methodthat calls comparePlayers. FourTurnsPlayer should win more often thanSimpleHoldPlayer. If it doesn’t, you’ve implemented it incorrectly.

Two More Strategies for the Computer

Write two more classes (one at a time) forthe computer to play pig:

WatchOpponentPlayer – this player is very concerned about itsopponent’s score and tries to make sure that its score is never toomuch smaller than its opponent’s score. See below for more hints.

StrategicPlayer – develop your own strategy and implementit.

WatchOpponentPlayer:

This player will have two strategies basedon whether either player is close to winning.

If a player is close to winning (either this player or theopponent), this player will roll until the GOAL is reached.

If neither player is close to winning, then this player willuse a hold value that is based on how far ahead is the opponent. Use ahold value that begins at a reasonable hold value, but then add to it ifthe opponent is winning (because this player will be more willing to takerisks) and subtract from it if the opponent is losing. Hint: the amountyou should add/subtract to the original hold value should be a fraction ofthe difference between the the opponent’s score and your score.

holdValue = reasonable + (opponentScore – myScore)/number

Notice for the above strategies, there arethree important values:

in (a), how you determine what is “close to winning”

in (b)’s equation for holdValue, a reasonable initialhold value

in (b)’s equation for holdValue, the number youwant to divide the difference by

All three of these important values shouldbe instance variables in your WatchOpponentPlayer. Then write a constructor thatallows you to set all three of these instance variables.

You’ll need to run some simulations to finda good values for these three instance values. Write a static method calledfindGoodWatchValues in Simulations, and have it try values between 5-50 for allthree values. (If you are using “close to winning” as a constantvalue, then use 50-95; if you are use “close to winning” as thedifference between your score and the GOAL, then use 5-50.) You should callcomparePlayers, and test different versions of WatchOpponentPlayers against aSimpleHoldPlayer. When you find what values work best, use those for yourdefault constructor in your WatchOpponentPlayer.

[UPDATED – YOU MAY FIND ITDIFFICULT TO DETERMINE ALL THREE VALUES AS THIS REQUIRES 3 NESTED FOR LOOPS. ISUGGEST USING A “CLOSE TO WINNING” VALUE OF APPROXIMATELY 75.]

Be sure to write up what your findings werein your Project Writeup.

StrategicPlayer:

As you write the StrategicPlayer, compareyour strategy to SimpleHoldPlayer. You should tweak your strategies so they dowell against SimpleHoldPlayer. The student with the best StrategicPlayer thisyear earns an automatic A in the class (as long as they have completed theproject and write-up satisfactorily). If your StrategicPlayer does not winagainst SimpleHoldPlayer, you’ll still earn most of the credit onStrategicPlayer if you defend the reasoning behind your strategy in yourProject Writeup.

After you have finalized your strategies,you will need to include a description of your three strategies in your ProjectWriteup.

Run more simulations

We have one more questions to answer:

Which is the best strategy: SimpleHoldPlayer (using the besthold value determined in the above simulation), WatchOpponentPlayer,FourTurnsPlayer, or StrategicPlayer? Provide percentages of how theyperform against the other strategies. To calculate these percentages,you should be calling comparePlayers.

All four strategies should be good (whenplayed against each other, none of the strategies should lose more than 55% oftheir games). If one of these strategies is losing more than 55% of theirgames, first try running more simulations. If it’s still happeningconsistently, you probably have a bug with your strategy.

Run the Graphical Version of Pig Game

At any time after you have SimpleHoldPlayerworking, you can check to make sure your program works with the graphical userinterface.

Begin by downloading this zip file

.

Extract the zip files contents into the SAME folder as yourPigGame java code. When you are done, you should have (in this folder):PigGame.java, PigPlayer.java, SimpleHoldPlayer.java, Die.java,PigGameProgram.java, and my three class files (all beginning withPigGameGUI). You should also have a folder called images, with several pngfiles inside it.

Compile PigGameProgram.java. If you get the error “cannotfind symbol”, or if you compile successfully but then get this errorwhen you run the program:

Exception in thread“AWT-EventQueue-0” java.lang.NoClassDefFoundError: Die

your class names, method names, or variablenames do not follow the specifications in the assignment.

The PigGameGUI program relies on:

the roll() method from your Die class

the PigGame.GOAL constant

the isRolling method from the SimpleHoldPlayer

You can modify PigGame.GOAL to make thegame easier to test. You can also modify line 16 to use a different strategyfor the computer.

Test Your Code with Unit Tests

Here are three classes of unit tests foryou to use to check your code. They assume that PigGame.GOAL is 100.

PigPlayerTest

– tests your PigPlayer methods (getName,setName, addPoints, etc). You must have PigPlayer and UserPigPlayercompleted to run these unit tests.

TestAllPigPlayers

– tests your playTurn (from PigGame) andisRolling methods. You must have most of your classes completed,including PigGame, SimpleHoldPlayer,FourTurnsPlayer, WatchOpponentPlayer, StrategicPlayer andSimulations. You’ll can always comment out the later tests to test yourSimpleHoldPlayer and FourTurnsPlayer classes earlier. After you determinethe best hold value, modify line 8 of this unit test. You should also setverbose to false before running the unit test. (This test has beenmodified on 11/17 to reflect the new comparePlayer method.)

DieTest

– tests your Die methods

If you fail unit tests from the secondfile, remember that your isRolling method should return false if the player haswon already. For example, if the player had 90 points, and then rolls 10points, your isRolling should return false at this point (because the playerhas already won the game).

Remember if you fail a unit test, youshould move that code into a main method and replace any “assert”calls with System.out.println.FULL PROJECT