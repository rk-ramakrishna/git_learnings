# GIT cheat sheet


## Table of Contents


* [GIT command syntax](#git_command_syntax)
* [GIT help](#git_help)
* [GIT configuration settings](#git_configuration_settings)

<br/> <br/><br/><br/>


## GIT command syntax
<br/> <br/>

git {git-options} {command} {command-options} {operands}


 <p align="center">
	<img src="static/images/git_command_notes.PNG">
 </p>	 

<br/> <br/><br/><br/>

 
## GIT help 
<br/> <br/>
 
git help -a <br/>
Display all available Git commands																		
<br/> <br/>

git help -g <br/>
Display all available Git guides
<br/> <br/>																	

git help glossary <br/>
Display the Git glossary																	
<br/> <br/>

git <<command>>  -h  <br/>
Display all options of <<command>> in Bash																		
Example:  git config -h 
<br/> <br/> <br/> <br/>
 

 
## GIT configuration settings


git config --global user.name "Your Name" <br/>
Add your name to the global Git configuration                             														
<br/><br/>

	
git config --global user.email "Your E-mail Address" <br/>
Add your email address to the global Git configuration																		
<br/><br/>


git config --global core.editor "'C:\Program Files\Notepad++\notepad++.exe' -multiInst -noSession -notabbar" <br/>				
Configure GIT to use Notepad++ for edit 
<br/><br/>


git config --global difftool.bc3.path "C:\Program Files\Beyond Compare 4\BCompare.exe"  <br/>
To configure difftool path     									 
<br/><br/>


git config --global diff.tool bc3   <br/>
Tell to GIT to use bc3 as difftool for files comparsion																							
<br/><br/>


git config --global difftool.prompt false  <br/>
Tell to GIT don't prompt {yes or no} for each file comparsion
<br/><br/>

																					
git config --list <br/>																
Display all the Git configurations
<br/><br/>


git config user.name	<br/>														
Display the user.name configuration value
<br/><br/>


git config user.email		<br/>													
Display the user.email configuration value
<br/><br/>
 