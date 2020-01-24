# GIT cheat sheet


## Table of Contents


* [GIT command syntax](#git-command-syntax)
* [GIT help](#git-help)
* [GIT configuration settings](#git-configuration-settings)
* [GIT create](#git-create)
* [GIT Add, Delete, Track changes](#git-add-delete-track-changes)
* [GIT diff files](#git-diff-files)
* [GIT visual diff files](#git-visual-diff-files)

<br/> <br/>


## GIT command syntax
<br/>

**git {git-options} {command} {command-options} {operands}**
<br/>

 <p align="center">
	<img src="static/images/git_command_notes.PNG">
 </p>	 

<br/> <br/>

 
## GIT help 
<br/>
 
**git help -a** <br/>
Display all available Git commands																		
<br/> <br/>

**git help -g** <br/>
Display all available Git guides
<br/> <br/>																	

**git help glossary** <br/>
Display the Git glossary																	
<br/> <br/>

**git {command}  -h**  <br/>
Display all options of {command} in Bash																		
Example:  git config -h 
<br/> <br/>
 

 
## GIT configuration settings
<br/>

**git config --global user.name "Your Name"** <br/>
Add your name to the global Git configuration                             														
<br/><br/>

	
**git config --global user.email "Your E-mail Address"** <br/>
Add your email address to the global Git configuration																		
<br/><br/>


**git config --global core.editor "'C:\Program Files\Notepad++\notepad++.exe' -multiInst -noSession -notabbar"** <br/>				
Configure GIT to use Notepad++ for edit 
<br/><br/>


**git config --global difftool.bc3.path "C:\Program Files\Beyond Compare 4\BCompare.exe"**  <br/>
To configure difftool path     									 
<br/><br/>


**git config --global diff.tool bc3**   <br/>
Tell to GIT to use bc3 as difftool for files comparsion																							
<br/><br/>


**git config --global difftool.prompt false**  <br/>
Tell to GIT don't prompt {yes or no} for each file comparsion
<br/><br/>

																					
**git config --list** <br/>																
Display all the Git configurations
<br/><br/>


**git config user.name**	<br/>														
Display the user.name configuration value
<br/><br/>


**git config user.email**		<br/>													
Display the user.email configuration value
<br/><br/>
 
 
## GIT create
<br/>

**git clone** https://github.com/rk-ramakrishna/git_learnings.git  <br/>
clone an existing remote repository
<br/><br/>

**git init** <br/>
Create a new local repository
<br/><br/>


## GIT Add, Delete, Track changes
<br/>

**git add {FILE}** <br/>
Start tracking {FILE} in Git; adds FILE to the staging area
<br/><br/>

**git add -f** <br/>
pick part of your changes to add to staging area
<br/><br/>

**git add .** 					<br/>													
To Add all changes in current & sub directory to staging area
<br/><br/>


**git rm --cached file** 			<br/>												
Remove file from staging area. Note: Removed file still avilable in working directory
<br/><br/>


**git rename file1 file2**			<br/>
Rename file1 to file2 in the staging area
<br/><br/>


**git status**						<br/>												
Display status of current working directory, as it relates to Git
<br/><br/>

**git status -s** 							<br/>										
Display status of files in short notation form. Short form notations are:  **?? - untracked  A - ADD   M - Modified**
<br/><br/>


**Note**

1. **Tracked files:**  <br/>
   Files which are known by GIT, means atleast it maintains single version of file 
   <br/><br/>
   
2. **UnTraced files:** <br/> 
   Files which are unknown to GIT, means no version of file exist in GIT
   <br/><br/>

3. GIT status command displays the tracked & untracked files
	<br/><br/>


**git status -b**  <br/>
Displays number of commits which are ahead of Head
<br/><br/>																				


**git commit -m "commit message"**					<br/>								
Commit changes to GIT repository with supplied log message  <br/>

**Note:** <br/> 
If you would like to provide more meaningful commit message, use git editor. 
<br/><br/>

**git commit -i <name of the file> -m "commit message"** <br/>
Commit only selected files
<br/><br/>

**git commit -am "commit message"** <br/>
Perform git add and then a git commit with supplied log message <br/>

**Note:**  <br/>
Above command only works for files which are already tracked by GIT. Above command would not work for files which are newly added in working directory and not staged.
<br/> <br/>

**git commit --amend -m "commit message"**    <br/>
Update the last commit in git repository with whatever content currently avilable in staging area. <br/> 
If no updates avilable in staging area, then only the commit message updated.

<br/>

**Note:** <br/>
It is not recommended to amend content that has already been pushed to a remote repository where others may be working with it. Operations that rewrite history such as amend 
ideally only be done in your local enviornment before content is initially pushed to the remote repository.
<br/><br/>



 
## GIT diff files
<br/>

**git diff**  <br/>
Show any changes between the tracked files in the current directory and the local repository
<br/><br/>

**git diff –staged** <br/>
Show any changes between the staging area and the repository
<br/><br/>

**Note:**

Git diff is a bit tricky. Comparsion of files typicllay based on below work flow <br/>

1. Git starts comparing file xxxx in working directory with file xxxx in staging area. <br/>
   If file xxxx not exist in staging area, then it compares xxxx file avilable in local repository. <br/><br/>
   
2. If user wants to compar file xxxx in staging area with xxxx in local repository, user should use command **git diff --staged xxxx**    <br/>
   Please make a note that, different versions of files in different levels. so while using diff command, you have to understand files and their levels. <br/><br/>

**git diff c344553  w3232323** <br/>
Shows difference between two commits <br/> <br/> 

**git diff c344553  w3232323 build.gradle**  <br/>
Shows difference between the file build.gradle of provided two snapshots  <br/><br/>

**git diff c344553 HEAD**  <br/>
Shows differences between snapshots c344553 and HEAD  <br/><br/>

**git diff c344553 master** <br/>
Shows differences between snapshots c344553 and latest commit in master       <br/><br/>


**git diff --name-only**															
Shows only names of the files that are different             <br/><br/>

**git diff --name-status**
Shows only names of the files that are different along with status  <br/><br/>


## GIT visual diff files
<br/>

git diff shows the differences in default format called **patch format.** <br/>
While you are focusing primarily command line usage,there are times when a visual interface adds significant value or convenience. <br/>
One of these cases is diffing.  To invoke the diffing tool, you run the command **git difftool**.   <br/>
Git comes preconfigured to be able to work with a number of different tools for diffing. To see a list of these tools, you can run the command **git difftool --tool-help**. <br/>

**Note:** <br/>

Use below commands to configure Beyond compare is default compare tool  <br/> 

**git config --global difftool.bc3.path "C:\Program Files\Beyond Compare 4\BCompare.exe"**     	<br/> 								
To configure difftool path    <br/> <br/> 

**git config --global diff.tool bc3**            <br/> 
Tell to GIT to use bc3 as difftool for files comparsion             <br/> <br/> 


