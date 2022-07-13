# Learn-Bash-building-5-programs
Learn-Bash-building-5-programs

Learn Bash Scripting by Building Five Programs
Review
The first thing you need to do is start the terminal. Do that by clicking the "hamburger" menu at the top left of the screen, going to the "terminal" section, and clicking "new terminal". Once you open a new one, type echo hello bash into the terminal and press enter.

1. Capitalization matters

2. If the tests don't run automatically, "trash" all the terminals and try the instructions again

You can run commands in the terminal or put them in a file to be run as a script. You will be making five small programs to learn some scripting. The first one will be a "questionnaire". Use the touch command to create questionnaire.sh in the project folder.

1. Type touch questionnaire.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

To start, open the file in the main editor by clicking the filename in the left side panel.
Then, add the text echo hello questionnaire at the top of the file.

1. If the left side panel isn't visible, click the icon that looks like two pieces of paper
at the top left to open the panel. Then, click on your file to open it

2. Add the suggested text to the questionnaire.sh file

Your script has one command. Run it with sh questionnaire.sh to see what happens. sh stands for shell.

1. Type sh questionnaire.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

Using sh to run your script uses the shell interpreter. Run your script again with bash questionnaire.sh to use the bash interpreter. bash stands for bourne-again shell.

1. Type bash questionnaire.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

The output was the same. There are many interpreters which may not give the output you expect. Find out where the bash interpreter is located by entering which bash in the terminal.

1. Type which bash in the terminal and press enter

That's the absolute path to the bash interpreter. You can tell your program to use it by placing a shebang at the very top of the file like this: #!<path_to_interpreter>. Add a shebang at the very top of your file, the one you want looks like this: #!/bin/bash.

1. Add #!/bin/bash at the top of your questionnaire.sh file

Now, instead of using sh or bash to run your script. You can run it by executing the file and it will default to bash. Run your script by executing it with ./questionnaire.sh

1. Type ./questionnaire.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

You should have got a permission denied message because you don't have permissions to execute the script. List what's in the project folder in long list format with ls -l to see the file permissions.

1. Type ls -l in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

Next to your file is -rw-r--r--. All but the first character (-) describe permissions different users have with the file. r means read, w means write, x means execute. I don't see an x anywhere, so nobody can execute it. Enter chmod +x questionnaire.sh in the terminal to give everyone executable permissions.

1. Type chmod +x questionnaire.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

List what's in the folder again with ls -l to see the new permissions.

1. Type ls -l in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

The x was added by each type of user to denote that anyone can execute the file. Run your file again by executing it with ./questionnaire.sh.

1. Type ./questionnaire.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

Now it works. In your script, you can add any commands that you would be able to enter in the terminal. Test this by adding the ls -l command below your other command.

1. Add ls -l at the bottom of your questionnaire.sh file

Run the script by executing it again.

1. Type ./questionnaire.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

Your script printed the result of the two commands as if you entered them in the terminal. Delete everything but the shebang from your file so you can start making the questionnaire.

1. Only #!/bin/bash should remain in your questionnaire.sh file

Bash has variables, functions, and other things you might be familiar with. You can create a variable with VARIABLE_NAME=VALUE. There cannot be any spaces around the equal (=) sign. If a variable has any spaces in it, place double quotes around it. Create a variable named QUESTION1 and set it's value to "What's your name?".

1. Add QUESTION1="What's your name?" at the bottom of your questionnaire.sh file

To use a variable, place $ in front of it like this: $VARIABLE_NAME. Shell scripts run from top to bottom, so you can only use variable below where it's created. Use echo to print your variable.

1. Add echo $QUESTION1 at the bottom of your questionnaire.sh file

Run the file like you did before to see if it worked.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

4. Enter cd ~/project in the terminal to get to the project folder if you aren't there

The question was printed. Next, you want to be able to accept input from a user. You can do that with read like this: read VARIABLE_NAME. This will get user input and store it into a new variable. After you print the question, use read to get input and store it in a variable named NAME.

1. Add read NAME at the bottom of your questionnaire.sh file

At the bottom of your script, use echo to print Hello <name>. to the terminal.

1. You can use your NAME variable like this: $NAME

2. Use your $NAME variable in place of <name>

3. Don't forget the period

4. Add echo Hello $NAME. at the bottom of your script

Run the file again. Type your name and press enter after it asks for it.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

4. Enter cd ~/project in the terminal to get to the project folder if you aren't there

5. You can press ctrl+c to close the program

Right below your first variable, create another one named QUESTION2. Set the value to, Where are you from?. Make sure to put it in double quotes.

1. Here's an example: VARIABLE="value"

2. Add QUESTION2="Where are you from?" to your script

After your read command, use your new variable to print the next question.

1. Use echo to print the variable

2. Add echo $QUESTION2 below your read command

Below where the second question is printed, use read to get input from the user into a variable named LOCATION.

1. Here's an example read VARIABLE_NAME

2. Add read LOCATION to your script below echo $QUESTION2

Change the existing response to Hello <name> from <location>..

1. Use your two variables in place of <name> and <location

2. Use your two variables with $NAME and $LOCATION

3. Make sure the command is at the bottom of the file

4. The suggested command should look like: echo Hello $NAME from $LOCATION.

Run the script and enter values when it is waiting for input.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

4. You can press ctrl+c to close a program

It's looking good. I want a title to appear when the program first starts. Use echo to print ~~ Questionnaire ~~ before anything else is printed.

1. Add echo ~~ Questionnaire ~~ below your shebang

Run the script and enter values until it is done again so you can see what the title looks like.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

4. You can press ctrl+c to close the program

It would be nice if there was some empty lines around the title. You've probably used the --help flag before, see if you can use it with echo to try and find a way to add empty lines.

1. Enter the suggested command in the terminal

2. Here's an example: <command> <flag>

3. The command is echo, the flag is --help

4. Type echo --help in the terminal and press enter

That didn't work as I hoped. Another way to find information about a command is with man. It stands for manual and you can use it like this: man <command>. See if there's a manual for echo.

1. Type man echo in the terminal and press enter

2. Press enter until you have seen the whole menu

At the top of the menu, the -e option looks promising. And the \n below it says new line. You should take a look at those. In your script, change the title to echo -e \n~~ Questionnaire ~~\n to see if that prints the empty lines.

1. Change the suggested line to echo -e \n~~ Questionnaire ~~\n

Run it to see if it worked. You can press ctrl+c to close the program after it starts if you don't want to enter values.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

4. You can press ctrl+c to close the program

It didn't print the empty lines. echo will only print empty lines if the value is enclosed in quotes. Place double quotes around the title that gets printed to see if it works.

1. Change the suggested line to echo -e "\n~~ Questionnaire ~~\n"

Run your script again to see if that fixed it.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

4. You can press ctrl+c to close the program

