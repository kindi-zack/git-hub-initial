# git-hub-initial

    First select your project & open your terminal in your project’s root directory.

1. Check for Git Version

git --version 

    If it is not showing the version of git then go to the official website of git and download the git according to OS of your system.

2. If we are setting up the git for the first time, we can configure the git with name & email.

git config --global user.name "Your_Name"
git config --global user.email "Your-Email"

3. Initialize Git Repository

git init

    Note:- On your Project’s root directory

    It initializes the git repository in local project & will make .git folder that contain important folders and files.

4. Commiting files into the git repo.

There are three steps :-

Step 1 : We need to add a file to staging area .

git add <File_Name>  {{For Single File}}
git add .            {{For all the files in current Directory}}

    Note :- In place of <File_Name> add your file and if you want select all the files in current directory then use {{ . }} or {{ * }}

    Staging area :- Staging area is that area where we can buy some items and put them in bucket .

To check,if files are added or not,use this:

git status

Step 2 : Commit a file into the git repo is to write a commit message.

    m = message

git commit -m "First Commit"

    Note :- In the “Double Quotes”, you should write your message.

Step 3 : Push the file into a remote repository. {{Github}}

    Now create your account on git-hub and create a repository .

    To add files in your remote repo use this :

git remote add origin git@github.com:"Username_on_github"/"Repository_Name"

    Note :- This above command is a single command & Now place your git-hub username (without any quotes) and put your repository name (without any quotes).

Like this

git remote add origin git@github.com:XYZ/project.git

    And if you don’t understand this then go to your repository on git-hub and click on clone or download button and copy url with SSH method.

To check

git remote -v

5. Create SSH Key.

    Why we use SSH?

    By using the ssh protocol, we can connect and authenticate to remote servers and services. With ssh keys we can connect to GitHub without supplying our username and password at each visit with the help of passphrase.
    In HTTPS method, you will need to fill our username and password at every visit, which will be very inconvenient.

    Git associates a remote URL with a name and our default remote is usually called “Origin”

1. Generating New ssh key and adding it to a ssh agent.

ssh-keygen -t rsa -b 4096 -C "email"

    Note :- Place your email in “double quotes”.

This creates a new ssh key using the provided email as a label.

1.1. For default file Press {{ ENTER }}

/home/{{username_of_pc}}/.ssh/id_rsa: ENTER

1.2. Enter a passphrase.

1.3. Now our identification has been saved in

Private Key : /home/{{username_of_pc}}/.ssh/id_rsa
& Public Key : .ssh/id_rsa.pub

2. Adding our ssh key to the ssh agent

eval "$(ssh-agent -s)"
it gives like {{agent_id : 15800}}

3. Now we add SSH Private key to ssh-agent to our default path.

ssh-add ~/.ssh/id_rsa

4. Adding a new ssh key to your github account.

    Copy the ssh key to our clipboard.

    Automatic Method (Using Xclip)

On Ubuntu
sudo apt-get install xclipon Manjaro
Open Octopi -> Download XclipXclip-set clip <~/.ssh/id_rsa.pub

2. Manual Method

Home/.ssh/id_rsa.pub
Open this file and copy your key.

    Now goto github.com ➢➢ Under Profile Photo (Drop Down) ➢➢ Settings ➢➢ Use SideBar {{ SSH & GPG Keys }} ➢➢ Then go to this directory on your computer {{Home/.ssh/id_rsa.pub}}
    Open this file and copy your key.

    Create new SSH key ➢➢ Title the filed with descriptive label ➢➢ Paste key into a “Key Field” ➢➢ Click on {{ Add SSH Key }}

5. Now for Testing SSH Connection.

ssh -T git@github.com

After running this , it will show this messege on terminal!!

Hi {{ USERNAME }}! You've successfully authenticated but github does not provide shell access.
