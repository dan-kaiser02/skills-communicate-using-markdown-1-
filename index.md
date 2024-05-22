# working?
![photo of me rn](https://ih1.redbubble.net/image.4701025867.8070/flat,750x,075,f-pad,750x1000,f8f8f8.u1.jpg)

``` java
package pack;
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
public class EnterWorkout {

	static String [] storeWorkout = new String[99];
	//max num of possible workouts
	static String [] dataToPrint = new String[119];
	//array to read the txt file
	static Scanner input = new Scanner(System.in);
	static int workNum = 0;
	static int minutes = 0;
	static int seconds = 0;
	//variables initialized
	
	
	
	public static void startWorkout(){
		Scanner code1;
		try {
			code1 = new Scanner(new File("workoutData.txt"));
			for(int i = 0; i < 119; i++){
				dataToPrint[i] = code1.nextLine();
			}}
		catch (FileNotFoundException e1){
			e1.printStackTrace();
		}
		//this code scans the txt file line by line and stuffs it into our array
		Scanner input = new Scanner(System.in);
		int workoutType;
			System.out.println("Welcome to 'enter workout!'");
			System.out.println("Pick your Workout type: ");
			System.out.println("1 for legs");
			System.out.println("2 for chest");
			System.out.println("3 for arms");
			System.out.println("4 for back");
			System.out.println("5 for core");
			System.out.println("6 for cardio");
			System.out.println("7 to end your workout");
			//Prints main menu
			workoutType = input.nextInt();
			if (workoutType == 7){
				
				summarizeWorkout();
				
			}
			//ends the workout
			workNum++;
			//this is to count the total number of workouts. used in SummarizeWorkout()
			switch(workoutType){
			case 1:
				Exercise(0, 12, 1);
				//legs
			case 2:
				Exercise(24, 35, 25);
				//chest
			case 3: 
				Exercise(46, 57, 47);
				//arms
			case 4: 
				Exercise(69, 76, 69);
				//back
			case 5: 
				Exercise(85, 92, 85);
				//core
			case 6: 
				cardio(101, 110, 101);
				//cardio
				
				//sends the correct pointers in the text file to our method to build exercises
			}}
	
	public static void Exercise(int startIndex, int endIndex, int offset){
		int selection = 0;
		for (int i = startIndex; i < endIndex; i++){
			System.out.println(dataToPrint[i]);
		}
		//prints exercise group menu
		System.out.println("Type the number cooresponding to the exercise "
				+ "you would like to input!");
		boolean inputValid = false;
		while (inputValid == false){
		selection = input.nextInt();
		if (selection == 0){
			startWorkout();
		}else if (selection > (endIndex - startIndex)){
			System.out.println("Number invalid! input a valid number");
			continue;
		}else{
			inputValid = true;;
			}}
		//makes sure the selected exercise # is valid
		System.out.println(dataToPrint[selection + endIndex]);
		System.out.println("How many sets?");
		int setNum = input.nextInt();
		System.out.println("How many reps per set?");
		int repNum = input.nextInt();
		System.out.println("How much weight per rep?");
		int weightNum = input.nextInt();
		//user inputs exercise details
		storeWorkout[workNum - 1] = dataToPrint[selection + offset].substring(3) + 
				" for " + setNum + " sets, " + repNum +
				" reps per set, at " + weightNum + "lbs per rep";
		//sets a String variable that we use to print a workout summary here and in SummarizeWorkout()
		System.out.println("You did " + storeWorkout[workNum - 1] + "! Great job! Workout stored");
		//prints summary of workout
		Exercise(startIndex, endIndex, offset);
	}
	public static void cardio(int startIndex, int endIndex, int offset){
		//cardio works different so it gets its own method
		int selection = 0;
		for (int i = startIndex; i < endIndex; i++){
			System.out.println(dataToPrint[i]);
		}
		//prints cardio menu
		System.out.println("Type the number cooresponding to the exercise "
				+ "you would like to input!");
		boolean inputValid = false;
		while (inputValid == false){
		selection = input.nextInt();
		if (selection == 0){
			startWorkout();
		}else if (selection > (endIndex - startIndex)){
			System.out.println("Number invalid! input a valid number");
			continue;
		}else{
			inputValid = true;;
			}}
		//makes sure the selected exercise # is valid
		System.out.println(dataToPrint[selection + 110]);
		System.out.println("How much time? Enter Minutes, hit Enter, then input seconds, then hit enter!");
		minutes = input.nextInt();
		seconds = input.nextInt();
		//gets time input from user
		if (seconds < 10){
		storeWorkout[workNum - 1] = dataToPrint[selection + offset].substring(3) + 
				" for " + minutes + ":0" + seconds;
		}else{
			storeWorkout[workNum - 1] = dataToPrint[selection + offset].substring(3) + 
					" for " + minutes + ":" + seconds;}
		System.out.println("You did " + storeWorkout[workNum - 1] + "! Great job! Workout stored");
		//puts in "xx:yy" format
		cardio(startIndex, endIndex, offset);
	}
	
	public static void summarizeWorkout(){
		System.out.println("Workout summary");
		for (int i = 0; i < workNum; i++){
			if (storeWorkout[i] != null){
			System.out.println(storeWorkout[i]);
			}}
		System.exit(0);
	}}
```


- [x] fortnite
- [x] sleep
- [x] fortnite
- [ ] sleep
- [ ] fortnite
- [ ] sleep
