Hey, 
Back for even more? Today we're going to learn how to use VIM and github thru the bash terminal.

---
## Step 1: Logging into IENG6

First you're going to want to ssh into the ieng6 server.
Keys Pressed: 
`ssh yourlogin@ieng6.ucsd.edu` `<enter>` 
`yourpassword' `<enter>`
This logs into ieng6 using ssh.
  
![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/ieng6LoginLabReport4.png)
  
## Step 2: Cloning Lab 7 repo
  
Keys Pressed:
`git clone` `<ctrl+v>` `<enter>` as I had `https://github.com/l1joseph/lab7` copied to my clipboard allowing me to more quickly create a clone of the repo. 

![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/SS2LabReport4.png)
  
## Step 2: Running Tests(Fail)

Keys Pressed:
`bash t` `<tab>` `<enter>` to autocomplete to `bash test.sh` which runs the test script, and shows that tests fail.  
 
![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/SS3LabReport4.png)
 

## Step 3: Editing Code

Keys Pressed: 
`vim` `L`  `<tab>` `.` `<tab>` `<enter>` This is to enter vim editor for `ListExamples.java', resulting terminal input should be 'vim ListExamples.java' and hit enter.
Assuming that your cursor is at top of test when entering vim: `42j` `e` `r` `2`  `:wq`
These commands first move cursor down 42 lines, then to the end of the first word on that line using `e`. Next `r` is for replace, where we're replacing 1 with 2.
`:wq` saves changes to file and quits vim.

![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/SS5LB4.png)

Before & After:
![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/SS6.png)
![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/SS7.png)
  
## Step 4: Running Tests(Fail)

Keys Pressed:
`bash t` `<tab>` `<enter>` to autocomplete to `bash test.sh` which runs the test script, and shows that tests pass now.  
 
![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/SS8LB4.png)

## Step 5: Pushing to Github.

Keys Pressed:
`git add` `L` `<tab>` `.java` `<enter>` The resulting input should correspond to `git add ListExamples.java`
`git commit -m "Updated Bug"` `<enter>` This is the commit message, where you update the repo with your changes.
`git push origin` This should ask you to enter your github username and password, pressing `<enter>` after each to authorize push.

![Image](https://github.com/l1joseph/cse15l-lab-reports/blob/main/SS9LB4.png)
