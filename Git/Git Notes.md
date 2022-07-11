

#### Class 1 - 09-12-2019
### 1. What is the your reason for Devops ?

Update your Skill Set ..No 
Latest Trend ..We dont learn every Latest Trend

Ex : Change of Job / Getting Jobs

There are many sites in India for Booking Movie Tickets /Bus Tickets / Car Bookings

	Book My Show 
	Red Bus  / Abhi Bus 
	Ola / Uber

	Popular Bcz who has release first to the market 

Time to market to be reduced 
Increase business value by reducing costs by using ( Opensource or Free ) Alternatives 
Devops will be using Mostly or 99 % Opensource
Organisation can do effective devops using opensource and delivering app to market in short time 

	Devops can be used for any applications which has developed by any technology (Java/.Net/Mainframes/SAP/Andriod)
	Devops is not designed for one technology , Devops is designed bcz you can deploy any thing

Amazon/Flipkart/Facebook : Have u seen an updation message for delivery new features (DownTime)
Organisation : Will see message for DownTime
Intially Once we write the code , the code changes can be seen by customers (How much time it will take : Months/Days)
Now : Using Agile may be in Weeks 
Facebook : One Hour
Amazon : One and Hour 
Eventually Our Goal should be Zero Hours Time (one months -- Hours)

Not Possible for Health Care and Aeronatical Projects 
Restrictions to Devops : MRI SCANS / AUTO PILOT , Not Tested correctly 


### Devops Pipeline : 

		VCS : Version Control System(Source Server) (Code is ready and need to store in a place/Commit )
			
			GIT  
			
		Build /Packaging
		
			MAVEN
			MS BUILD
			DOCKER 

		System Testing
		
		Performance Testing

		User Acceptance Testing / Pre Production

		Production / Live
		
			For a tester (What will be easier to use Package or Url)
			
			We need to convert Build/Package to give URL : 
		
			For that , we need 
				Servers 
					Softwares
						Deploy the package

				Do we have server already ?

					No : Create Servers (Virtual Servers) /That could be Cloud or VMWare in Organisation
					
					To Create Servers :  we learn , Infra provisioning : (TERRAFORM / PACKERS)
					
					Using Terraform ,We can Create Servers in Azure , Servers in AWS , Servers in VMWare

					Server is Created and we have Opearting System (Windows / Linux / Mac)
						
					Yes : Configuration Management (ANSIBLE/CHEF/POWERSHELL DSC)
					
		For all phases we use  
		
			TERRAFORM
			ANSIBLE/CHEF/POWERSHELL
			KUBERNATES/OPENSHIFT
			
		Using Many Servers : Monitoring / Log (Changes will be in Monitoring)
		
		SITE RELIABILTY ENGINEERING ( Googles way of doing devops  : If a developer submits the code . how google do devops ?)

		Need to reduce time by using Automation by knowning all of the Phases of the devops pipeline

Manual /Automation : If we do same work again and again , human tendency will make mistakes but an machine(Applications) can't do mistakes 

	CI/CD Engines 
		
			Jenkins
			Azure Devops (VSTS)

#####################################################################################################################################
		
### DEVOPS :

	GIT
	MAVEN/MSBUILD/DOCKER
	TERRAFORM/PACKERS
	ANSIBLE/CHEF/POWERSHELL DSC
	KUBERNATES/OPENSHIFT/PCF 
	MONITORING 
	
### FOUNDATIONS : 
	
	LINUX 
		BASICS
		ADMINSTRATION
		SHELL SCRIPTING
	
	WINDOWS 
	    BASICS
		ADMINSTRATION
		POWERSHELL SCRIPTING
		POWERSHELL DSC
		
	SCRIPTING 
		PYTHON
		GROOVY(IN JENKINS)
		
	SERVERS 
		APACHE
		IIS
		TOMCAT
		KAFKA
		MYSQL
		

##############################################################################################################################

