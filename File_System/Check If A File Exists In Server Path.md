# Hex Breaker Tech - Power Automate DPA Tutorials

## Episode 2: Checking if a File Exists on a Server Using File System

### Description
Streamline your file management with Power Automate! 

In this tutorial, we’ll show you how to create an instant cloud flow that checks if specific files exist on a server using the File System connector. Perfect for automating your workflows and keeping your systems running smoothly.

Low Code Formula Example:
- Join Example:
  
  join(outputs('List_Files_in_Folder_-_Source_File')?['body'], ',')
  

### Script
Welcome back to Hex Breaker Tech!  
Today, we’re unleashing some automation magic that’s more relentless than John Wick—hunting down files on your server and checking if they exist using Power Automate. No need to assemble the Avengers for this task; we’ve got it all under control!

We kick off with a manual trigger for an instant cloud flow. Next, we’ll initialize two string variables with example filenames—think of them as the secret codes to your hidden files. Then, using the File System connector, we’ll list all the files in a specified directory. 

Here’s where the real action begins: we compose a string that joins all the listed folder files. With this, we can set up two conditions—one for each filename—checking if the file exists. If our condition is true, we send a confirmation email; if false, we send a denial. Just like Neo in the Matrix, we’re making choices, and every outcome is in our control.

And there you have it! Another tech hex shattered, files checked, and workflows running smoother than a John Wick reload. If this helped you, hit that like button and subscribe for more Power Automate wisdom. As they say in the world of tech, ‘The code never stops, and neither should your automation!’

---



