---
layout: post
title:  "Software Carpentry Workshop"
date:   2015-1-07 10:45:00
comments: true
---
 
UMich WiSE Software Carpentry Workshop: intermediate room
5-6 January 2015

Link to workshop website:
http://danabauer.github.io/2015-01-05-wise-umich/

**If students are having trouble install software on their machines, we have a Linux VM available. Scroll to the bottom of the page for installation instructions: http://danabauer.github.io/2015-01-05-wise-umich/**

Instructors
Dana Bauer
Sarah Supp
Christie Bahlai
Kara Woo

Helpers
Alyxandria Schubert
Iris Holmes
Marian Schmidt
Michelle Berry

Handy dandy bit.ly link for this etherpad: http://bit.ly/umich-wise-intermediate

============================================================
DAY 2: git & SQL

Material for this lesson:
1. Software Carpentry tutorials: http://danabauer.github.io/2015-01-05-wise-umich/novice/sql/
2. Get yer data here: https://app.box.com/s/zt7taox3c9bwhznbzir7
•	sqlite3 survey.db < gen-survey-database.sql (command to generate database)
3. Install SQLite plugin in Firefox: https://addons.mozilla.org/en-US/firefox/addon/sqlite-manager
•	In Firefox, go to Tools --> SQLite manager


SQL Resources
Getting started with SQLite: http://cs.stanford.edu/people/widom/cs145/sqlite/SQLiteIntro.html
Loading data into SQLite: http://cs.stanford.edu/people/widom/cs145/sqlite/SQLiteLoad.html
There are a number of R packages that let you interact with SQL databases; check out dplyr, RMySQL, RPostgreSQL

SQL: Structured Query Language
Databases consist of tables, which are analogous to sheets in Excel
 
Getting started:
sqlite3 survey.db < gen-survey-database.sql  generates a database file from the .sql file
sqlite3 survey.db loads the database file
.exit to leave the database
.tables to view tables
.schema to view structure of the table data (somewhat similar to `str()` function in R)
    - .schema nameoftable to view schema for a specific table
These commands above (.exit, .tables, .schema) are specific to sqlite (the flavor of SQL we are using)
select * from nameoftable;    query the table, will show contents of entire table
    select * from nameoftable where ident = 'nameexample';     query the table, will show contents of table where matches
    
Note: sql is case INsensitive

SELECT distinct nameoffield from nameoftable     shows only the distinct values

order by tells how to sort the data
    - options are asc or desc

Note: If you use "where" in your query with "order by", this comes first then the "order by" statement.

Note: If joining two tables, field names in the query should begin with "tablename." so has the form "tablename.fieldname".

Null values: see section 5 and table 1 of this paper 
http://library.queensu.ca/ojs/index.php/IEE/article/view/4608

Steps to export a query to csv:
.mode csv tells sqlite to dump data to a csv file
.output test.csv tells sqlite to store output in test.csv
run your query:  select * from Person;
.output stdout
.exit

Dana likes a tool called open refine to clean data : http://openrefine.org/

==================================================
Day 2 morning Git/Version control

Version control:
git is a simple programming language for version control that all happens locally on your computer
github is a site that helps you store your repositories online so they can be accessible from multiple computers

which *nameofprogram* tells you where the program is ie which git

Configuring:
This only needs to be done once per machine unless you want to change one of the global settings

git config --global user.name "Your name"
git config --global user.email "Your email"
git config --global color.ui "auto"
git config --global core.editor "your editor (ie nano) "

Initializing:
1. make a directory using mkdir
2. move to the repository using cd
3. git init (initializes the current directory as a git repository)
4. type ls -a and see that your computer has created a .git file

Structure:
1. working copy
2. git add --> staging area. The staging area helps set up the commit. Add all of the files that you want to commit together with the same message
3. git commit --> file is under version control in repository

Commands
git status    shows the status of files in git repository
    git status --ignored    shows the ignored files that are included in the '.gitignore' file
git add filename     will move the copy from working copy to "staging area"
git commit -m "text to describe changes made"    version of file is saved in version control repository, the '-m' allows you to add the message
git log  prints out a log of all your git calls. Each call has a unique identifier. Shows commits in reverse chronological order.
    git log --oneline    shows a one line summary for each commit
    git log -2 --oneline    adding the number 2 will show you the last 2 recent commits