#### Class 2 - 10-12-2019

### Devops Journey Starts :
Our journey into CI/CD Pipelines as a DevOps Engineer starts when developer finishes coding of some feature and shares it with you

### Sharing Code to Others and Possible Approaches:

	#### Share the code via Email:
	Generally we have more that one developer working, then which version of whose mail should be consider

	#### Shared Folder:
	Looks like good option.
	All of your devteam once finished the code have to copy that in a shared location, 
	so which developers work to take is resolved by dev team
	Some developers work has caused lot of trouble in testing, so your lead wants to remove the work done by your dev team for that day

	#### General Opinion of sharing code:
	Multiple developers should be able to work in parallel
	Your code should have some kind of history/version

### Requirements for system to store code:

	We need some software to manage all of the above challenges
	Multiple users working parallelly on some code base
	Version/History Support
	Capability to maintain different copies of code base
	Have features like Backup/Restore and Archive

	Common Server/Application/System to store the code from muliple developers
	Version should be maintained for every change.
	Multiple users should be allowed to work on same files/code

Any system which satisfies above three points is a Version Control System (VCS)
		VCS:
			CVS : Concurrent Versions System
			VSS : Microsoft Visual SourceSafe
			SVN : SubVersioN 
			ClearCase
			Perforce
			Mercurial
			TFVC (Team Found Version Control)	
			GIT : GASTRO INTESTINAL TRACT
				
### Architectures of Version Control System :

Evolution in Version Control Systems

Generations of VCS

#### Client-Server Architecture:

	Client Server:
			Need a centralized Servers
			All the developers systems , will be clients
			For Disaster Recovery take a Secondary Setup
			Take Periodic Backups of VCS
			For all of this we need a VCS Administrator
			
			Two models:
			
			Connected: First Generation (Online Clients: For working server needs to connected all the time)
			Clients should be connected to servers all the time
			Administrators are required to take backups and also to replicate to multi-sites(Locations)
			Network connectivity issues could disrupt developers in doing the work
		
			Dis-Connected: Second Generation (Offline Clients: Clients can work and when they want to interact can establish a connection to server)
			Clients needed to be connected to servers only for getting the latest code or to submit work. 
			Clients can work in offline mode
			Administrators are required to take backups and also to replicate to multi-sites(Locations)

#### DevOps Engineers Misconceptions
Only Developer only will use git(VCS) a lot?
		Absolutely not, we as DevOps Engineers develop automation to pipeline and we use git to preserve our work
		Ansible/Chef/Terraform/K8s/Dockerfile which you have developed will be stored in Version Control System
		
		So DevOPs Engineers need to have two perspectives of VCS
		Developer
		Administrator

### Distributed Architecture:

	Whole copy of code is present on every node (client).
	Backup of the Code is one more node (Deamon)
	Other site(Location) is one more node(Deamon)

	No Need of Centralized Servers
	Any system can act as server
	Backup is just one more system having the code

#### In DVCS all the nodes
		will have the same version control software installed
		Will have the full copy of the code locally
		In DVCS we still use servers which is a node plus a Service to help other nodes get and submit the code

#### Advantage of DVCS over Client Server (Centralized Version Control Systems):
		No single point of failure
		All developers will send the changes made (changesets) and each changeset is version controlled rather than individual file, 
		so if some functionality is not working due to some developers mistake, its easy to revert back
		Developers can work in offline and only when they want to sync the code the need to be connected to the server
		Performance is much better
		Less Adminstration

#### Disadvantage:
		If your project is very huge, and every developer having a full copy can be extra cost on storage
		Are less performance when it comes to large binary files

#### Practical Enterprise Scenario :
You have a Project called as QT-Commerce for organization QT
We have developers who are working on coding and devops team which builds, packages and gives releases to testing team
Testing Team Uses the urls to test Application
To Host the code of QT-Commerce, 

