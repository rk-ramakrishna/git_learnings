# GIT cheat sheet


## Table of Contents


* [GIT command syntax](#git_command_syntax)
* [GIT help](#git_help)
* [GIT configuration settings](#git_configuration_settings)




## GIT command syntax


git {git-options} {command} {command-options} {operands}


 <p align="center">
	<img src="static/images/git_command_notes.PNG">
 </p>	 



 
## GIT help 

 
git help -a
Display all available Git commands																		


git help -g
Display all available Git guides
																	

git help glossary
Display the Git glossary																	


git <<command>>  -h
Display all options of <<command>> in Bash																		
Example:  git config -h 

 

 
## GIT configuration settings


git config --global user.name "Your Name"
Add your name to the global Git configuration                             														


	
git config --global user.email "Your E-mail Address"
Add your email address to the global Git configuration																		



git config --global core.editor "'C:\Program Files\Notepad++\notepad++.exe' -multiInst -noSession -notabbar"				
Configure GIT to use Notepad++ for edit 



git config --global difftool.bc3.path "C:\Program Files\Beyond Compare 4\BCompare.exe"
To configure difftool path     									 



git config --global diff.tool bc3
Tell to GIT to use bc3 as difftool for files comparsion																							



git config --global difftool.prompt false
Tell to GIT don't prompt {yes or no} for each file comparsion


																					
git config --list 																
Display all the Git configurations



git config user.name															
Display the user.name configuration value



git config user.email															
Display the user.email configuration value

 