git diff shows you all the changes that have occurred since last commit
    git diff --staged    will show you the difference between the staged files and the last committed files
    git diff HEAD~1 filename    HEAD means the most recent commit, this is asking for the difference between the most recent commit and the version right before it (indicated by '1')
    git diff id1 id2 filename    use shortened version (maybe about 6 characters) of the identifier that git gave to commits to compare any two older commits. It's good to indicate the filename or else will get the differences of all files within that commit
git reset HEAD filename    will unstage the specified file
git checkout HEAD filename    will bring you back a copy from the last commit
git remote add origin https://github.com/yourgithub/yourrepo    to add the remote repository from github, using the link they gave when you made the new repository. Origin is the standard name, but could be anything.
    git remote -v    shows you the remote repositories that you have connected
git push origin master     pushes the master branch on your computer to the remote repository which is called origin
git pull origin master    pulls any changes from the github version
git clone https://github.com/githubname/githubrepo     clone (copy) someone else's entire repository on github onto your computer

Note: If you make edits after you add a file to the staging area, git diff will show differences between the working file and the file in the staging area. git commit will still only commit the file(s) that has been added to the staging area. 

Forking: make a copy of somebody else's repository into your github so you can work with it and edit it for your own use

.gitignore file: a list of files to ignore when making commits
    1. make a new file named .gitignore
    2. commit this file! 
     git status --ignored  shows you a list of ignored files
     
