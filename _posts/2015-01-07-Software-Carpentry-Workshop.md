---
layout: post
title:  "Software Carpentry Workshop Notes"
date:   2015-01-07 10:45:00
comments: true
---
 Notes from the Intermediate room at the workshop.





<body><b>UMich WiSE Software Carpentry Workshop: intermediate room</b><br
/>5-6 January 2015<br
/><br
/>Link to workshop website:<br
/><a href="http://danabauer.github.io/2015-01-05-wise-umich/">http://danabauer.github.io/2015-01-05-wise-umich/</a><br
/><br
/>If students are having trouble install software on their machines, we have a Linux VM available. Scroll to the bottom of the page for installation instructions: <a href="http://danabauer.github.io/2015-01-05-wise-umich/">http://danabauer.github.io/2015-01-05-wise-umich/</a><br
/><br
/><u>Instructors</u><br
/>Dana Bauer<br
/>Sarah Supp<br
/>Christie Bahlai<br
/>Kara Woo<br
/><br
/><u>Helpers</u><br
/>Alyxandria Schubert<br
/>Iris Holmes<br
/>Marian Schmidt<br
/>Michelle Berry<br
/><br
/>Handy dandy bit.ly link for this etherpad: <a href="http://bit.ly/umich-wise-intermediate">http://bit.ly/umich-wise-intermediate</a><br
/><br
/>============================================================<br
/><b>DAY 2: git &amp; SQL</b><br
/><br
/><b>Material for this lesson:</b><br
/>1. Software Carpentry tutorials: <a href="http://danabauer.github.io/2015-01-05-wise-umich/novice/sql/">http://danabauer.github.io/2015-01-05-wise-umich/novice/sql/</a><br
/>2. Get yer data here: <a href="https://app.box.com/s/zt7taox3c9bwhznbzir7">https://app.box.com/s/zt7taox3c9bwhznbzir7</a><br
/><ul><li>sqlite3 survey.db &lt; gen-survey-database.sql (command to generate database)</li></ul
>3. Install SQLite plugin in Firefox: <a href="https://addons.mozilla.org/en-US/firefox/addon/sqlite-manager">https://addons.mozilla.org/en-US/firefox/addon/sqlite-manager</a><br
/><ul><li>In Firefox, go to Tools --&gt; SQLite manager<br/><br
/><br/><br
/></li></ul
><b>SQL Resources</b><br
/>Getting started with SQLite: <a href="http://cs.stanford.edu/people/widom/cs145/sqlite/SQLiteIntro.html">http://cs.stanford.edu/people/widom/cs145/sqlite/SQLiteIntro.html</a><br
/>Loading data into SQLite: <a href="http://cs.stanford.edu/people/widom/cs145/sqlite/SQLiteLoad.html">http://cs.stanford.edu/people/widom/cs145/sqlite/SQLiteLoad.html</a><br
/>There are a number of R packages that let you interact with SQL databases; check out dplyr, RMySQL, RPostgreSQ<br
/>TIDY DATA: <a href="http://vita.had.co.nz/papers/tidy-data.pdf">http://vita.had.co.nz/papers/tidy-data.pdf</a><br
/><br
/><b>SQL: Structured Query Language</b><br
/>Databases consist of tables, which are analogous to sheets in Excel<br
/>&nbsp;<br
/><u>Getting started:</u><br
/><b>sqlite3 survey.db &lt; gen-survey-database.sql</b>&nbsp; generates a database file from the .sql file<br
/><b>sqlite3 survey.db </b>loads the database file<br
/><b>.exit</b> to leave the database<br
/><b>.tables</b> to view tables<br
/><b>.schema</b> to view structure of the table data (somewhat similar to `str()` function in R)<br
/>&nbsp;&nbsp;&nbsp; - .schema nameoftable to view schema for a specific table<br
/>These commands above (.exit, .tables, .schema) are specific to sqlite (the flavor of SQL we are using)<br
/><b>select * from </b><i>nameoftable</i>;&nbsp;&nbsp;&nbsp; query the table, will show contents of entire table<br
/>&nbsp;&nbsp;&nbsp; <b>select * from </b><i>nameoftable</i> <b>where </b><i>ident</i><b> =</b> 'nameexample'<b>;&nbsp;</b>&nbsp;&nbsp;&nbsp; query the table, will show contents of table where matches<br
/>&nbsp;&nbsp;&nbsp;&nbsp;<br
/>Note: sql is case INsensitive<br
/><br
/><b>SELECT distinct </b><i>nameoffield</i><b> from </b><i>nameoftable</i><b>&nbsp;&nbsp;&nbsp;&nbsp; </b>shows only the distinct values<br
/><br
/><b>order by </b>tells how to sort the data<br
/>&nbsp;&nbsp;&nbsp; - options are asc or desc<br
/><br
/>Note: If you use "where" in your query with "order by", this comes first then the "order by" statement.<br
/><br
/>Note: If joining two tables, field names in the query should begin with "tablename." so has the form "tablename.fieldname".<br
/><br
/>Null values: see section 5 and table 1 of this paper&nbsp;<br
/><a href="http://library.queensu.ca/ojs/index.php/IEE/article/view/4608">http://library.queensu.ca/ojs/index.php/IEE/article/view/4608</a><br
/><br
/><b>Steps to export a query to csv:</b><br
/><b>.mode csv</b> tells sqlite to dump data to a csv file<br
/><b>.output test.csv</b> tells sqlite to store output in test.csv<br
/>run your query:&nbsp; <b>select * from Person;</b><br
/><b>.output stdout</b><br
/><b>.exit</b><br
/><br
/>Dana likes a tool called open refine to clean data : <a href="http://openrefine.org/">http://openrefine.org/</a><br
/><br
/>==================================================<br
/>Day 2 morning Git/Version control<br
/><br
/><b>Version control:</b><br
/>git is a simple programming language for version control that all happens locally on your computer<br
/>github is a site that helps you store your repositories online so they can be accessible from multiple computers<br
/><br
/><b>which</b> *nameofprogram* tells you where the program is ie which git<br
/><br
/><b>Configuring:</b><br
/>This only needs to be done once per machine unless you want to change one of the global settings<br
/><br
/>git config --global user.name "Your name"<br
/>git config --global user.email "Your email"<br
/>git config --global color.ui "auto"<br
/>git config --global core.editor "your editor (ie nano) "<br
/><br
/><b>Initializing:</b><br
/>1. make a directory using mkdir<br
/>2. move to the repository using cd<br
/>3. git init (initializes the current directory as a git repository)<br
/>4. type ls -a and see that your computer has created a .git file<br
/><br
/><b>Structure:</b><br
/>1. working copy<br
/>2. git add --&gt; staging area. The staging area helps set up the commit. Add all of the files that you want to commit together with the same message<br
/>3. git commit --&gt; file is under version control in repository<br
/><br
/><b><u>Commands</u></b><br
/><b>git status</b>&nbsp;&nbsp;&nbsp; shows the status of files in git repository<br
/><b>&nbsp;&nbsp;&nbsp; git status --ignored</b>&nbsp;&nbsp;&nbsp; shows the ignored files that are included in the '.gitignore' file<br
/><b>git add</b><i> filename&nbsp;</i>&nbsp;&nbsp;&nbsp; will move the copy from working copy to "staging area"<br
/><b>git commit -m</b> <i>"text to describe changes made"</i>&nbsp;&nbsp;&nbsp; version of file is saved in version control repository, the '-m' allows you to add the message<br
/><b>git log&nbsp; </b>prints out a log of all your git calls. Each call has a unique identifier. Shows commits in reverse chronological order.<br
/><b>&nbsp;&nbsp;&nbsp; git log --oneline</b>&nbsp;&nbsp;&nbsp; shows a one line summary for each commit<br
/><b>&nbsp;&nbsp;&nbsp; git log -2 --oneline</b>&nbsp;&nbsp;&nbsp; adding the number 2 will show you the last 2 recent commits<br
/><b>git diff </b>shows you all the changes that have occurred since last commit<br
/><b>&nbsp;&nbsp;&nbsp; git diff --staged</b>&nbsp;&nbsp;&nbsp; will show you the difference between the staged files and the last committed files<br
/><b>&nbsp;&nbsp;&nbsp; git diff HEAD~1 </b><i>filename</i>&nbsp;&nbsp;&nbsp; HEAD means the most recent commit, this is asking for the difference between the most recent commit and the version right before it (indicated by '1')<br
/><b>&nbsp;&nbsp;&nbsp; git diff</b> <i>id1 id2 filename</i>&nbsp;&nbsp;&nbsp; use shortened version (maybe about 6 characters) of the identifier that git gave to commits to compare any two older commits. It's good to indicate the filename or else will get the differences of all files within that commit<br
/><b>git reset HEAD</b> <i>filename</i>&nbsp;&nbsp;&nbsp; will unstage the specified file<br
/><b>git checkout HEAD</b> <i>filename</i>&nbsp;&nbsp;&nbsp; will bring you back a copy from the last commit<br
/><b>git remote add</b> <i>origin</i> <a href="https://github.com/yourgithub/yourrepo">https://github.com/yourgithub/yourrepo</a>&nbsp;&nbsp;&nbsp; to add the remote repository from github, using the link they gave when you made the new repository. Origin is the standard name, but could be anything.<br
/>&nbsp;&nbsp;&nbsp; <b>git remote -v</b>&nbsp;&nbsp;&nbsp; shows you the remote repositories that you have connected<br
/><b>git push</b> <i>origin</i> master&nbsp;&nbsp;&nbsp;&nbsp; pushes the master branch on your computer to the remote repository which is called origin<br
/><b>git pull </b><i>origin</i> master&nbsp;&nbsp;&nbsp; pulls any changes from the github version<br
/><b>git clone</b> <a href="https://github.com/githubname/githubrepo">https://github.com/githubname/githubrepo</a>&nbsp;&nbsp;&nbsp;&nbsp; clone (copy) someone else's entire repository on github onto your computer<br
/><br
/><u>Note:</u> If you make edits after you add a file to the staging area, git diff will show differences between the working file and the file in the staging area. git commit will still only commit the file(s) that has been added to the staging area.&nbsp;<br
/><br
/><b>Forking:</b> make a copy of somebody else's repository into your github so you can work with it and edit it for your own use<br
/><br
/><b>.gitignore file:</b> a list of files to ignore when making commits<br
/>&nbsp;&nbsp;&nbsp; 1. make a new file named .gitignore<br
/>&nbsp;&nbsp;&nbsp; 2. commit this file!&nbsp;<br
/><b>&nbsp;</b>&nbsp;&nbsp;&nbsp; <b>git status --ignored&nbsp; </b>shows you a list of ignored files<br
/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br
/><b>Linking the repository on your computer to github:</b><br
/>1. go to github, create a new repository&nbsp;<br
/>2. In shell (make sure you're in the repository):&nbsp;<br
/>&nbsp;&nbsp;&nbsp; git remote add origin <a href="https://github.com/yourgithub/yourrepo">https://github.com/yourgithub/yourrepo</a><br
/>&nbsp;&nbsp;&nbsp; git remote -v (shows you the remote repositories that you have connected)<br
/>&nbsp;&nbsp;&nbsp; git push origin master (pushes the master branch on your computer to "origin" the remote&nbsp; repo)<br
/>&nbsp;&nbsp;&nbsp;&nbsp;<br
/><b>Add Collaborators:</b><br
/>1. Go to the repository on Github<br
/>2. On the right hand panel click Settings&nbsp;<br
/>3. Click collaborators, search for person and add.<br
/><br
/><b>Clone somebody elses repo onto your computer:</b><br
/>git clone <a href="https://github.com/githubname/githubrepo">https://github.com/githubname/githubrepo</a><br
/><u>Note:</u> git pull will pull down latest updates and can only be done once you've established a connection with a remote repository, git clone will completely copy a remote repository to your machine<br
/><br
/><b>Working with git in RStudio:&nbsp;</b><br
/><br
/>Go to RStudio and open up the project you want to turn into a repo<br
/>1. In Rstudio: Tools &gt;&gt; Project Options &gt;&gt; Git/SVN and select git as your version control<br
/>2. In Rstudio: go to the Git tab next to environment and history tabs and select which files you want to add to the staging area&nbsp;<br
/>&nbsp;&nbsp;&nbsp; - use diff to see changes<br
/>&nbsp;&nbsp;&nbsp; - use commit button to commit items selected for staging area<br
/><br
/>Linking your rstudio version control with github:&nbsp;&nbsp;&nbsp;&nbsp;<br
/>1. In Github: make a new repository and copy the url link<br
/>2. In bash:&nbsp; cd to the local repository<br
/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; git remote add origin <a href="https://github.com/yourrepo">https://github.com/yourrepo</a><br
/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; git remote -v (to see that you've established a connection)<br
/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; git push -u origin master (pushes your repo in rstudio to the origin on github)<br
/>Now you can use the green and blue arrows to push and pull<br
/><br
/><br
/><br
/><b>Other learning resources</b><br
/>Try git: <a href="https://try.github.io/levels/1/challenges/1">https://try.github.io/levels/1/challenges/1</a><br
/>GitHub for Beginners: Don't Get Scared, Get Started: <a href="http://readwrite.com/2013/09/30/understanding-github-a-journey-for-beginners-part-1">http://readwrite.com/2013/09/30/understanding-github-a-journey-for-beginners-part-1</a><br
/><br
/><b>Questions</b><br
/><ul><li>Can I use git with Dropbox? <a href="http://stackoverflow.com/questions/1960799/using-git-and-dropbox-together-effectively">http://stackoverflow.com/questions/1960799/using-git-and-dropbox-together-effectively</a>&nbsp; LOTS of pros and cons here.</li
><li>Why is git always asking for my password?</li></ul
><a href="https://help.github.com/articles/why-is-git-always-asking-for-my-password/">https://help.github.com/articles/why-is-git-always-asking-for-my-password/</a><br
/><ul><li>I'm tired of entering my username and password. What can I do?&nbsp;&nbsp;&nbsp;<ul><li>Setting your username in git:</li></ul
></li></ul
><a href="https://help.github.com/articles/setting-your-username-in-git/">https://help.github.com/articles/setting-your-username-in-git/</a> (commits now show up under your username)<br
/>**You&nbsp; can do the above with your password BUT please note that your password&nbsp; will be stored in plaintext in your git config file.**<br
/><ul><li>Use a credential helper: <a href="https://help.github.com/articles/caching-your-github-password-in-git/">https://help.github.com/articles/caching-your-github-password-in-git/</a></li
><li>A more secure option is to use SSH<ul><li><a href="https://help.github.com/articles/generating-ssh-keys/">https://help.github.com/articles/generating-ssh-keys/</a></li
><li><a href="https://help.github.com/articles/which-remote-url-should-i-use/#cloning-with-ssh">https://help.github.com/articles/which-remote-url-should-i-use/#cloning-with-ssh</a><br/><br
/></li></ul
></li></ul
>============================================================<br
/><b>DAY 1: R &amp; Shell</b><br
/><br
/>Link to data for R exercises:<br
/><a href="https://dl.dropboxusercontent.com/u/98197254/data.zip">https://dl.dropboxusercontent.com/u/98197254/data.zip</a>&nbsp;<br
/><br
/><b>R</b><br
/>#rstats for help on twitter<br
/><br
/><b><u>R style notes:</u></b><br
/>&lt;- is more readable than =<br
/>include parameter names ie read.csv(file = "surveys.csv") instead of read.csv("surveys.csv")<br
/>functions don't require a return statement, but it improves readability<br
/><br
/><br
/><b>Getting Started:</b><br
/>File &gt; New Project to create a clean environment and new directory<br
/><br
/>Use `&lt;-` to assign values to objects, e.g.:<br
/>x &lt;- 5<br
/><br
/><b>To load data:&nbsp;</b><br
/>surveys &lt;- read.csv(file = "surveys.csv")<br
/>inflam2 &lt;- read.csv(file = "inflammation-02.csv", header = FALSE)<br
/>'read.csv' assumes that the file has a header line.&nbsp; If it does not include a header, use:<br
/>surveys &lt;- read.csv(file = "surveys.csv", header=FALSE)<br
/>Note: Header names should start with characters (preferred by R) rather than start with numbers.&nbsp;<br
/><br
/><b>To view data:</b><br
/>Double click on 'surveys' object in the environment window<br
/>head(surveys) will show you the first few lines of surveys<br
/><br
/><b>To learn more about data:</b><br
/>class(inflam2)<br
/>dim(inflam2) -- gives number of rows and columns<br
/><br
/><b>View a single cell:</b><br
/>inflam2[30, 2] (format is dataframe[row, column])<br
/><br
/><b>View a column:</b><br
/>inflam2[, 2]<br
/><br
/><b>View a range of rows and columns:</b><br
/>inflam2[1:4, 1:5]<br
/><br
/>Note: R indexing begins with 1, NOT 0.<br
/><br
/><b>Function 'apply'</b><br
/>Use apply function to repeat command over all rows or columns<br
/>- MARGIN specifies whether to repeat function over rows (1) or columns (2)<br
/>-much faster than a for loop<br
/>-can use to calculate things like mean, max, min, sd (standard deviation), i.e.:<br
/><br
/>#average<br
/>avg_day_inflam&lt;-apply(inflam2, MARGIN=2, mean)<br
/>plot(avg_day_inflam)&nbsp; #plots the results<br
/><br
/><br
/><b>For troubleshooting:</b><br
/>Type '?read.csv' This will open the help files/R documentation for this particular function ('read.csv').<br
/>To search for help with a function whose name you don't know: help.search("searchterm")<br
/>Stack overflow online is a good resource to use for looking up errors. (<a href="http://stackoverflow.com/">http://stackoverflow.com/</a> )<br
/><br
/><b>To read in all files that start with `inflam`:</b><br
/># list the file names of files that begin with `inflam` in the current directory<br
/>filenames &lt;- list.files(pattern = "^inflammation")<br
/># read in all the CSV files -- this puts them into a list called `files`, from which you could extract the individual data frames<br
/>files &lt;- lapply(filenames, read.csv, header = FALSE)<br
/># give each list element a name that corresponds to the file it came from<br
/>names(files) &lt;- filenames<br
/><br
/><b>Writing functions:</b><br
/><br
/>#defining simple function&nbsp;<br
/>fahr_to_kelvin&lt;-function(temp){<br
/>&nbsp; kelvin&lt;-((temp-32)*(5/9))+273.15<br
/>&nbsp; return(kelvin)<br
/>}<br
/><br
/>kelvin_to_c &lt;- function(temp) {<br
/>&nbsp; celsius &lt;- temp - 273.15<br
/>&nbsp; return(celsius)<br
/>}<br
/><br
/>#use the function<br
/>fahr_to_kelvin(7)<br
/><br
/>Notes:&nbsp;<br
/>-'temp' is the parameter taken in by the defined function, which returns 'kelvin'.<br
/>-While you don't need to return an object in your defined function, it is always good practice.<br
/>-The variable 'kelvin' ONLY exists inside the function.&nbsp; So it won't be a part of your work environment.<br
/><br
/><b>Vectors:</b><br
/>#vector of numbers<br
/>vec&lt;-c(1, 2, 3)<br
/><br
/>#vector of characters<br
/>vec&lt;-c("1", "2", "3")<br
/><br
/>Create a function that puts the vector `asterisk` at the beginning and end of the vector `best_practice`:<br
/><br
/>best_practice &lt;- c("Write", "programs", "for", "people", "not", "computers")<br
/>asterisk &lt;- "***"<br
/><br
/>fence &lt;- function(original, wrapper) {<br
/>&nbsp;&nbsp;&nbsp; result &lt;- c(wrapper, original, wrapper)<br
/>&nbsp;&nbsp;&nbsp; return(result)<br
/>}<br
/><br
/><br
/><b>For loops:</b><br
/>Basic structure:<br
/>for(variable in collection){<br
/>&nbsp;&nbsp;&nbsp; do something<br
/>&nbsp;&nbsp;&nbsp; }<br
/><br
/><i>Example:</i><br
/>length(best_practice) #this is the same as:<br
/><br
/>len&lt;-0<br
/>for(v in best_practice){<br
/>&nbsp; len&lt;- len+1<br
/>}<br
/>len<br
/><br
/><br
/><b>Regular expressions</b><br
/><br
/>To list all files that begin with inflammation and end in csv:<br
/>"^inflammation.+\\.csv$"<br
/>^ means "starts with"<br
/>.+ is the wildcard<br
/>\\. deals with the fact that the . is a special character<br
/>$ means that csv is the end<br
/><br
/>list.files(pattern=<br
/><br
/><b>Regular expression ("regex") resources:</b><br
/><ul><li>Concept map: <a href="http://teaching.software-carpentry.org/2014/04/30/concept-map-for-regular-expressions/">http://teaching.software-carpentry.org/2014/04/30/concept-map-for-regular-expressions/</a> (you can see why I was wrong about the * -- this will be relevant in the shell)</li
><li>Online tool to test regexes, includes cheatsheet and examples: <a href="http://www.regexr.com/">http://www.regexr.com/</a>&nbsp;</li
><li>Software carpentry materials on regexes: <a href="http://software-carpentry.org/v4/regexp/index.html">http://software-carpentry.org/v4/regexp/index.html</a>&nbsp;</li
><br/><br
/><br/></ul
><b>Shell basics</b><br
/><br
/>For apple users, you can find a comprehensive list of commands here: <a href="http://ss64.com/osx/">http://ss64.com/osx/</a><br
/>- also can use the command 'man', i.e., "man ls" will return the manual and the options for the 'ls' command. Typing 'q' will quit the manual. Additionally can use "info ls", which basically shows the same thing as "man ls".<br
/><br
/>For windows users use --help ie ls --help<br
/><br
/>DONT use spaces in filenames EVER<br
/>&nbsp;&nbsp;&nbsp; - but you can get around them with " "&nbsp; and an absolute pathname&nbsp;<br
/>&nbsp;&nbsp;&nbsp; - or by placing a '\' before the space<br
/><br
/><b>echo </b>spits back whatever statement you type in<br
/>&nbsp;&nbsp;&nbsp; - use single quotes to get around special characters<br
/>&nbsp;&nbsp;&nbsp;&nbsp;<br
/><b>pwd </b>"print working directory" shows you where you are<br
/><br
/><b>cd</b> "change directory" changes you to a different directory<br
/><br
/>to return to home directory:<br
/>cd ~<br
/>cd<br
/>cd /Users/yourname<br
/><br
/>To back up one directory:<br
/>cd ..&nbsp;&nbsp;<br
/>. current directory<br
/>. .&nbsp; parent directory<br
/><br
/><b>ls </b>lists contents in the given directory<br
/><b>&nbsp;&nbsp;&nbsp; ls -l </b>long form--&gt; gives permissions, owners, size, etc details of the files in the directory<br
/>&nbsp;&nbsp;&nbsp;<b> ls -lt </b>sorts files by time since last modified<br
/>&nbsp;&nbsp;&nbsp; ls -lh human readable sizes<br
/>&nbsp;&nbsp;&nbsp; <b>ls -S</b> sorts by file size<br
/>&nbsp;&nbsp;&nbsp; <b>ls -a</b> shows hidden files<br
/>&nbsp;&nbsp;&nbsp; <b>ls -F</b> outs slash after folders so you can more easily distinguish them from files<br
/>&nbsp;&nbsp;&nbsp;<b> ls -d */&nbsp;</b>&nbsp;&nbsp; will show only the directories in a folder<br
/>&nbsp;&nbsp;&nbsp;&nbsp;<br
/><br
/><b>Shortcuts:</b><br
/>Up arrow - will show recent commands used<br
/>Tab - will complete the filename or foldername you are currently writing (THIS ALSO WORKS IN R!! For the R console and scripts and inputting parameters, calling functions, variables, and other objects in your environment)<br
/>&nbsp;&nbsp;&nbsp; -If you hit tab twice, it will give you a list of files/folders that match what you've started typing<br
/><b>history</b>&nbsp;&nbsp;&nbsp; gives the whole list of commands that you've used<br
/>&nbsp;&nbsp;<b>&nbsp; !<i>NUMBER&nbsp;</i></b>&nbsp;&nbsp;&nbsp; will execute the command on line NUMBER, found in the history<br
/><br
/><b>Inspecting files:</b><br
/><b>file</b> <i>surveys.csv</i> gives you information on the file named surveys.csv<br
/><b>head </b>shows you the first 10 lines<br
/><b>tail </b>shows you the last 10 lines<br
/><b>wc</b> prints out the number of lines, number of words, number of bytes in the file<br
/>&nbsp;&nbsp;&nbsp; - if you just want number of lines you can do wc -l surveys.csv<br
/><b>less</b> <i>surveys.csv</i> let you go line by line<br
/><br
/><br
/><b>Manipulating files:</b><br
/><b>touch</b> <i>testfile</i>&nbsp;&nbsp;&nbsp; will make a new empty file called testfile<br
/><b>rm -i </b><i>testfile</i>&nbsp;&nbsp;&nbsp; will delete testfile, the '-i' is optional but good to use because it will double check you want this file deleted<br
/><b>nano</b><i> notes.txt</i>&nbsp;&nbsp;&nbsp; creates and opens editor to edit notes.txt<br
/><b>mkdir</b> <i>newdir</i>&nbsp;&nbsp;&nbsp;&nbsp; creates a new folder called newdir in current directory<br
/><b>cp</b> <i>file1 newdir/&nbsp;</i>&nbsp;&nbsp;&nbsp; will copy file1 to the directory called newdir/<br
/><b>mv</b> <i>file2 newdir2/</i>&nbsp;&nbsp;&nbsp; will move file2 to directory called newdir2/<br
/><b>mv</b><i> file3 file4</i>&nbsp;&nbsp;&nbsp; will rename file3 as file4<br
/><b>rmdir</b> <i>directory</i>&nbsp;&nbsp;&nbsp; will remove directory if directory is empty<br
/><b>rm -r</b> <i>directory</i>&nbsp;&nbsp;&nbsp; will remove directory and all its contents<br
/><br
/><b>Shell Regular expressions</b><br
/>*&nbsp;&nbsp;&nbsp; Asterisk is the wildcard, will match any character and any length of characters<br
/>?&nbsp;&nbsp;&nbsp; matches a single character<br
/><br
/><b>text editors:</b><br
/>nano<br
/>vim<br
/>emacs&nbsp;<br
/>notepad++<br
/>text wrangler, for macs<br
/>sublime<br
/><br
/><br
/><b>Data Management:</b><br
/><br
/>A Quick Guide to Organizing Computational Biology Projects by William Noble:<br
/><a href="http://www.ploscompbiol.org/article/info%3Adoi%2F10.1371%2Fjournal.pcbi.1000424#pcbi-1000424-g001">http://www.ploscompbiol.org/article/info%3Adoi%2F10.1371%2Fjournal.pcbi.1000424#pcbi-1000424-g001</a><br
/><br
/>Tips:<br
/>- Dont move or rename files because it makes it harder to reproduce results and track where things have gone<br
/>- version control is not ideal for data because you can't remove or compress old and obsolete data files<br
/>- One approach would be to keep the data file the same name but put new versions of it into folders which are sorted by date<br
/>- USE METADATA<br
/><ul><li>who is the data from</li
><li>when was it generated</li
><li>what were the experiment conditions</li></ul
>- Separate metadata file for each data file takes too long, so use a README file<br
/><br
/><br
/><b>Big Picture:</b><br
/>Project folder<br
/>-*src<br
/>&nbsp;&nbsp;&nbsp; -*scripts, source code, etc<br
/>-experiments<br
/>&nbsp;&nbsp;&nbsp; -yyyy-mm-dd<br
/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; -results from running scripts on data<br
/>-data<br
/>&nbsp;&nbsp;&nbsp; -*README<br
/>&nbsp;&nbsp;&nbsp; -yyyy-mm-dd<br
/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; -*README<br
/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; -data files<br
/>* indicates under version control<br
/>Readme files should include where from data generated and how.&nbsp;<br
/><br
/>Note: This isn't a one size fits all.&nbsp; For example, pipelines may need a different layout, possibly by dates of analysis.&nbsp;<br
/><br
/><br
/>Learn more about your bash profile: <a href="http://natelandau.com/my-mac-osx-bash_profile/">http://natelandau.com/my-mac-osx-bash_profile/</a><br
/>Dotfiles! <a href="http://code.tutsplus.com/tutorials/setting-up-a-mac-dev-machine-from-zero-to-hero-with-dotfiles--net-35449">http://code.tutsplus.com/tutorials/setting-up-a-mac-dev-machine-from-zero-to-hero-with-dotfiles--net-35449</a><br
/>Where do I put software that I compile myself? <a href="http://unix.stackexchange.com/questions/30/where-should-i-put-software-i-compile-myself">http://unix.stackexchange.com/questions/30/where-should-i-put-software-i-compile-myself</a><br
/><br
/>What's in my $PATH?&nbsp;<br
/>What's in my .bash_profile?<br
/><br
/>Type "man bash" to learn more!<br
/><ul><li>/bin/bash</li></ul
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The bash executable<br
/><ul><li>/etc/profile</li></ul
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The systemwide initialization file, executed for login shells<br
/><ul><li>~/.bash_profile</li></ul
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The personal initialization file, executed for login shells<br
/><ul><li>~/.bashrc</li></ul
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The individual per-interactive-shell startup file<br
/><ul><li>~/.bash_logout</li></ul
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The individual login shell cleanup file, executed when a login shell exits<br
/><ul><li>~/.inputrc</li></ul
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Individual readline initialization file<br
/><br
/><b>Simple .bash_profile example:</b><br
/>nano ~/.bash_profile&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; #This will create the file and open it for editing<br
/><br
/>Within this file you can use the '<b>alias</b>' command:<br
/>alias test = "cd ~/Desktop/mothur/abxD01"<br
/>This will create a shortcut command called "test", which when called in the terminal will automatically perform "cd ~/Desktop/mothur/abxD01".&nbsp;<br
/><br
/><b>Data management slides</b><br
/><a href="http://software-carpentry.org/v4/data/mgmt.html">http://software-carpentry.org/v4/data/mgmt.html</a><br
/><br
/><b>Data Analysis Networking Group (DANG)!</b><br
/>-to get on the email list, go to the mcommunity page, sign in, and add your name!<br
/><a href="https://mcommunity.umich.edu/#group:umich%20dang">https://mcommunity.umich.edu/#group:umich%20dang</a><br
/>-if this doesn't work, email me at aseekatz@umich.edu, and I will add you<br
/><br
/><br
/></body>