Now it's working 😄 Create a QUESTION3 variable next to the other two, set it's value to "What's your favorite coding website?"

1. Add QUESTION3="What's your favorite coding website?" to your questionnaire.sh file

2. Add it by the other two variables

Use echo to print the third question after you read the LOCATION.

1. Add echo $QUESTION3 below the read LOCATION

2. Add it to your questionnaire.sh file

After the question you just printed, add code to read input into a variable named WEBSITE.

1. Add read WEBSITE below the echo $QUESTION3

Change the echo command of the response to print this sentence instead: Hello <name> from <location>. I learned that your favorite coding website is <website>!.

1. Replace the echo Hello $NAME from $LOCATION. with the suggested sentence

2. Use your three variables in place of <name>, <location>, and <website>

3. The command should look like this: echo Hello $NAME from $LOCATION. I learned that your favorite coding website is $WEBSITE!

Run the script and enter values when the program is waiting. Let's see the final output.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

One last thing. Change that final response to print an empty line at the beginning of the sentence.

1. Use echo with the -e flag and a new line (\n) character like you did for the title

2. Don't forget to put the response in double quotes so it prints the empty line

3. Here's an example: echo -e "\n<message>"

4. Only add a new line at the beginning of the response, not the end

5. The final command should look like this: echo "\nHello $NAME from $LOCATION. I learned that your favorite coding website is $WEBSITE!"

Run it one last time and enter values when it asks to see if you like how it looks.

1. Run your file by executing it

2. Type ./questionnaire.sh in the terminal and press enter

3. Make sure you are in the project folder first

It looks good. I think you are done with that script for now. The next program will be countdown timer. Use the touch command to create a new file named countdown.sh in your project folder.

1. Type touch countdown.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

Give your file executable permissions so you can run it like the other one. It's the chmod command with the +x flag.

1. Here's an example chmod <permissions> <filename>

2. The value for permissions you want to use is +x

3. You previously used chmod +x questionnaire.sh

4. Type chmod +x countdown.sh in the terminal and press enter

5. Make sure you are in the project folder first

You want to use the bash interpreter again. Add a shebang at the top of your new file to denote that.

1. A shebang looks like this: #!<path_to_interpreter>

2. Enter which bash in the terminal to see the path to bash

3. Look at the shebang in your first script to get the syntax

4. It should look like this: #!/bin/bash

5. Add #!/bin/bash at the top of your countdown.sh file

Comments in bash look like this: # <comment>. Add a comment below the shebang that says Program that counts down to zero from a given argument so people know what it does. Note that the shebang is a special case and is not treated like a comment.

1. Add # Program that counts down to zero from a given argument to your countdown.sh file

Programs can take arguments. You can access them a few different ways with $. Add echo $* in your script to print all arguments passed to it.

1. Add echo $* at the bottom of the countdown.sh file

Execute your script with ./countdown.sh.

1. Type ./countdown.sh in the terminal and press enter

2. Make sure you are in the project folder first

Nothing was printed. Run your script again, but this time add three arguments to the command; arg1, arg2, and arg3. Place them after the command with a space before each one.

1. Type ./countdown.sh arg1 arg2 arg3 in the terminal and press enter

2. Make sure you are in the project folder first

$* printed all the arguments passed to your script. To access any one of them, use $<number>. arg2 could have been accessed with $2. Change your script to echo the first argument instead of all the arguments.

1. Try running your script with an argument to make sure it’s giving the expected output

2. Use echo $1 to print the second argument

3. Change echo $* to echo $1 in your countdown.sh file

Run your file with ./countdown.sh arg1 arg2 arg3 again.

1. Type ./countdown.sh arg1 arg2 arg3 in the terminal and press enter

2. Make sure you are in the project folder first

Now it just prints the first argument. Your program will accept an argument to count down from. You will test it with an if statement to make sure it's a positive integer. I wonder what that syntax would look like. Type help in the terminal to see if you can find anything.

1. Type help in the terminal and press enter

This is a list of built-in commands. You should look over it, some of them may look familiar. I see echo in there. Another one is if. See if you can find out more about it by checking its man page.

1. Here's an example: man <command>

2. Type man if in the terminal and press enter

I guess there isn't a man page for it. At the top of the help screen, I noticed you can use help <command> to find out more. Yet another way to find out about a command 😥 See if you can find out more about if with that method.

1. Here's an example help <command>

2. Type help if in the terminal and press enter

The syntax is at the top, not all of it is required. Here's another example:

if [[ CONDITION ]]
then
  STATEMENTS
fi
Remove the echo $1 in your script and add an if condition that checks if [[ $1 == arg1 ]]. In its then area, use echo to print true to the screen. There must be spaces on the inside of the brackets ([[ ... ]]) and around the operator (==).

1. Make sure to remove the echo $1

2. Add the following to your countdown.sh file:

if [[ $1 == arg1 ]]
then
  echo true
fi
Notice that the end of the syntax is fi (if backwards). It should print true if you pass arg1 to your script now. Run the script with arg1 as the only argument.

1. Type ./countdown.sh arg1 in the terminal and press enter

2. Make sure you are in the project folder first

The if condition worked, it printed true. Run it again with anything except arg1 as the first argument.

1. Type ./countdown.sh arg2 in the terminal and press enter

2. Make sure you are in the project folder first

Nothing was printed. One of the optional parts of if was an else area. You can use it like this:

if [[ CONDITION ]]
then
  STATEMENTS
else
  STATEMENTS
fi
Add an else to your existing if condition. Use echo to print false if the condition fails.

1. Your if should look like this:

if [[ $1 == arg1 ]]
then
  echo true
else
  echo false
fi
Run the script again and use anything except arg1 as the only argument.

1. Type ./countdown.sh !arg1 in the terminal and press enter

2. Make sure you are in the project folder first

3. Enter cd ~/project in the terminal to get to the project folder if you aren't there

Now it printed false. Your program is expecting an integer to count down from as its argument. You can compare integers inside the brackets ([[ ... ]]) of your if with -eq (equal), -ne (not equal), -lt (less than), -le (less than or equal), -gt (greater than), -ge (greater than or equal). Change your if condition to check if your first argument is less than 5.

1. Make sure there's spaces inside the brackets ([[ ... ]]) and around the operator (-lt)

2. Your if condition should look like this: [[ $1 -lt 5 ]]

3. The whole if should look like this:

if [[ $1 -lt 5 ]]
then
  echo true
else
  echo false
fi
Run the script again and use 4 as a first argument to make sure it's working.

1. Type ./countdown.sh 4 in the terminal and press enter

2. Make sure you are in the project folder first

It printed true since your argument was less than 5. Run it again with 5 as the argument.

1. Type ./countdown.sh 5 in the terminal and press enter

2. Make sure you are in the project folder first

As expected, that printed false. Take a look at that help menu again. I want to see if we can find out more about how these expressions work.