Companies need
		A Server
		With GIt Installed
		Some Daemon/Service with https/ssh configured (Software)
		Periodic Backups have to be taken

### QT for Version control system has the following options

1.Can host the code in its own server managed by its admins
			Find a Software to install on your server to Maintain Git
			Gitolite
			GitHub Enterprise
			Git Lab
			others Refer Here : https://www.slant.co/topics/1440/~best-self-hosted-web-based-git-repository-managers

2.Go for companies which provide git server servcies
			Find a Provider who maintains Git Servers (Paying monthly bills)
			GitHub
			GitLab
			Bit Bucket
			Code Commit From AWS
			Azure Source Repos

3.Some of the Providers provide free services for opensource projects.


######################################################################################################################################

#### Class 3 - 11-12-2019

### Git Installation : 

Git is a Distributed Version Control System.

For the Developers, DevOPs team and testers, they have to
		Install git
		Get the account in Git Server and access rights to the code

#### How are we going to Learn git
		1.We learn how to use git locally
		2.We learn how to sync with servers
		3.Advanced Topics of git
		4.How git works?

### Installing Git

Windows: Download from here https://gitforwindows.org/
	
		Download software from here (https://gitforwindows.org/)
		Chocolatey:
		Install from here (https://chocolatey.org/install)
	
		****Go to windows
				Search Windows Powershell -- Right Click -- Run as Administrator
				Paste the above command -- click Enter
		
		From Windows Powershell :
		
		Copy this command to install Chocolatey
		
		    ****Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
			
			*****PS C:\Windows\system32> Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
			
			Getting latest version of the Chocolatey package for download.
			Getting Chocolatey from https://chocolatey.org/api/v2/package/chocolatey/0.10.15.
			Extracting C:\Users\91888\AppData\Local\Temp\chocolatey\chocInstall\chocolatey.zip to C:\Users\91888\AppData\Local\Temp\chocolatey\chocInstall...
			Installing chocolatey on this machine
			Creating ChocolateyInstall as an environment variable (targeting 'Machine')
			  Setting ChocolateyInstall to 'C:\ProgramData\chocolatey'
			WARNING: It's very likely you will need to close and reopen your shell
			  before you can use choco.
			Restricting write permissions to Administrators
			We are setting up the Chocolatey package repository.
			The packages themselves go to 'C:\ProgramData\chocolatey\lib'
			  (i.e. C:\ProgramData\chocolatey\lib\yourPackageName).
			A shim file for the command line goes to 'C:\ProgramData\chocolatey\bin'
			  and points to an executable in 'C:\ProgramData\chocolatey\lib\yourPackageName'.

			Creating Chocolatey folders if they do not already exist.

			WARNING: You can safely ignore errors related to missing log files when
			  upgrading from a version of Chocolatey less than 0.9.9.
			  'Batch file could not be found' is also safe to ignore.
			  'The system cannot find the file specified' - also safe.
			WARNING: Not setting tab completion: Profile file does not exist at
			'C:\Users\91888\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1'.
			Chocolatey (choco.exe) is now ready.
			You can call choco from anywhere, command line or powershell by typing choco.
			Run choco /? for a list of functions.
			You may need to shut down and restart powershell and/or consoles
			 first prior to using choco.
			Ensuring chocolatey commands are on the path
			Ensuring chocolatey.nupkg is in the lib folder
		
		To download Git from Chocolatey
		
			Open the Powershell and execute choco install git
			
			****PS C:\Windows\system32> choco install git 
			
			Chocolatey v0.10.15
			Installing the following packages:
			git
			By installing you accept licenses for the packages.
			git v2.24.1.2 already installed.
			 Use --force to reinstall, specify a version to install, or try upgrade.

			Chocolatey installed 0/1 packages.
			 See the log for details (C:\ProgramData\chocolatey\logs\chocolatey.log).

			Warnings:
			 - git - git v2.24.1.2 already installed.
			 Use --force to reinstall, specify a version to install, or try upgrade.
					 
Linux:
		Ubuntu: sudo apt-get update && sudo apt-get install git -y (APT Means : Advanced Packaging Tool)
		Redhat: sudo yum install git -y (YUM Means : Yellowdog Updater Modified)

MAC:
		If you have XCode, you already have git
		Use Homebrew https://brew.sh/
		brew install git

#### Exercise:
		Install Git as mentioned above
		Create a GitHub Account from here

#######################################################################################################################################

### Git Operations on Node (Local) :

Commands to Move forwards from Current Folder 

****PS C:\> cd Users                                                                                                        
****PS C:\Users> cd 91888                                                                                                   
****PS C:\Users\91888> cd LearningDevops                                                                                    
****PS C:\Users\91888\LearningDevops> cd LearningGit
****PS C:\Users\91888\LearningDevops\LearningGit>  


Commands to Move backwards from Current Folder 

****PS C:\Users\91888\LearningDevops\LearningGit> cd..                                                                      
****PS C:\Users\91888\LearningDevops> cd..                                                                                  
****PS C:\Users\91888> cd..                                                                                                 
****PS C:\Users> cd.. 
****PS C:\> 

Commands To Clear the PowerShell Screen : ****PS C:\Users\91888\LearningDevops\LearningGit> clear

Commands To exit the PowerShell Screen :  ****PS C:\Windows\system32> exit

Rename a file :  ****Rename-Item twp.txt two.txt


#### Understanding Git :

To understand Git, we need to understand 5 areas of git : Lets create a git Repository

Lets start from folder level
Create an empty directory

		Create a folder under C:\Users\91888\LearningDevops
		
		****mkdir LearningGit
		
		Change the directory 
		
		****cd LearningGit --> C:\Users\91888\LearningDevops\LearningGit
		
		Mark this folder into repository by executing "git init"
		
		****PS C:\Users\91888\LearningDevops\LearningGit> git init                                                                  
		Reinitialized existing Git repository in C:/Users/91888/LearningDevops/LearningGit/.git/
		
In Git we have 3 logical areas

		1.Working Tree /Working Directory
		2.Staging Area/Index Area
		3.Local Repository / Git Database

Local Repo Workflow

	Make changes in Working Tree                             (New-Item <filename> ,touch <filename>.txt, git status )
	Add the changes to Staging Area                          (git add <filename> , git add . , git status )
	Save the changes from Staging Area to Local Repo.        (git commit , git status  , git log)

### Lets try this WorkFlow

Create two file 1.txt and 2.txt
	
Commands to Create Files using "New-Item Command" (Powershell)
	
		****PS C:\Users\91888\LearningDevops\LearningGit> New-Item 1.txt   
		C:\Users\91888\gitlearning>cd.>file.txt                                                         

		Directory: C:\Users\91888\LearningDevops\LearningGit
 

		Mode                LastWriteTime         Length Name
		----                -------------         ------ ----
		-a----       13-12-2019     00:51              0 1.txt


		****PS C:\Users\91888\LearningDevops\LearningGit> New-Item 2.txt                                                            

		Directory: C:\Users\91888\LearningDevops\LearningGit


		Mode                LastWriteTime         Length Name
		----                -------------         ------ ----
		-a----       13-12-2019     00:51              0 2.txt

#### To know what is happening in git ?
		
	Execute the command "git status"
	
	****PS C:\Users\91888\LearningDevops\LearningGit> git status                                                                
	
	On branch master

	No commits yet

	Untracked files:
	  (use "git add <file>..." to include in what will be committed)
			One.txt
			Two.txt

	nothing added to commit but untracked files present (use "git add" to track)

#### What is Untracked File ????

	Untracked file is a new file which has no history in local repo. 
	
Now lets add the changes to staging area from working tree clean using "git add" command
	
	****git add 1.txt
	git status
	
	****git add 2.txt
	git status


Now lets try to commit the change from staging Area to Local Repo using "git commit" command

git commit

To do a commit requires 3 details
	
	Username
	Email
	Message
	
	Username and Email can be configured once at the system level, but message has to passed for every commit.
	
	To configure email and username
	git config --global user.name "<yourusername>"
	git config --global user.email "<youremailid>"
	To commit the changes now execute git commit -m "First Commit" 

****git commit -m "First Commit" 	
	
To check the history, execute the following command "git log"

For every change you get unique commit id as shown below "be556125d6ec6126574c3e1c9d31e6bf32414e4a"

	****PS C:\Users\91888\LearningDevops\LearningGit> git log
	commit be556125d6ec6126574c3e1c9d31e6bf32414e4a (HEAD -> master)
	Author: Suneel <Suneel.Kallur@gmail.com>
	Date:   Thu Dec 12 06:30:29 2019 +0530

		FIRST COMMIT

Learning some more commands		

		Create a new folder called as docs
		Create one more folder called as test

		****PS C:\Users\91888\LearningDevops\LearningGit> mkdir docs                                                                

			Directory: C:\Users\91888\LearningDevops\LearningGit


		Mode                LastWriteTime         Length Name
		----                -------------         ------ ----
		d-----       13-12-2019     01:26                docs


		****PS C:\Users\91888\LearningDevops\LearningGit> mkdir test


		Directory: C:\Users\91888\LearningDevops\LearningGit


		Mode                LastWriteTime         Length Name
		----                -------------         ------ ----
		d-----       13-12-2019     01:26                test

In the test folder create a new file called as 3.txt 

****PS C:\Users\91888\LearningDevops\LearningGit> New-Item test/3.txt


    Directory: C:\Users\91888\LearningDevops\LearningGit\test


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       13-12-2019     01:28              0 3.txt

Now Execute git status and you will observed docs folder information is not shown in git status. 
"Git never identifies empty directories".

****PS C:\Users\91888\LearningDevops\LearningGit> git status
	On branch master
	Untracked files:
	  (use "git add <file>..." to include in what will be committed)
			test/

nothing added to commit but untracked files present (use "git add" to track)

Now add the change to staging area "git add test/"
	****PS C:\Users\91888\LearningDevops\LearningGit> git add test/

Now execute the following commands and observe the ouptut info
	****git commit -m "Second Commit"

	[master 1deabfb] Second Commit
	 1 file changed, 0 insertions(+), 0 deletions(-)
	 create mode 100644 test/3.txt

	git status
	
****PS C:\Users\91888\LearningDevops\LearningGit> git status

	git log

****PS C:\Users\91888\LearningDevops\LearningGit> git log

	commit 1deabfb1ca0fc79498766c7761b9c2dc703ab248 (HEAD -> master)
	Author: Suneel <suneel.kallur@gmail.com>
	Date:   Fri Dec 13 01:33:22 2019 +0530

		Second Commit

	commit be556125d6ec6126574c3e1c9d31e6bf32414e4a
	Author: Suneel <Suneel.Kallur@gmail.com>
	Date:   Thu Dec 12 06:30:29 2019 +0530

		FIRST COMMIT

Popular Cheatsheets :
Git Hub : https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf
Atlassian : https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet

#################################################################################################################################

Untracked file and modified file :

Execute the following commands. 

	Open (Git-Bash or Linux/Mac Terminal) in particular folder where we wants to add or modify 

	Now iam using Desktop 

	91888@Suneel-Laptop MINGW64 ~/Desktop

	****touch 4.txt
	****echo "Hello" >> 1.txt

The above commands create a new file which is not in local repository and modifies a file which is already in local repository
Now Execute ****git status and the following output will be shown

On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        4.txt

no changes added to commit (use "git add" and/or "git commit -a")

### Terms:

### Untracked: 

Is a file which was never part of local-repository. 
Newly added files are generally untracked
Untracked file is a new file which has no history in local repo.

### Modified: 

Making changes to existing file in local repository
Modified file is existing file which has history in local repo.

### Color Significance :

Red => Working Tree
Green => Added to staging area

Add only modified file to staging area

	****git add --help : file:///C:/Program%20Files/Git/mingw64/share/doc/git-doc/git-add.html

	****git add -u 

	****git status

Now add the untracked file to staging area 

	****git add 4.txt

and commit the changes to local repo.

	****git commit -m "Third Commit"

	****git log

	****git status


Handling multiple Changes

Execute the following commands

	****touch docs/1.txt
	****touch docs/2.txt
	****touch test/5.txt
	****touch test/4.txt
	****touch 5.txt
	****touch 6.txt

91888@Suneel-Laptop MINGW64 ~/LearningDevops/LearningGit (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        docs/
        five.txt
        test/five.txt
        test/four.txt
        three.txt

nothing added to commit but untracked files present (use "git add" to track)

echo "hello" >> 2.txt
echo "hello" >> test/3.txt

If you want add all the changes at once to staging Area

****git status

****git add -A


# or if you are in top folder on git repo

****git add .


****git status

        new file:   docs/one.txt
        new file:   docs/two.txt
        new file:   five.txt
        new file:   test/five.txt
        new file:   test/four.txt
        modified:   test/three.txt
        new file:   three.txt
        modified:   two.txt

****git commit -m "Fourth Commit"


Ignoring some directories and files :

Execute the following commands

	****mkdir bin
	****touch bin\10.txt
	****touch 7.txt
	****echo "hello" >> 6.txt

We want everything in bin folder to be ignored. 

Now execute git status and the following o/p will be shown
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   6.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        7.txt
        bin/

no changes added to commit (use "git add" and/or "git commit -a")

	Git has a way to ignore certain files/foders. 

	For that create a file called as ".gitignore" in the repository root.

	****touch .gitignore

	Now add bin/* in the .gitignore file 

	and execute the following

	****git status # no bin/ information should be shown

On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   five.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        six.txt

no changes added to commit (use "git add" and/or "git commit -a")

http://gitignore.io/

git restore --staged bin/One.txt
git restore --staged bin/Two.txt

****git add .
****git commit -m "Fifth Commit"
****git status
****git log


Forward Commands

	New-Item
	Add
	Add.
	Commit


Backwards Commands
	Reset
	


Moving Changes from Staging Area to Working Tree

Reset command can help in doing this 

Execute the following command
****touch 8.txt
****touch 9.txt
****touch 10.txt
****echo "hello" >> 7.txt
****git status
****git add .
****git status

Now move 10.txt from staging area to working tree
****git reset 10.txt
****git status

Now if you want to remove all the changes in staging area and modified changes in working tree
****git reset --hard
****git status

To remove all the untracked files from working tree

****git clean -fd 

Removing files from local repo.

Execute the following command
****rm 7.txt
Execute the following commands
****git status
****git add .
****git commit -m "Sixth Commit"


You can also use git rm. https://www.atlassian.com/git/tutorials/undoing-changes/git-rm

git reset --soft ?


###################################################################################################################

Git History : 

	Every Change moved from staging Area to Local Repo is called as COMMIT.
	Every Commit has an ID
	using GIT you can move to any commit in history.

Lets Define HEAD : 

	HEAD is pointer which points to commit id working tree is looking at or pointing to .

Lets try to move the HEAD to Third commit. 
	For that you need commit id.
	Commit id which can be used are long and short

	****git log
	****git log --oneline

Now Lets move the HEAD to Third Commit
	****git checkout 7907137

Now to move the HEAD back to latest commit
	****git checkout master

Revert the modified changes in the Working Tree
	Make changes to 6.txt and add some content.

To revert the changes from the working tree on this file
	****git checkout -- 6.txt

Git Branches
	
The default branch of git is master

Now lets try to create some branches.
	****mkdir ecommerceapp
	****cd ecommerceapp
	****git init

Now lets create basic folder structure
	****mkdir src
	****mkdir test
	****mkdir docs
	****touch Readme.md
	****touch src/main.py
	****touch test/main.py
	****touch docs/main.md
	
Now commit these changes
	****git add -A
	****git commit -m "Initial Folder Structure Created"
	
Now this ecommerce application development is agile, 
We need create the branches for sprints. 

For now we need to create a branch called as sprint-1
	****git branch sprint-1
	****git branch 
	****git checkout sprint-1
	
To create a branch called sprint-1 and move the head to sprint-1
    ****git checkout -b sprint-1
	
Sprint-1 Developement has made some commits
	****echo "Sprint 1 Started" >> src/main.py
	****git add .
	****git commit -m " Feature 1 completed"
	****echo "Sprint 1 Started Testing" >> test/main.py
	****git add .
	****git commit -m "Feature 2 completed"
	****git log

Now checkout to master branch and then back to sprint-1
	****git checkout master
	****git checkout sprint-1

##############################################################################################################

Merge
	Merge is done when changes from one branch has to be brought to other branches.

Merges can be of two kinds

Fast-Forward:

	No Extra commit gets created
	When the Parent branch has no changes and if we try merging child to parent branch
	Can be skipped
	
Merge:

	Extra Commit with two parents will be created
	In all the other cases apart from Fast Forward Preview

 
Lets continue from previous repository created from here
	Merge the changes from sprint-1 to master.
	Note that there were no changes in master branch after sprint-1 branch was created, now merging will lead to fast forward

		Lets merge
				# move to the destination branch (master)
				git checkout master
				git merge sprint-1
				
		Create a branch called as sprint-2 from master
				git checkout -b sprint-2

		An Important fix from sprint-1 is done on master.
				git checkout master
				echo "Updated Docs of Sprint1" >> Readme.md
				git status
				git add .
				git commit -m "added imp fix"

		Continue working on sprint-2 branch

				git checkout sprint-2
				echo "sprint-2" >> src/main.py
				echo "sprint-2" >> test/main.py
				git status
				git add .
				git commit -m "features in sprint 2"
				
		Now try to merge the changes from sprint-2 to master
				git checkout master
				git merge sprint-2
		
		New commit gets created and HEAD & Master will be pointing to this new commit.

		Create a new branch called as sprint-3.

				git checkout master
				git branch sprint-3
				git checkout sprint-3
	
	
Rebase :

		Now add some changes for sprint-3 branch
		Now an important bug fix is done on master, which is required for sprint-3
		Now to rebase from master onto sprint-3, execute the following commands
		git checkout sprint-3
		git rebase master
		
References:

Rebase  https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase
Merge vs Rebase  https://www.atlassian.com/git/tutorials/merging-vs-rebasing


Merge-Conflict  :

Merge Conflicts can happen during

		merge
		rebase
		pull
		
		Lets create a child branch from master and call it as poc-qt

				git checkout master
				git checkout -b poc-qt
				
		Now add the following to src/main.py at the end
				working for qt

		Now master branch has one commit which changes in src/main.py.
		In master branch main.py has the following contents
				Sprint 1 Started
				SPrint-2
				testing is in progress
				need to add many comments

		In qt-poc branch main.py has the following contents
				Sprint 1 Started
				SPrint-2
				working for qt
		
		
Conflicts has to be resolved manually.


Viewing Differences
		To view differences, use git diff
		
		Try the following commands
		# make local changes on Working tree
		git diff
		git diff <commit-id-A> <commit-id-B>
		git diff <branch-A> <branch-B>

How is git Working
		Git is internally a very simple content tracker
		To understand this, lets create a new folder called as understanding-git
				mkdir understanding-git
				cd understanding-git
				git init
		Now lets get into .git folder and see the contents 
		lets make our first change
				mkdir src
				touch src/main.py
				git add .
				git commit -m "Commit-1"
				git log
		Now lets make other change
				mkdir test
				touch test/main.py
				git add .
				git commit -m "Commit-2"
				git log

To understand how git works , we need to understanding Hashing SHA1
Git Uses hashing (SHA-1) to calculate commit ids. Commit id is hash of many things.
				To understand contents of commit
				git cat-file -p <commit-id>
				Lets examine commit-2 contents Preview
				Take a look at below image Preview

#################################################################################################################################

Remote Repository

	Remote Repository is git on other node (generally) Preview
	Any node can host remote repositories. There are many softwares/platforms which can help us.

Softwares:
		Gitolite
		Git-Lab (Hosted)
		
Platforms
		GitHub
		BitBucket
		Code Commit (AWS)
		Azure Git Repos
		
Remote Repository Scenarios

	Create a Local Repo first and push the changes to Remote Repository
	Clone the Local Repo using Remote Repository Preview
	
Exercise on Remote Repository

		Create a Remote Repository for Local Repository (Ecommerce app)
		I will be using GitHub
		Created a new repo and got the url as https://github.com/GitPracticeRepo/ecommerceapp.git

		Push the changes from Local Repo to Remote Repo.
		Add this new url as your remote repository
		git remote add <name-of-remote> <url>
		git remote add origin https://github.com/GitPracticeRepo/ecommerceapp.git

		Push the changes to Remote Repository
		git push <name-of-the-remote> <branch-name>
		git push origin master

		Lets push other branches
		git push origin sprint-1
		git push origin sprint-2

		Clone a Local Repository from existing remote repository
		I will be using a Repository present at https://github.com/GitPracticeRepo/AnsibleSamples
		Clone a Local Repo from Remote Repo
		git clone <url>
		git clone https://github.com/GitPracticeRepo/AnsibleSamples.git

How the Remote is Handled

	Whenever a Remote Repo is added, new branches gets created in Local Repository. 
	<Remote-name>/<branch-name> will be the name for the remote branch.
	Sending the changes from local to Remote is Push
	Getting the latest changes from Remote to local is Pull (Fetch + Merge)

	Changing Hisory of commits
	
			Use Interactive Rebasing.

	Cherry-Pick
			To pick individual/sequence of commit(s) from one branch to other use cherry-pick
			
	Bare Repositories
			Git repositiries with only .git folders
			Generally used on servers and also used for taking backup
			git clone --bare <url>
			One local Git Repo with multiple Remote Repos
			git clone <url>
			# a remote called as origin gets created
			git remote add <other-repo-name> <other-repo-url>

Topics to be covered

		Git Communication Protocols
		Git Stash
		Git Tags
		Git Branching Strategy
		Git Reflog
		Git config
		Git Hooks/WebHooks
		
		
Exercises

		Demonstrate Fast-Forward
		Demonstrate Merge
		Demonstrate Rebase
		Remove 3 commits from histroy
		Combine 2 commits into one
		Get one commit from one branch to other
		Demonstrate Merge-Conflict


#####################################################################################################################


Using Git Bash

1.touch <Filename> / New-Item 
2.echo "Message" >> <Filename>
3.git status
4.git add
5.git add .
6.git add -A
7.git add --help
8.git -u
9.git commit -m "Commit Message"
10.git log
11.git restore --staged bin/One.txt
12.git reset :  git reset Four.txt
13.git reset --hard 
14.git clean -fd 
15.git rm -r 
16.git reset --soft
17.git reset --mixed


1.mkdir <dir name>
2.cd <dir name>
3.cd..
4.git init <To make folder into repository
5.New-item <filename>
6.git add <filename>
7.git add.
8.git status
9.git commit -m <Message>
10.git log
11.clear
12.exit

1 class Pending





		




















