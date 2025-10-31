# Lab8-part-2
Part 2 of Lab 8 for prog101

19. It would be nice to define that CommandWords class is responsible for producing (but not printing!) 
the list of command words, but that the Game class should decide how it is presented to the user. 
Change the ShowAll from CommandWords to not print the list of commands, but only produce and 
return it. Make sure that your program still works as before.

19b.
//commandWords class
public static String showCommandWords()
    {
        StringBuilder listCommands = new StringBuilder();
        listCommands.append("     ");
        for(String command : getValidCommands())
        {
            listCommands.append(command + "  ");
        }
        String listOfCommands = listCommands.toString();
        System.out.println("Your command words are:");
        return listOfCommands;
    }

//game class
/**
     * Print out some help information.
     * Here we print some stupid, cryptic message and a list of the 
     * command words.
     */
    private void printHelp() 
    {
        System.out.println("You are lost. You are alone. You wander");
        System.out.println("around at the university.");
        System.out.println();
        System.out.println(CommandWords.showCommandWords());
    }

20. If the game has a lot of commands, it might be useful in the getCommandList method to return the list
 sorted alphabetically. Implement that feature using the static sort method of the Arrays class in the 
java.util package.

20b.
//in commandWords class
public static String[] getValidCommands()
    {
        Arrays.sort(validCommands);
        return validCommands;
    }

21. How might the CommandWords class provide more detail on each command? For instance, a list of 
command words, whether each has a second word, and what each command does. Add a method to your
version of CommandWords to provide this and add a command word to the game whose use will call 
that method and displays what it returns.

We could add further fields to a command such as int length and String Utility. Then we simply just return
those fields with accessor methods and print them out in the CommandWords class.

22. Find out what the model-view-controller pattern is. You can do a web search to get information, or you 
can use any other sources you find. How is it related to the topic discussed here? What does it suggest? 
How could it be applied to this project? (Only discuss its application to this project, as an actual 
implementation would be an advanced challenge exercise.) 



23. Extend either your adventure project or the zuul-better project so that a room can contain a single item. 
Items have a description and a weight. When creating rooms and setting their exits, items for this game 
should also be created. When a player enters a room, information about an item in this room should be 
displayed. 



24. How should the information be produced about an item present in a room? Which class should produce 
the string describing the item? Which class should print it? Why? Explain in writing. If answering this 
exercise makes you feel you should change your implementation, go ahead and make the changes.

 
 
25. Modify the project so that a room can hold any number of items. Use a collection to do this. Make sure 
the room has an addItem method that places an item into the room. Make sure all items get shown 
when a player enters a room. 



26. Implement a back command. This command does not have a second word. Entering the back command 
takes the player into the previous room they were in.



27. Test your new command. Does it work as expected? Also, test cases where the command is used 
incorrectly. For example, what does your program do if a player types a second word after the back 
command? Does it behave sensibly? 



28. What does your program do if you type “back” twice? Is this behavior sensible?



29. Challenge exercise Implement the back command so that using it repeatedly takes you back several rooms,
all the way to the beginning of the game if used often enough. Use a Stack to do this. (You may need to 
find out about stacks. Look at the Java library documentation.)



30. Replace the sequence of if-else tests in the processCommand method of your Game class with an 
equivalent switch statement. In the default case, as well as printing a “command not recognized” message,
 print the list of available commands.