1. Type help in the terminal and press enter

Near the top left, it says [[ expression ]]. Those look like the double brackets you are using. See if you can get more info about that with the help command like you did with help if.

1. Here's an example: help <command>

2. Type help [[ expression ]] or help [[ in the terminal and press enter

It might not be a bad idea to read that. Looks like you can use some, probably familiar, things like !, &&, and || to compare multiple expressions. There's also == and != operators for an individual expression. It says something about the test built-in command. See if you can bring up the help menu for that.

1. View the help menu of the suggested command like you did for the help if

2. Here's an example: help <command>

3. Type help test in the terminal and press enter

That's what I was looking for. At the top are some file operators. There's some string and other operators as well. You should take a look at them. Near the bottom, are the arithmetic operators you used with your if condition. Change the condition in your script to check if the first argument is less than or equal to 5.

1. The if condition should look like this: [[ $1 -le 5 ]]

2. Make sure there's spaces inside the brackets ([[ ... ]]) and around the operator (-le)

3. It's the if in your countdown.sh file

Run the script and use 5 as a first argument again.

1. Type ./countdown.sh 5 in the terminal and press enter

2. Make sure you are in the project folder first

Now it prints true. Remember I said any command can run in the terminal or a script. Try running an expression right in the terminal by entering [[ 4 -le 5 ]] in it.

1. Enter the suggested expression in the terminal

2. Make sure there's spaces inside the brackets ([[ ... ]]) and around the operator (-le)

3. Type [[ 4 -le 5 ]] in the terminal and press enter

Nothing happened? Each command has an exit status that can be accessed with $?. View the exit status of the last command with echo $?.

1. Type echo $? in the terminal and press enter

2. Your second to last command should be [[ 4 -le 5 ]]. So enter that before echo $?

The exit status of 0 means it was true, 4 is indeed less or equal to 5. Try it again with [[ 4 -ge 5 ]].

1. Enter the suggested expression in the terminal

2. Make sure there's spaces inside the brackets ([[ ... ]]) and around the operator (-ge)

3. Type [[ 4 -ge 5 ]] in the terminal and press enter

Use echo to view the exit status of the command you just entered.

1. Type echo $? in the terminal and press enter

2. Your second to last command should be [[ 4 -ge 5 ]]. So enter that right before echo $?

It printed 1 this time for false. You can separate commands on a single line with ;. Enter your last two commands on one line like this: [[ 4 -ge 5 ]]; echo $?. It will run the expression, then print the exit status of it since it was the last command.

1. Make sure there's spaces inside the brackets ([[ ... ]]) and around the operator (-ge)

2. Type [[ 4 -ge 5 ]]; echo $? in the terminal and press enter

It's still false. Using the same syntax of [[ ... ]]; echo$?, check if 10 is not equal to 5 and print the exit status of the expression on one line.

1. Check the help test menu to find the not equal operator

2. It's the -ne operator

3. You previously used [[ 4 -ge 5 ]]; echo $?

4. Make sure there's spaces inside the brackets and around the operator

5. Type [[ 10 -ne 5 ]]; echo $? in the terminal and press enter

You can think of an exit status of 0 as true. But it means that the command had zero errors. All commands have an exit status. Using the same syntax, enter bad_command; and check its exit status on a single line.

1. The syntax looks like this: <command>; echo $?

2. You previously used [[ 10 -ne 5 ]]; echo $?

3. Type bad_command; echo $? in the terminal and press enter

command not found, with an exit status of 127. Anything but 0 means there was an error with the command. bad_command didn't exist. Try it again with ls.

1. Use the same syntax you have been using

2. Here's an example <command>; echo $?

3. You previously used bad_command; echo $?

4. Type ls; echo $? in the terminal and press enter

The command executed as expected and there were zero errors. So it gave you an exit status of 0. Try it again with ls -y.

1. Use the same syntax you have been using

2. Here's an example: <command>; echo $?

3. You previously used ls; echo $?

4. Type ls -y; echo $? in the terminal and press enter

The -y flag doesn't work with ls so it gave you an exit status other than 0, meaning that the command was unsuccessful. View the help menu of the test command again, I want to see what else is in that list.

1. Here's an example: help <command>

2. Type help test in the terminal and press enter

You tried a few of the arithmetic operators, those work for integers. Try one of the file operators. The first one on the list checks if a file exists. Type [[ -a countdown.sh ]]; echo $? in the terminal to see if your file exists.

1. Enter the suggested commands in the terminal

2. Type [[ -a countdown.sh ]]; echo $? in the terminal and press enter

3. Don't forget the spaces inside the brackets

4. Make sure you are in the project folder first

The file must exist. It's checking the folder the command is entered from. Try it again with bad_file.txt.

1. Use the same syntax you have been using

2. Here's an example: <command>; echo $?

3. You previously used [[ -a countdown.sh ]]; echo $?

4. Type [[ -a bad_file.txt ]]; echo $? in the terminal and press enter

bad_file.txt doesn't exist. I think you're getting the hang of this. Using the same syntax, check if you have permissions to execute your countdown.sh file. You may want to look at that menu again.

1. View the help test menu to find the file operator for checking if a file is executable by you

2. It's the -x operator

3. The syntax you want is [[ ... ]]; echo $? to see if the condition is true

4. Don't forget the spaces inside the brackets

5. Type [[ -x countdown.sh ]]; echo $? in the terminal and press enter

6. Make sure you are in the project folder first

You played around with a number of the expressions. View the help [[ expression ]] menu again that you looked at before to see a few more options. You can view the menu with just help [[.

1. Enter the suggested command in the terminal

2. Type help [[ expression ]] or help [[ in the terminal and press enter

As I mentioned before, you can test multiple expressions with && and ||. Enter [[ -x countdown.sh && 5 -le 4 ]]; echo $? in the terminal to test the file is executable by you and five is less than or equal to four.

1. Enter the suggested command in the terminal

2. Type [[ -x countdown.sh && 5 -le 4 ]]; echo $? in the terminal and press enter

3. Make sure there's spaces around the brackets and all the operators

Both conditions weren't true, so the exit status was 1 for false. Try testing the same two conditions with the or operator.

1. Modify this [[ -x countdown.sh && 5 -le 4 ]]; echo $? with the suggestion and enter it in the terminal

2. Use the or operator from the help [[ expression ]] menu

3. The or operator is ||

4. Type [[ -x countdown.sh || 5 -le 4 ]]; echo $? in the terminal and press enter

5. Make sure there's spaces around the brackets and all the operators

One of the conditions was true so it printed 0. I think that's enough of a detour. Back in your script, change the if condition to check if the first argument is greater than zero so you can be sure it's something you can count down from.

The condition you added checks if a positive integer was passed as an argument to the script and executes the then area. Change the existing echo command to print Include a positive integer as the first argument. if a positive integer is not used.

1. The else area should look like this: echo Include a positive integer as the first argument.

2. The whole if condition should look like this:

if [[ $1 -gt 0 ]]
then
  echo true
else
  echo Include a positive integer as the first argument.
fi
Run your script and use 1 as a first argument to make sure the condition is working.

1. Type ./countdown.sh 1 in the terminal and press enter

2. Make sure you are in the project folder first

Run it again and use anything but a positive integer as the only argument.

1. Type ./countdown.sh 0 in the terminal and press enter

2. Make sure you are in the project folder first

Looks like your if condition is working. Next, you want to loop over the argument and count down to zero from it. Check the help menu to see if there's any commands for this.

1. Enter the suggested command in the terminal

2. Type help in the terminal and press enter

There's two for loops in there, you want the second one. Here's an example:

for (( i = 10; i > 0; i-- ))
do
  echo $i
done
The above creates a variable (i = 10), then prints it, subtracts one, and repeats until i is not greater than 0. So it prints 10 through 1. In the then area of your condition, replace the echo with a for loop that prints from the argument ($1) to 1.

1. Set the variable to the value of your argument ($1) initially

2. Use the same syntax as the example except change the 10 to $1

3. Don't include any extra commands in the then area

4. Your then area should look like this:

for (( i = $1; i > 0; i-- ))
do
  echo $i
done
5. The whole if condition should look like this:

if [[ $1 -gt 0 ]]
then
  for (( i = $1; i > 0; i-- ))
  do
    echo $i
  done
else
  echo Include a positive integer as the first argument.
fi
Run your script and use 10 as the first argument.

1. Type ./countdown.sh 10 in the terminal and press enter

2. Make sure you are in the project folder first

It works 😄 But I want it to pause for one second between each number. Check the help menu again to see if there's any commands that might help.

1. Enter the suggested command in the terminal

2. Type help in the terminal and press enter

I'm not seeing the command I was hoping to. These are the built-in commands, where are the rest? Type ls / to look around.

1. Enter the suggested command in the terminal

2. Type ls / in the terminal and press enter

The / listed what's in the root of the file system. I see a bin folder, bin stands for binary. View what's in it with ls /bin.

1. Enter the suggested command in the terminal

2. Type ls /bin in the terminal and press enter

These are some non built-in commands. There's quite a few that should look familiar. One is bash, that's the one you used for the shebang in your scripts. I see one called sleep. View the manual of it.

1. View a manual with the man command

2. Here's an example: man <command>

3. Enter man sleep in the terminal

4. Press enter until you have seen the whole menu

At the top, it says you can pause execution for a number of seconds. Try it out by entering sleep 3 in the terminal.

1. Enter the suggested command in the terminal

2. Enter sleep 3 in the terminal

That should work. In your for loop, use sleep to make the script pause for 1 second after each number is printed.

1. Add the suggestion to the for loop in your countdown.sh file

2. Add sleep 1 after you print i in your for loop

Run your script and use 3 as the first argument.

1. Type ./countdown.sh 3 in the terminal and press enter

2. Make sure you are in the project folder first

Awesome. Except it should print 0 instead of stopping at 1. Change the condition in your for loop so that it checks for i >= 0.

1. Your for loop should look like this:

for (( i = $1; i >= 0; i-- ))
do
  echo $i
  sleep 1
done
2. The whole if condition should look like this:

if [[ $1 -gt 0 ]]
then
  for (( i = $1; i >= 0; i-- ))
  do
    echo $i
    sleep 1
  done
else
  echo Include a positive integer as the first argument.
fi
Run your script with 3 as the argument again.

1. Type ./countdown.sh 3 in the terminal and press enter

2. Make sure you are in the project folder first

Excellent. I want it to display a title like the other script. Make it so that it prints ~~ Countdown Timer ~~ before anything else. Include a new line before and after it like you did for the other title.

1. Use the echo command with the -e flag and the new line (\n) character

2. Make sure to place the message in double quotes

3. Here's an example: echo -e "\n<message>\n"

4. Add echo -e "\n~~ Countdown Timer ~~\n" to the countdown.sh file after the comment

Run your script and use 1 as the first argument again to see the title.

1. Type ./countdown.sh 1 in the terminal and press enter

2. Make sure you are in the project folder first

This is fun. You can create a multiline comment like this:

: '
  comment here
  more comment here
'
Comment out your for loop with a multiline comment. I want to try and do this with a while loop.

1. Comment out the for loop in your countdown.sh file with a multiline comment

2. Make sure there's a space between the : and '

3. Your for loop should look like this:

: '
for (( i = $1; i >= 0; i-- ))
do
  echo $i
  sleep 1
done
'
View the help menu for the while command to see if you can find anything.

1. Here's an example: help <command>

2. Enter help while in the terminal

It shows the syntax. First, below your comment, create a variable named I that is set to the value of your first argument. It will start there, then on each iteration of the while loop you can subtract 1 from it until it reaches 0.

1. Add I=$1 in the then area of your if statements below the multi-line comment

2. The then area should look like this:

: '
for (( i = $1; i >= 0; i-- ))
do
  echo $i
  sleep 1
done
'
I=$1
The menu showed that you can make a while loop like this:

while [[ CONDITION ]]
do
  STATEMENTS
done
Add a while loop below the I variable you made. The condition should be $I -ge 0 and you should echo the I variable in the do statements.

1. Your while loop should look like this:

while [[ $I -ge 0 ]]
do
  echo $I
done
I never changes here, so you would have an infinite loop. You can subtract one from I with double parenthesis (((...))) and the -- operator. In your while loop, add (( I-- )) after you echo $I to subtract one from I on each pass.

1. Your while loop should look like this:

while [[ $I -ge 0 ]]
do
  echo $I
  (( I-- ))
done
The last thing to do is to add the sleep again. In your while loop, add the code to make it sleep for 1 second. Add the code after the (( I-- )).

1. Use the same sleep 1 you used in the for loop

2. Your while loop should look like this:

while [[ $I -ge 0 ]]
do
  echo $I
  (( I-- ))
  sleep 1
done
Run the script and use 5 as the first argument.

1. Type ./countdown.sh 5 in the terminal and press enter

2. Make sure you are in the project folder first

I think the countdown timer is finished. Feel free to try it with some other arguments. The next one is a bingo number generator. Use touch to create bingo.sh in the same folder as the others.

1. Type touch bingo.sh in the terminal and press enter

2. Make sure you are in the project folder first

Give your file executable permissions like you did for the other two.

1. Use the chmod command with the +x flag

2. Here's an example chmod <permissions> <filename>

3. You previously used chmod +x countdown.sh

4. Type chmod +x bingo.sh in the terminal and press enter

Add a shebang at the top of your new script. It should use bash again like other two.

1. A shebang looks like this: #!<path_to_interpreter>

2. Enter which bash in the terminal to see the path to bash

3. Look at the shebang in one of your other scripts to get the syntax

4. It should look like this: #!/bin/bash

5. Add #!/bin/bash at the top of your bingo.sh file

Add a comment below the shebang that says, Bingo Number Generator.

1. Comments look like this: # <comment>

2. Add #Bingo Number Generator below the shebang

3. Capitalization matters

Before I forget, use a single echo command to print a title for this program. It should say ~~ Bingo Number Generator ~~ with an empty line before and after it.

1. Use the echo command with the -e flag and the new line (\n) character

2. Don't forget the double quotes when using a new line character

3. Take a look at one of the title's from a previous file for a hint

4. Here's an example: echo -e "\n<message>\n"

5. You previously used echo -e "\n~~ Countdown Timer ~~\n"

6. Add echo -e "\n~~ Bingo Number Generator ~~\n" below the comment of your bingo.sh file

In your script, create a NUMBER variable that equals 5.

1. Here's an example: VARIABLE_NAME=VALUE

2. Add NUMBER=5 to the bottom of your bingo.sh file

Below your new variable, use echo to print it to the screen.

1. Here's an example: echo $<variable>

2. Use NUMBER in place of <variable>

3. Add echo $NUMBER at the bottom of your bingo.sh file

Run the script by executing it.

1. Type ./bingo.sh in the terminal and press enter

2. Make sure you are in the project folder first

The numbers in bingo go up to 75, each number has a letter from the word bingo associated with it. You will need to randomly generate a number between 1 and 75. Bash may have something that can help you here. A shell comes with environment variables. View them by entering printenv in the terminal.

1. Type printenv in the terminal and press enter

These are all environment variables, they are predefined and loaded with each shell. Most of them aren’t very relevant, but it’s nice to know they’re there. One of them is LANG. Use echo to print it in the terminal.

1. Here's an example: echo $<variable>

2. Type echo $LANG in the terminal and press enter

View all variables in the shell with declare -p. -p stands for print

1. Type declare -p in the terminal and press enter

This list includes all the environment variables, and any others that may have been created in the current shell. There's one named RANDOM. Use echo to print it in the terminal.

1. Here's an example: echo $<variable>

2. Type echo $RANDOM in the terminal and press enter

Back in your script, use the RANDOM variable to set NUMBER to a random number instead of 5.

1. Change NUMBER=5 to NUMBER=$RANDOM

Run the script a few times in a row to make sure it's working.

1. Type ./bingo.sh in the terminal and press enter two times in a row

2. Make sure you are in the project folder first

The RANDOM variable will generate a random number between 0 and 32767. You can use the modulus operator to make it in the range you want. In your script, change the NUMBER variable to $RANDOM%75.

1. Change NUMBER=$RANDOM to NUMBER=$RANDOM%75

Run the script again.

1. Type ./bingo.sh in the terminal and press enter

2. Make sure you are in the project folder first

Bash sees everything as a string so it just printed the %75 part literally. In the terminal, create an I variable equal to 0 (zero), so you can play with it and figure out how to do some calculations.

1. Type I=0 in the terminal and press enter

In the terminal, use echo to print your new variable.

1. Here's an example: echo $<variable>

2. Type echo $I in the terminal and press enter

I noticed that you used double parenthesis in the while loop of your countdown timer to subtract one from I. Type (( I++ )) in the terminal to see if anything happens.

1. Type (( I++ )) in the terminal and press enter

There was no output. Use echo to print I in the terminal again.

1. Type echo $I in the terminal and press enter

The double parenthesis performed the calculation, changing the value of I from 0 to 1. Enter help let in the terminal to see the operators you can use with the double parenthesis.

1. Type help let in the terminal and press enter

You used several of these now, including in the for loop from the countdown timer. Enter (( I += 10 )) in the terminal to increment I by 10. Note that you don't need to prepend variables with $ inside these parenthesis.

1. Type (( I += 10 )) in the terminal and press enter

Use echo to print your I variable again.

1. Type echo $I in the terminal and press enter.

It should have printed 11 for the value of I. Using the double parenthesis like you have been is good for changing variable values or making comparisons. It makes the calculation in place and provides no output. If you want to make a calculation and do something with the result, add a $ in front like this: $(( ... )). Type $(( I + 4 )) in the terminal to see what happens.

1. If it didn't print 11 for I, enter I=11 to set it to 11

2. Type $(( I + 4 )) in the terminal and press enter

It should say, bash: 15: command not found. It replaced the command with the result of the calculation. Effectively, trying to run 15 as a command. Enter the same command, but put echo in front of it. The command was $(( I + 4 ))

1. Type echo $(( I + 4 )) in the terminal and press enter

Again, it replaced the calculation with the result. So it was basically the same as if you entered echo 15. Use echo to print I to the screen again.

1. Type echo $I in the terminal and press enter

It should still have printed 11 for I. See the hints if it didn't. These double parenthesis with a $ are how you can assign a variable to some calculation. In the terminal, create a J variable, and use the $(( ... )) syntax to set its value to I - 6.

1. If it didn't print 11 for I, enter I=11 to set it to 11

2. Type J=$(( I - 6 )) in the terminal and press enter

Use echo to print J.

1. Here's an example: echo $<variable>

2. Type echo $J in the terminal and press enter

J should equal 5. For some more practice, use echo to print the value J * 5 + 25.

1. Type echo $(( J * 5 + 25 )) in the terminal and press enter

It should have printed 50. Print J with echo again.

1. Here's an example: echo $<variable>

2. Type echo $J in the terminal and press enter

So, as a reminder, (( ... )) will perform a calculation or operation and output nothing. $(( ... )) will replace the calculation with the result of it. You made a few variables in this shell, view them with declare -p.

1. Type declare -p in the terminal and press enter

declare can be used to create variables, but you are just going to use it to view them for now. If you scroll up a little, you should find your I and J variables in there. View J with declare -p J.

1. Type declare -p J in the terminal and press enter

I saw RANDOM in that list, too. View it with declare -p <variable> like you did for J.

1. Type declare -p RANDOM in the terminal and press enter

Okay, I think I finally know how to get the random number for the Bingo Number Generator. Use echo and RANDOM % 75 to print a random number in the terminal.

1. Use the $(( ... )) syntax to calculate the random number

2. Here's an example: echo $(( <calculation> ))

3. Type echo $(( RANDOM % 75 )) in the terminal and press enter

One tiny problem, that calculation will give a number between 0 and 74. Enter the same command in the terminal, but add 1 to the calculation to get a random number between 1 and 75.

1. Type echo $(( RANDOM % 75 + 1 )) in the terminal and press enter

Back in your bingo.sh script, change the NUMBER variable so that it starts as a random number between 1 and 75 using the syntax you have been practicing.

1. Change the NUMBER variable to the result of the calculation RANDOM % 75 + 1

2. Use the $(( ... )) syntax to make the calculation

3. It should look like this: NUMBER=$(( RANDOM % 75 + 1 ))

Run your script a few times in a row to make sure it's working.

1. Type ./bingo.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Run it at least two times in a row

Next, create a TEXT variable and set the value to "The next number is, ". When the script is finished, the output will be something like The next number is B:15.

1. Make sure there's a space after the comma

2. Add TEXT="The next number is, " to the bingo.sh file

The letter that goes with the random number depends on what the number is. If it's 15 or less, it will be a B. I saw some comparisons in the help let menu, take a look at it again.

1. Type help let in the terminal and press enter

You used the double square brackets with your if statement in the last program, but you can use the double parenthesis with these operators as well. In your script, create an if statement that uses double parenthesis for the condition. Check if the number variable is less than or equal to 15. If it is, use your two variables to print The next number is, B:<number>.

1. Make sure you only have two echo statements in your script, the title being one of them

2. Here's an example of how your if statement should look:

if (( CONDITION ))
then
  STATEMENTS
fi
3. The condition you want is (( NUMBER <= 15 ))

4. In the statements area, use echo and your two variables to print The next number is, B:<number>

5. The statements area should look like this: echo $TEXT B:$NUMBER

6. The whole if statement should look like this:

if (( NUMBER <= 15 ))
then
  echo $TEXT B:$NUMBER
fi
if statements can have an "else if" area like this:

if (( CONDITION ))
then
  STATEMENTS
elif [[ CONDITION ]]
then
  STATEMENTS
fi
Using the double square brackets this time, add an elif condition that checks if the number variable is less than or equal to 30. If it is, use your two variables again to print The next number is, I:<number>

1. View the help test menu to see the operators you can use with the double square brackets

2. The condition you want is [[ $NUMBER -le 30 ]]. Don't forget the $

3. In the statements area, use echo and your two variables to print The next number is, I:<number>

4. The statements area should look like this: echo $TEXT I:$NUMBER

5. The elif area should look like this:

elif [[ $NUMBER -le 30 ]]
then
  echo $TEXT I:$NUMBER
fi
6. The whole if statement should look like this:

if (( NUMBER <= 15 ))
then
  echo $TEXT B:$NUMBER
elif [[ $NUMBER -le 30 ]]
then
  echo $TEXT I:$NUMBER
fi
You can add as many elif sections to an if statement as you want. Add another elif, below the last, one that uses the double parenthesis to check if the number variable is less than 46. If it is, use your two variables to print The next number is, N:<number>

1. View the help let menu to see the operators you can use with the double parenthesis

2. The operator you want it <

3. You can add another elif like this:

if CONDITION
then
  STATEMENTS
elif CONDITION
then
  STATEMENTS
elif CONDITION
then
  STATEMENTS
fi
4. The condition you want is (( NUMBER < 46 ))

5. In the statements area, use echo and your two variables to print The next number is, N:<number>

6. The statements area should look like this: echo $TEXT N:$NUMBER

7. This elif area should look like this:

elif (( NUMBER < 46 ))
then
  echo $TEXT N:$NUMBER
fi
8. The whole if statement should look like this:

if (( NUMBER <= 15 ))
then
  echo $TEXT B:$NUMBER
elif [[ $NUMBER -le 30 ]]
then
  echo $TEXT I:$NUMBER
elif (( NUMBER < 46 ))
then
  echo $TEXT N:$NUMBER
fi
Run your script if you want to see the output. It should print one of the sentences if the random number is less than 46. It may take a couple tries. Add another elif, below the last one, that uses double square brackets to check if the number variable is less than 61. If it is, use your two variables to print The next number is, G:<number>

1. View the help test menu to see the operators you can use with the double square brackets

2. The operator you want it -lt

3. The condition you want is [[ $NUMBER -lt 61 ]]. Don't forget the $

4. The statements area should look like this: echo $TEXT G:$NUMBER

5. This elif area should look like this:

elif [[ $NUMBER -lt 61 ]]
then
  echo $TEXT G:$NUMBER
fi
6. The whole if statement should look like this:

if (( NUMBER <= 15 ))
then
  echo $TEXT B:$NUMBER
elif [[ $NUMBER -le 30 ]]
then
  echo $TEXT I:$NUMBER
elif (( NUMBER < 46 ))
then
  echo $TEXT N:$NUMBER
elif [[ $NUMBER -lt 61 ]]
then
  echo $TEXT G:$NUMBER
fi
One more case to handle. Add an else at the bottom of the if that uses your two variables to print The next number is, O:<number>.

1. View the if/else in your countdown.sh file to see how you did it before

2. You don't need a condition or the then on this one

3. Here's an example:

if CONDITION
then
  STATEMENTS
elif CONDITION
then
  STATEMENTS
...
else
  STATEMENTS
fi
4. The else area should look like this:

else
  echo $TEXT O:$NUMBER
5. The whole if should look like this:

if (( NUMBER <= 15 ))
then
  echo $TEXT B:$NUMBER
elif [[ $NUMBER -le 30 ]]
then
  echo $TEXT I:$NUMBER
elif (( NUMBER < 46 ))
then
  echo $TEXT N:$NUMBER
elif [[ $NUMBER -lt 61 ]]
then
  echo $TEXT G:$NUMBER
else
  echo $TEXT O:$NUMBER
fi
Run your script a few times and make sure it's working.

1. Type ./bingo.sh in the terminal and press enter

2. Make sure you are in the project folder first

3. Run it at least two times in a row

I think the generator is done 😄 The next project is a fortune teller. Use the touch command to create fortune.sh in the same folder as the other scripts.

1. Type touch fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

Give your file executable permissions.

1. Use the chmod command with the +x flag

2. Here's an example chmod <permissions> <filename>

3. You previously used chmod +x bingo.sh

4. Type chmod +x fortune.sh in the terminal and press enter

Add a shebang at the top of your new file that uses bash again.

1. A shebang looks like this: #!<path_to_interpreter>

2. Enter which bash in the terminal to see the path to bash

3. Look at the shebang in one of your other scripts to get the syntax

4. It should look like this: #!/bin/bash

5. Add #!/bin/bash at the top of your fortune.sh file

Add comment Program to tell a persons fortune

1. Comments look like this: # <comment>

2. Add #Program to tell a persons fortune below the shebang

3. Capitalization matters

Add a title for this one like the others. This one should say ~~ Fortune Teller ~~. Don't forget the empty line before and after it.

1. Print the whole title and the empty lines with a single echo command

2. Use the echo command with the -e flag and the new line (\n) character

3. Don't forget to put it in double quotes

4. Take a look at one of the title's from a previous file for a hint

5. Here's an example: echo -e "\n<message>\n"

6. You previously used echo -e "\n~~ Bingo Number Generator ~~\n"

7. Add echo -e "\n~~ Fortune Teller ~~\n" below the comment of your fortune.sh file

Run the file once to make sure it's working.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

This program will have an array of responses. One will be printed randomly after a user inputs a question. Practice first 😄 In the terminal, create an array like this: ARR=("a" "b" "c")

1. Type the suggested command in the terminal

2. Type ARR=("a" "b" "c") in the terminal and press enter

Each variable in the array is like any other variable, just combined into a single variable. In the terminal, print the second item in the array with echo ${ARR[1]}. Note that the first item would be index zero.

1. Type echo ${ARR[1]} in the terminal

If you recall, you were able to print all the arguments to your countdown.sh script with echo $*. echo $@ would have worked as well. Similarly, you can use the * or @ to print your whole array. In the terminal, use echo to print all the items in your array.

1. Here's an example echo ${ARR[<index>]}

2. Type echo ${ARR[@]} in the terminal and press enter

The variable must be in that declare list. View your array variable using the declare command and the -p flag.

1. Here's an example: declare -p <variable>

2. Type declare -p ARR in the terminal

The -a next to it stands for array. In your script, create an array named RESPONSES. Give it these six values: Yes, No, Maybe, Outlook good, Don't count on it, and Ask again later.

1. Here's an example: VARIABLE=(value value ...)

2. Make sure any values with spaces are in proper quotes

3. You created your other array with ARR=("a" "b" "c")

4. Add RESPONSES=("Yes" "No" "Maybe" "Outlook good" "Don't count on it" "Ask again later") in your script

In your script, use echo to print the last item in the array.

1. Here's an example echo ${ARR[<index>]}

2. Remember that the first item starts at zero

3. Add echo ${RESPONSES[5]} to your fortune.sh file

Run it to see the output.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

You will randomly print one of the values. In your script, create a variable named N. Set it equal to a random number between 0 and 5, the first and last index of the array.

1. Use the modulus (%) operator and 6 to get a number between 0 and 5

2. Look at the random number you created in the bingo.sh file for a hint

3. Here's an example: VARIABLE=$(( <calculation> ))

4. Calculate a random number in the range you want with RANDOM % 6

5. Add N=$(( RANDOM % 6 )) to the script

Change your echo command to print the item in the array whose index is the random number you generated.

1. Use your $N variable as the index where you print an item from the array

2. Don't forget that scripts run from top to bottom, so you can't use any variables before they are created

3. Change the echo line to echo ${RESPONSES[$N]}

You will create a function to generate an answer. Check the help menu to see if you can find anything.

1. Enter the suggested command in the terminal

2. Type help in the terminal

See any that might help? There's one that says function. See if you can find out more about it.

1. Use the help command to find out more

2. Here's an example: help <command>

3. Type help function in the terminal

It looks like you can create a function like this:

FUNCTION_NAME() {
  STATEMENTS
}
Add an empty function named GET_FORTUNE to your script. Make sure the repsonse you are printing is the last thing in the script.

1. Add this to your script:

GET_FORTUNE() {}
2. Your echo ${RESPONSES[$N]} command should be at the bottom of the file

In your function, use echo to print Ask a yes or no question:

1. Your function should look like this:

GET_FORTUNE() {
  echo Ask a yes or no question:
}
2. Your echo ${RESPONSES[$N]} command should be at the bottom of the file

Call your function by putting the name of it below where you create it. No $ needed. Make sure the reponse you are printing is at the bottom of the file.

1. Add GET_FORTUNE below where you create your function to call it

2. Your echo ${RESPONSES[$N]} command should be at the bottom of the file

Run your script to make sure it's working.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

In your function after you print the sentence, use read to get user input into a variable named QUESTION.

1. Add read QUESTION to your function below the echo

2. Your function should look like this:

GET_FORTUNE() {
  echo Ask a yes or no question:
  read QUESTION
}
3. Your echo ${RESPONSES[$N]} command should be at the bottom of the file

Run the script again to test it out. Enter a question when it asks.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

I want to make sure the input is a question. You are going to add a loop that asks for input until the input ends with a question mark. View the help menu to see if you can find an appropriate loop.

1. Type help in the terminal and press enter

View more about that until command. That might be the one to use here.

1. Use help <command> to view more about a command

2. Type help until in the terminal and press enter

The until loop is very similar to the while loop you used. It will execute the loop until a condition is met. Here's an example:

until [[ CONDITION ]]
do
  STATEMENTS
done
Add an until loop below your function. Use the double brackets to check if QUESTION is equal to test?. Move the GET_FORTUNE function call to the statements area of the loop. It should run the function until you input test? as the question.

1. View the help [[ or help test menu to see if you can find the operator to use

2. You want the == operator

3. The condition should look like this: [[ $QUESTION == test? ]]

4. Your until loop should look like this:

until [[ $QUESTION == test? ]]
do
  GET_FORTUNE
done
5. You should only call the GET_FORTUNE function once

6. Your echo ${RESPONSES[$N]} command should be at the bottom of the file

Run the script and enter something other than test?. Then enter test? after it asks for a question the second time.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

View that help [[ expression ]] menu again. You need to find out how to test if the input ends with a question mark (?).

1. Type help [[ or help [[ expression ]] in the terminal and press enter

Let's play with these again. You can test if two strings are the same with ==. In the terminal, use the [[ ... ]]; echo $? syntax you used before to test if hello is equal to hello.

1. Be sure to use the == operator

2. Type [[ hello == hello ]]; echo $? in the terminal and press enter

Exit status of 0, it was true. Using the same syntax, test if hello is equal to world.

1. Use the [[ ... ]]; echo $? syntax

2. Be sure to use the == operator

3. Type [[ hello == world ]]; echo $? in the terminal and press enter

False. An import operator in that menu is =~. It allows for pattern matching. Using the same syntax but with this operator, check if hello contains the pattern el.

1. Use the [[ ... ]]; echo $? syntax

2. Use the =~ operator with it

3. Type [[ hello =~ el ]]; echo $? in the terminal and press enter

True. The condition was checking for el within the word hello. Using the same syntax, check if hello world contains the pattern lo wor. You will need to put them both in quotes so it recognizes the spaces.

1. Use the [[ ... ]]; echo $? syntax

2. Use the =~ operator with it

3. Type [[ "hello world" =~ "lo wor" ]]; echo $? in the terminal and press enter

Your patterns have been checking for literal matches, el and lo wor. You can use regular expression characters as well, but you can't put the pattern in quotes when you do. Using the same syntax, check if hello world starts with an h by using ^h as the pattern.

1. Make sure not to use quotes around the pattern when using regex characters it

2. Type [[ "hello world" =~ ^h ]]; echo $? in the terminal

Do it again, but use ^h.+d$ as the pattern to see if the string starts with an h, has at least one character after it, and ends with a d.

1. Use the [[ ... ]]; echo $? syntax again

2. Check if hello world contains the suggested pattern

3. Make sure not to use quotes around the pattern when using regex characters it

4. Type [[ "hello world" =~ ^h.+d$ ]]; echo $? in the terminal

In the terminal, create a variable named VAR that equals hello world.

1. Type VAR="hello world" in the terminal

Use echo to print the variable you just created.

1. Type echo $VAR in the terminal

Using the [[ ... ]]; echo $? syntax, check if your variable is equal to hello world.

1. Check the help [[ menu to find the operator to use

2. It's the == operator

3. You want to check if $VAR == "hello world"

4. Type [[ $VAR == "hello world" ]]; echo $? in the terminal

Using the same syntax, check if your variable ends with ? by using the pattern \?$.

1. Be sure to use the pattern matching operator

2. It's the =~ operator

3. You want to check if $VAR =~ \?$

4. Type [[ $VAR =~ \?$ ]]; echo $? in the terminal

It doesn't end with ?. Just to make sure I don't have the pattern wrong, check if test? ends with ?.

1. Use the same [[ ... ]]; echo $? syntax you have been using

2. Use the \?$ pattern to see if a string ends with ?

3. Make sure you're using the pattern matching operator =~

4. You want to check if test? =~ \?$

5. Type [[ test? =~ \?$ ]]; echo $? in the terminal

I think that will work. Back in your script, change the until condition to see if your variable ends with ?.

1. Use the pattern matching operator with \?$

2. It's the =~ operator

3. Your condition should look like this: [[ $QUESTION =~ \?$ ]]

4. Make sure there's spaces inside the brackets and around the operator

Run the script and input something that doesn't end with ? the first time, then something that does the second.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

I know that it asks the same thing if the input isn't what you want. You should let users know that it needs to end with ?. Add an if condition in your function that checks if [[ ! $1 ]]. Put the existing echo statement in the then area and make sure the existing read is below the whole if condition.

1. Here's an example:

if [[ CONDITION ]]
then
  STATEMENTS
fi

read QUESTION
2. Your function should look like this:

function GET_FORTUNE() {
  if [[ ! $1 ]]
  then
    echo Ask a yes or no question:
  fi

  read QUESTION
}
You can pass arguments to functions like you did with your script. This condition will check if one isn't passed and print the sentence. Add an else to your if. Use echo to print Try again. Make sure it ends with a question mark: if the condition fails.

1. Here's an example:

if [[ CONDITION ]]
then
  STATEMENTS
else
  STATEMENTS
fi
2. Your if condition should look like this:

if [[ ! $1 ]]
then
  echo Ask a yes or no question:
else
  echo Try again. Make sure it ends with a question mark:
fi
Now, your function will print one thing if you pass it any argument, and something else if not. In the until loop, add again as an argument to where you call the function.

1. Here's an example: FUNCTION_NAME argument

2. Your function call should look like this: GET_FORTUNE again

3. Your until loop should look like this:

until [[ $QUESTION =~ \?$ ]]
do
  GET_FORTUNE again
done
Now, each time the function is called in the until loop, it will pass again as an argument and print the Try again... sentence. Before your until loop, call the function without an argument so the first time it runs, it prints the initial sentence.

1. Add GET_FORTUNE before the until loop

Run the script and enter something without a question mark when it asks the first time. Use a question mark the second time.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

Awesome. One last thing. Add an empty line in front of where you print the response.

1. Change the existing echo ${RESPONSES[$N]} line

2. Use the -e flag and the new line (\n) character with the echo statement

3. Make sure to use quotes so it prints the new line

4. Run the script and see if it's working

5. The suggested command should look like this: echo -e "\n${RESPONSES[$N]}"

Run the script one more time to see if you like the output.

1. Type ./fortune.sh in the terminal and press enter

2. Make sure you are in the project folder first

Excellent. One last program to make. Use touch to create a new file named five.sh in the same folder as the others.

1. Type touch five.sh in the terminal and press enter

2. Make sure you are in the project folder first

Give your file executable permissions.

1. Use the chmod command with the +x flag

2. Here's an example chmod <permissions> <filename>

3. You previously used chmod +x fortune.sh

4. Type chmod +x five.sh in the terminal and press enter

Add a shebang to the new script that uses bash like the others.

1. A shebang looks like this: #!<path_to_interpreter>

2. Enter which bash in the terminal to see the path to bash

3. Look at the shebang in one of your other scripts to get the syntax

4. It should look like this: #!/bin/bash

5. Add #!/bin/bash at the top of your five.sh file

Add a comment below the shebang that says, Program to run my other four programs

1. Comments look like this: # <comment>

2. Add # Program to run my other four programs below the shebang

3. Capitalization matters

This program will run all the programs you made so far consecutively. Add the command to run the questionnaire.sh file.

1. The command should look like how you would execute the file in the terminal

2. Add ./questionnaire.sh to the five.sh file

Run the file to see if it works. Enter input when it asks.

1. Type ./five.sh in the terminal and press enter

2. Make sure you are in the project folder first

Add commands to run the rest of your scripts in the file. They should be in this order: questionnaire, countdown, bingo, and fortune. Don't forget that your countdown.sh file needs an argument, so put a 3 next to it.

1. Your five.sh file should have these commands:

./questionnaire.sh
./countdown.sh 3
./bingo.sh
./fortune.sh
Okay, use clear to empty out what's in the terminal before the big moment.

1. Type clear in the terminal

Run the script and enter input when it asks.

1. Type ./five.sh in the terminal and press enter

2. Make sure you are in the project folder first

Cool. I think all the scripts are done. View the help menu again I want to explore one more thing.

1. Type help in the terminal and press enter

View more about that type command.

1. Use help <command> to find out more about a command

2. Type help type in the terminal and press enter

It says you can view the type of a command with type <command>. Just for fun, lets take a look at the type of a few different commands. View the type of echo.

1. Type type echo in the terminal and press enter

View the type of the read command.

1. Type type read in the terminal and press enter

View the type of if

1. Type type if in the terminal and press enter

View the type of then

1. Type type then in the terminal and press enter

Those were all from the help menu and described as a shell builtin or shell keyword. View the type of bash

1. Type type bash in the terminal and press enter

That's the location of the bash command. View the type of psql.

1. Type type psql in the terminal and press enter

It's showing the location of the commands. View the type of your ./five.sh file.

1. Type type ./five.sh in the terminal and press enter

Last step, close the terminal with the exit command. Thanks and happy coding!

1. Type exit in the terminal and press enter

Congratulations on completing "Learn Bash Scripting by Building Five Programs"!
You've reached the end of the road...
To go down another path:

- open a new VSCode workspace
- relaunch the CodeRoad app
- select a new tutorial
