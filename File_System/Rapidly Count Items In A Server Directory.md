# Hex Breaker Tech - Power Automate DPA Tutorials

## Episode 3: Counting Files in a Folder Using File System

### Description
Supercharge your file management with Power Automate! 

In this episode, we’ll show you how to set up an instant cloud flow to efficiently count the number of files in a folder using the File System connector. Perfect for optimizing your workflows and staying on top of file organization without looping through your listed folders.

Formula Examples:
- Join Example:
  
  join(outputs('List_Files_in_Folder_-_Source_File')?['body'], ',')
  
- Count Based on String Value:
  - All items in folder:
    
    sub(length(split(variables('StringOutput'),'"DisplayName":')),1)
    
  - All subfolders in folder:
    
    sub(length(split(variables('StringOutput'),' "IsFolder":true')),1)
    
  - All files in folder:
    
    sub(length(split(variables('StringOutput'),' "IsFolder":false')),1)
    

### Script
Greetings, Hex Breakers!  
Today, we’re diving into file management with the precision of a Jedi Knight—using Power Automate to count the number of files in a folder, without the hassle of looping through every single one. 

We start with a manual trigger for our instant cloud flow, followed by using the File System action to list all files in a folder. Next, we’ll compose a string that concatenates all the listed files. This is where the magic happens: we initialize a string variable to store the composed outputs, and then we initialize an integer variable to count the number of times a particular string value occurs within that concatenated string.

Once we have our count, we send an email with the results—no need for a Jedi Council to confirm this one, just a quick automated message to keep you on top of your file management game.

And that’s another hex broken! Files counted, emails sent, and workflows optimized. If you’re loving these automation tricks, don’t forget to like, subscribe, and hit that notification bell. Because in the words of a wise Jedi, ‘Automation is the path to the dark side... of manual tasks. Let’s keep it light!’

---