Linking the repository on your computer to github:
1. go to github, create a new repository 
2. In shell (make sure you're in the repository): 
    git remote add origin https://github.com/yourgithub/yourrepo
    git remote -v (shows you the remote repositories that you have connected)
    git push origin master (pushes the master branch on your computer to "origin" the remote  repo)
    
Add Collaborators:
1. Go to the repository on Github
2. On the right hand panel click Settings 
3. Click collaborators, search for person and add.

Clone somebody elses repo onto your computer:
git clone https://github.com/githubname/githubrepo
Note: git pull will pull down latest updates and can only be done once you've established a connection with a remote repository, git clone will completely copy a remote repository to your machine

Working with git in RStudio: 

Go to RStudio and open up the project you want to turn into a repo
1. In Rstudio: Tools >> Project Options >> Git/SVN and select git as your version control
2. In Rstudio: go to the Git tab next to environment and history tabs and select which files you want to add to the staging area 
    - use diff to see changes
    - use commit button to commit items selected for staging area

Linking your rstudio version control with github:    
1. In Github: make a new repository and copy the url link
2. In bash:  cd to the local repository
                git remote add origin https://github.com/yourrepo
                git remote -v (to see that you've established a connection)
                git push -u origin master (pushes your repo in rstudio to the origin on github)
Now you can use the green and blue arrows to push and pull



Other learning resources
Try git: https://try.github.io/levels/1/challenges/1
GitHub for Beginners: Don't Get Scared, Get Started: http://readwrite.com/2013/09/30/understanding-github-a-journey-for-beginners-part-1

Questions
•	Can I use git with Dropbox? http://stackoverflow.com/questions/1960799/using-git-and-dropbox-together-effectively  LOTS of pros and cons here.
•	Why is git always asking for my password?
https://help.github.com/articles/why-is-git-always-asking-for-my-password/
•	I'm tired of entering my username and password. What can I do?   
o	Setting your username in git:
https://help.github.com/articles/setting-your-username-in-git/ (commits now show up under your username)
**You  can do the above with your password BUT please note that your password  will be stored in plaintext in your git config file.**
o	Use a credential helper: https://help.github.com/articles/caching-your-github-password-in-git/
o	A more secure option is to use SSH
•	https://help.github.com/articles/generating-ssh-keys/
•	https://help.github.com/articles/which-remote-url-should-i-use/#cloning-with-ssh

============================================================
DAY 1: R & Shell

Link to data for R exercises:
https://dl.dropboxusercontent.com/u/98197254/data.zip 

R
#rstats for help on twitter

R style notes:
<- is more readable than =
include parameter names ie read.csv(file = "surveys.csv") instead of read.csv("surveys.csv")
functions don't require a return statement, but it improves readability


Getting Started:
File > New Project to create a clean environment and new directory

Use `<-` to assign values to objects, e.g.:
x <- 5

To load data: 
surveys <- read.csv(file = "surveys.csv")
inflam2 <- read.csv(file = "inflammation-02.csv", header = FALSE)
'read.csv' assumes that the file has a header line.  If it does not include a header, use:
surveys <- read.csv(file = "surveys.csv", header=FALSE)
Note: Header names should start with characters (preferred by R) rather than start with numbers. 

To view data:
Double click on 'surveys' object in the environment window
head(surveys) will show you the first few lines of surveys

To learn more about data:
class(inflam2)
dim(inflam2) -- gives number of rows and columns

View a single cell:
inflam2[30, 2] (format is dataframe[row, column])

View a column:
inflam2[, 2]

View a range of rows and columns:
inflam2[1:4, 1:5]

Note: R indexing begins with 1, NOT 0.

Function 'apply'
Use apply function to repeat command over all rows or columns
- MARGIN specifies whether to repeat function over rows (1) or columns (2)
-much faster than a for loop
-can use to calculate things like mean, max, min, sd (standard deviation), i.e.:

#average
avg_day_inflam<-apply(inflam2, MARGIN=2, mean)
plot(avg_day_inflam)  #plots the results


For troubleshooting:
Type '?read.csv' This will open the help files/R documentation for this particular function ('read.csv').
To search for help with a function whose name you don't know: help.search("searchterm")
Stack overflow online is a good resource to use for looking up errors. (http://stackoverflow.com/ )

To read in all files that start with `inflam`:
# list the file names of files that begin with `inflam` in the current directory
filenames <- list.files(pattern = "^inflammation")
# read in all the CSV files -- this puts them into a list called `files`, from which you could extract the individual data frames
files <- lapply(filenames, read.csv, header = FALSE)
# give each list element a name that corresponds to the file it came from
names(files) <- filenames

Writing functions:

#defining simple function 
fahr_to_kelvin<-function(temp){
  kelvin<-((temp-32)*(5/9))+273.15
  return(kelvin)
}

kelvin_to_c <- function(temp) {
  celsius <- temp - 273.15
  return(celsius)
}

#use the function
fahr_to_kelvin(7)

Notes: 
-'temp' is the parameter taken in by the defined function, which returns 'kelvin'.
-While you don't need to return an object in your defined function, it is always good practice.
-The variable 'kelvin' ONLY exists inside the function.  So it won't be a part of your work environment.

Vectors:
#vector of numbers
vec<-c(1, 2, 3)

#vector of characters
vec<-c("1", "2", "3")

Create a function that puts the vector `asterisk` at the beginning and end of the vector `best_practice`:

best_practice <- c("Write", "programs", "for", "people", "not", "computers")
asterisk <- "***"

fence <- function(original, wrapper) {
    result <- c(wrapper, original, wrapper)
    return(result)
}


For loops:
Basic structure:
for(variable in collection){
    do something
    }

Example:
length(best_practice) #this is the same as:

len<-0
for(v in best_practice){
  len<- len+1
}
len


Regular expressions

To list all files that begin with inflammation and end in csv:
"^inflammation.+\\.csv$"
^ means "starts with"
.+ is the wildcard
\\. deals with the fact that the . is a special character
$ means that csv is the end

list.files(pattern=

Regular expression ("regex") resources:
•	Concept map: http://teaching.software-carpentry.org/2014/04/30/concept-map-for-regular-expressions/ (you can see why I was wrong about the * -- this will be relevant in the shell)
•	Online tool to test regexes, includes cheatsheet and examples: http://www.regexr.com/ 
•	Software carpentry materials on regexes: http://software-carpentry.org/v4/regexp/index.html 
•	


Shell basics

For apple users, you can find a comprehensive list of commands here: http://ss64.com/osx/
- also can use the command 'man', i.e., "man ls" will return the manual and the options for the 'ls' command. Typing 'q' will quit the manual. Additionally can use "info ls", which basically shows the same thing as "man ls".

For windows users use --help ie ls --help

DONT use spaces in filenames EVER
    - but you can get around them with " "  and an absolute pathname 
    - or by placing a '\' before the space

echo spits back whatever statement you type in
    - use single quotes to get around special characters
    
pwd "print working directory" shows you where you are

cd "change directory" changes you to a different directory

to return to home directory:
cd ~
cd
cd /Users/yourname

To back up one directory:
cd ..  
. current directory
. .  parent directory

ls lists contents in the given directory
    ls -l long form--> gives permissions, owners, size, etc details of the files in the directory
    ls -lt sorts files by time since last modified
    ls -lh human readable sizes
    ls -S sorts by file size
    ls -a shows hidden files
    ls -F outs slash after folders so you can more easily distinguish them from files
    ls -d */    will show only the directories in a folder
    

Shortcuts:
Up arrow - will show recent commands used
Tab - will complete the filename or foldername you are currently writing (THIS ALSO WORKS IN R!! For the R console and scripts and inputting parameters, calling functions, variables, and other objects in your environment)
    -If you hit tab twice, it will give you a list of files/folders that match what you've started typing
history    gives the whole list of commands that you've used
    !NUMBER     will execute the command on line NUMBER, found in the history

Inspecting files:
file surveys.csv gives you information on the file named surveys.csv
head shows you the first 10 lines
tail shows you the last 10 lines
wc prints out the number of lines, number of words, number of bytes in the file
    - if you just want number of lines you can do wc -l surveys.csv
less surveys.csv let you go line by line


Manipulating files:
touch testfile    will make a new empty file called testfile
rm -i testfile    will delete testfile, the '-i' is optional but good to use because it will double check you want this file deleted
nano notes.txt    creates and opens editor to edit notes.txt
mkdir newdir     creates a new folder called newdir in current directory
cp file1 newdir/     will copy file1 to the directory called newdir/
mv file2 newdir2/    will move file2 to directory called newdir2/
mv file3 file4    will rename file3 as file4
rmdir directory    will remove directory if directory is empty
rm -r directory    will remove directory and all its contents

Shell Regular expressions
*    Asterisk is the wildcard, will match any character and any length of characters
?    matches a single character

text editors:
nano
vim
emacs 
notepad++
text wrangler, for macs
sublime


Data Management:

A Quick Guide to Organizing Computational Biology Projects by William Noble:
http://www.ploscompbiol.org/article/info%3Adoi%2F10.1371%2Fjournal.pcbi.1000424#pcbi-1000424-g001

Tips:
- Dont move or rename files because it makes it harder to reproduce results and track where things have gone
- version control is not ideal for data because you can't remove or compress old and obsolete data files
- One approach would be to keep the data file the same name but put new versions of it into folders which are sorted by date
- USE METADATA
•	who is the data from
•	when was it generated
•	what were the experiment conditions
- Separate metadata file for each data file takes too long, so use a README file


Big Picture:
Project folder
-*src
    -*scripts, source code, etc
-experiments
    -yyyy-mm-dd
        -results from running scripts on data
-data
    -*README
    -yyyy-mm-dd
            -*README
            -data files
* indicates under version control
Readme files should include where from data generated and how. 

Note: This isn't a one size fits all.  For example, pipelines may need a different layout, possibly by dates of analysis. 


Learn more about your bash profile: http://natelandau.com/my-mac-osx-bash_profile/
Dotfiles! http://code.tutsplus.com/tutorials/setting-up-a-mac-dev-machine-from-zero-to-hero-with-dotfiles--net-35449
Where do I put software that I compile myself? http://unix.stackexchange.com/questions/30/where-should-i-put-software-i-compile-myself

What's in my $PATH? 
What's in my .bash_profile?

Type "man bash" to learn more!
•	/bin/bash
       The bash executable
•	/etc/profile
       The systemwide initialization file, executed for login shells
•	~/.bash_profile
       The personal initialization file, executed for login shells
•	~/.bashrc
       The individual per-interactive-shell startup file
•	~/.bash_logout
       The individual login shell cleanup file, executed when a login shell exits
•	~/.inputrc
       Individual readline initialization file

Simple .bash_profile example:
nano ~/.bash_profile        #This will create the file and open it for editing

Within this file you can use the 'alias' command:
alias test = "cd ~/Desktop/mothur/abxD01"
This will create a shortcut command called "test", which when called in the terminal will automatically perform "cd ~/Desktop/mothur/abxD01". 

Data management slides
http://software-carpentry.org/v4/data/mgmt.html

Data Analysis Networking Group (DANG)!
-to get on the email list, go to the mcommunity page, sign in, and add your name!
https://mcommunity.umich.edu/#group:umich%20dang
-if this doesn't work, email me at aseekatz@umich.edu, and I will add you
