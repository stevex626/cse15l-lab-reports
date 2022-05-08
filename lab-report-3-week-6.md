# CSE 15L Week 6 Lab Report 3

## Streamlining ssh Configuration
1. Open the ssh folder on your local device. I am using a MacBook so
I can find and open the .ssh file through using the "Spotlight Search",
as shown below
![image](lab1.jpg)

2. Open a folder named "config" inside the ssh folder. If the folder doesn't exist, create one inside the ssh folder with a "txt" extension.
![image](lab2.jpg)

3. Type the following into the config folder
```
Host ieng6
    HostName ieng6.ucsd.edu
    User cs15lsp22apl (this is my username)
```

4. Now try and type `ssh ieng6` in your terminal. If everything is set up correctly, you should see something similar to the picture below
 ![image](lab3.jpg)

5. If we want to use the `scp` command to copy a file from the local to the remote server, we can just simply type the following line:
`scp helloworldtext.txt cs15lsp22apl@ieng6.ucsd.edu:~/` 
where the file name and its extension follows the `scp` and then the course-specific account username at the end.

7. Now we log in back to **ieng6** and we see that the text file has been copied to the remote server
![image](lab5.jpg)

## Setup Github Access from ieng6
1. First, we need to clone the **MarkdownParse** files from our repository into the remote server *ieng6*
![image](lab4.jpg)

2. Then, 