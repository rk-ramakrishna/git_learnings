# GIT cheat sheet


## Table of Contents


* [GIT command syntax](#git-command-syntax)
* [GIT help](#git-help)
* [GIT configuration settings](#git-configuration-settings)
* [GIT create](#git-create)
* [GIT Add, Delete & Track changes](#git-add-delete-track-changes)

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


## GIT Add, Delete & Track changes
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

git status -s 							<br/>										
Display status of files in short notation form. Short form notations are:  **?? - untracked  A - ADD   M - Modified**


