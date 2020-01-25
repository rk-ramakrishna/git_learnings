# GIT cheat sheet


## Table of Contents


* [GIT command syntax](#git-command-syntax)
* [GIT help](#git-help)
* [GIT configuration settings](#git-configuration-settings)
* [GIT create](#git-create)
* [GIT Add, Delete, Track changes](#git-add-delete-track-changes)
* [GIT diff files](#git-diff-files)
* [GIT visual diff files](#git-visual-diff-files)
* [Find out History of snapshots](#find-out-history-of-snapshots)
* [Tags](#tags)

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


**git diff --name-only**	  <br/>														
Shows only names of the files that are different             <br/><br/>

**git diff --name-status**    <br/> 
Shows only names of the files that are different along with status  <br/><br/>


## GIT visual diff files
<br/>

* git diff shows the differences in default format called **patch format.** 

* While you are focusing primarily command line usage,there are times when a visual interface adds significant value or convenience. <br/>
  One of these cases is diffing.  To invoke the diffing tool, you run the command **git difftool**.   

* Git comes preconfigured to be able to work with a number of different tools for diffing. 

* To see a list of these tools, you can run the command **git difftool --tool-help**. <br/>

**Note:** <br/>

Use below commands to configure Beyond compare is default compare tool  <br/> 

**git config --global difftool.bc3.path "C:\Program Files\Beyond Compare 4\BCompare.exe"**     	<br/> 								
To configure difftool path    <br/> <br/> 

**git config --global diff.tool bc3**            <br/> 
Tell to GIT to use bc3 as difftool for files comparsion             <br/> <br/> 



## Find out History of snapshots
<br/>

**git log**   <br/>
Display the log (history) of the Git repository   <br/><br/>


**git log --stat**   <br/>
shows some statistics on the number of changes (the number of inserted lines, deleted lines, and so on)    <br/><br/>


**git log --stat --oneline** <br/>
Display the log with statitical information in one line <br/><br/>

**git log --parents**   <br/>
Display each log and associated parent log 			  <br/><br/>				

**git log --oneline src/main/resources/application.yml**     <br/>
Display log of provided file name		          <br/><br/>

**git log -n 3**           <br/>
Display logs of last 3 commits                <br/><br/>

**git log --oneline --decorate --graph --all**  <br/> 
Display logs in graphically way       <br/><br/>

**git rev-parse HEAD**           <br/>
Display the last commit of HEAD      <br/><br/>

**git rev-parse <<branch-name>>**			<br/>										
Display the last commit in branch				<br/><br/>

**Note:** git rev-parse and git show has lot of functionality like git log		<br/><br/>	

**git log -4 --oneline --name-only**   <br/>
Displays last 4 snapshots file names with information in single line   <br/><br/>	

**git log --since 30.12.2019 --until 01.01.2020**           <br/><br/>	

**git log --before 01.01.2020 --after 12.31.2019**          <br/><br/>	

**gitk**        <br/>
Display history visually. GIT log viewer			 <br/><br/>	

**git show --name--only 45893EQQ**     <br/>	
Display history visually. GIT log viewer			 <br/><br/>												

**git ls-files**             		<br/>
List the files in the repository           <br/><br/>


# Tags

<br/>

**Note:** <br/>

* Tag provides meaningful name to specific commit. For example, if you wanted to refer to a commit as 2.0x,use command: git tag 2.0x <SHA1 value>

* GIT provides two types of Tags
    * Light weight tags
    * Annotated tags 

* A lightweight tag is very much like a branch that doesn’t change. It’s just a pointer to a specific commit. Light weight tags are temparary tags
* Annotated tags contains all objects information like author, commit message etc. It is generally recommended to create & use the Annotated tags rather than light weight tags
<br/> <br/>

**git tag -a v2.4x -m "Tagging the changes of 2.4x"** <br/>
Creates new annotation type of tag with name "v2.4x"   <br/> <br/>

**git tag v2.5x** <br/> 																	
creates new light weight type of tag with name "v2.5x" <br/> <br/>

**git tag v2.5x v2.6x** <br/>
Rename lightweight tag v2.5x to v2.6x in local repository <br/> <br/>

**Note:** 
  * If tag v2.5x already exists in remote repository, then it is required to delete old tag v2.5x and push new tag v2.6x to remote repository
  * git tag -d v2.5x  
  * git push origin --delete v2.5x
  * git push origin v2.6x
  * Inform to other team members to refer newly created tag v2.6x  by executing the git command  **git pull --prune --tags**


**git tag -a v3.4x v2.4x^{}** <br/>
Rename annotation tag v2.4x to v3.4x  <br/>  <br/>

**Note:**
  * Note the syntax ^{} at the end of the command. For annotation tag this syntax is required. 
  * ^{} syntax enables to refer underlying commit[snapshot where old tag was created] instead of refering the old tag commit
  * Refer this thread to get more details https://stackoverflow.com/questions/49283734/why-isnt-my-tag-listed-when-i-checkout-with-git-gui/49286861#49286861  
  		 

**git tag -d <tag-name>**  <br/> 															
To delete the tag in local repository   <br/><br/>

**git tag --list**  <br/> 														
Listout all tags avilalbe in repository   <br/> <br/>

**git show v2.4x**  <br/>
Display the tag information   <br/> <br/>

**git push origin <tag-name>** <br/>
To push the newly created tag available in local repository to remote repository  <br/>  <br/>


**git push --tags**    <br/> 																
To push all newly created tags in local repository to remote repository  <br/> <br/>


**git push origin :refs/tags/<tag-name> or git push origin --delete <tag-name>** <br/>
To delete the remote repository tag   <br/><br/>														

**git fetch --prune origin "+refs/tags/*:refs/tags/*"**   <br/>
Remove tags in local repository which are nonexistent in remote repository  <br/> <br/>



