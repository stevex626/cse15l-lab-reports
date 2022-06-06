# CSE 15L Week 10 Lab Report 5

## Use vimdiff to compare results

* First, we want the most updated versions of the markdown-parser, so we want to do `git clone https://github.com/nidhidhamnani/markdown-parser.git cse15lsp22-lab5` and `git clone https://github.com/Miyuki-L/markdown-parser.git cse15lsp22-lab5-self` on the server. I am using a representative implementation from my group (Helen Lin).

* Then, we type `cd cse15lsp22-lab5` to get into the directory with the "script.sh" file and then type `vim script.sh` to edit the file using vim.

* Add a line `echo $file` in the script.sh file (as shown below) and then press `:wq` to write and quit. The purpose of this step is to show the name of each file before showing their results so that we know which result belongs to which test file.

![image](lab1.jpg)

* Next, in order to compare the different results, we need to copy this "script.sh" file and the test files into our own implementation. To do that, we use the following commands:
```
cp -r cse15lsp22-lab5/test-files cse15lsp22-lab5-self/
cp cse15lsp22-lab5/script.sh cse15lsp22-lab5-self/
```
* Next, we `cd` into each directory, and type `bash script.sh > results.txt` to store the results of the test files using different implementations into a file named **results.txt**.

* We then use the following `vimdiff` command to show the differences in the results (screenshot below)
```
vimdiff cse15lsp22-lab5-self/results.txt cse15lsp22-lab5/results.txt
```

![image](lab2.jpg)

* As we can see, the results in **14.md** and **483.md** are different.

![image](lab3.jpg)

![image](lab4.jpg)

* The [link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/14.html.test) to **14.md**
* The [link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/483.html.test) to **483.md**

## 14.md
* The expected output for **14.md** should be nothing, as shown in the preview:

![image](lab5.jpg)

* This means that the representative implementation is correct while the shared version is not.

* I think the problem with the code in the shared version is that it does not have enough conditions check for special characters. In the **14.md** case, when the program encounters characters like "/" (escape character) which makes the link following it an invalid link, the program still considers the link behind the escape character to be a valid link. To provide a fix, we should add more conditions in the while loop to check for special characters like "/" and does not include the links following it. And I think we can do that after the line of where the openParen is first initialized.

![image](lab6.jpg)

## 483.md
* The expected output for **483.md** should be nothing, as shown in the preview:

![image](lab7.jpg)

* This means that the representative implementation is correct while the shared version is not.

* I think the problem with the code in the shared version is in the `getLinks` method. I don't think the code needs the nextCodeBlock. If the program doesn't detect any brackets, it should just return nothing by breaking the loop and return an empty arraylist.

![image](lab8.jpg)


