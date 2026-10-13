# DAY-01(GITHUB)
{#--> for main header)
Git-vcs(version control system to track changes in code)
git is a tool ,github is a website where you host all your git repositories
Commands:(note all commands are always in lower case)
cd: change directory
clone: repo available on github , u copy it and make it available on local computer
add: track your files and changes in git(bcoz we might delete or update stuffs).
commit: save your files in Git.
push: upload git commands to a remote repo like github
pull: download changes from remote repo to local machine, opposite of push

Basically README.md is a file that describes the entire project md--> means mark down(mark down is an easy way to format these texts)

colours in the github repo when viewing commits:
green-new changes(+)
red- removed part(-)
white-same as previous version

to check git version
git --version

In short, there are **3 main ways** to clone a GitHub repo:

1. **HTTPS** (`https://github.com/...`)
   *   Easiest to start, but asks for a username + token/password every time you push.
2. **SSH** (`git@github.com:...`)
   *   Requires setting up an SSH key once, but never asks for a password again. *(This is what you just set up!)*
3. **GitHub CLI** (`gh repo clone username/repo`)
   *   If you install GitHub's command-line tool, you can just type one short command and it handles login automatically.

*(There's also GitHub Desktop, but that's an app, not a terminal command.)*


cloning using SSH:
<img width="596" height="338" alt="image" src="https://github.com/user-attachments/assets/081f8a45-9267-472b-9cc6-3871469e7da4" />

GOT AN ERROR!

RESOLUTION : CREATE UR OWN SSH KEY:

<img width="380" height="281" alt="image" src="https://github.com/user-attachments/assets/9ca5d927-1a3d-4de8-a813-28c61900576d" />

ssh key: ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICxBlsTaE/auZ2AOlRUT2tYi7fzqOMC131KB5NyacnoI saimagnits@gmail.com

then:

<img width="640" height="318" alt="image" src="https://github.com/user-attachments/assets/fe7fc1ab-736c-4023-a2b3-e42a1d735ad8" />

<img width="448" height="301" alt="image" src="https://github.com/user-attachments/assets/150aa4e4-ada1-427b-8fe2-23cce6e0f74a" />

ls -Force command to see the hidden .git file

Why your ls output looks empty
When you typed ls, it showed a directory listing, but the Mode and LastWriteTime columns were cut off, and it looked like there was only one file with no name.

This is happening because the repository you cloned is empty except for a hidden folder.

Every Git repository has a hidden folder called .git. This folder contains all the history and tracking information for the project. But because it starts with a dot, Windows hides it by default.

How to see all files (including hidden ones) in PowerShell
To see the hidden files and folders in your new repo, type this command and press Enter:

powershell
ls -Force
(The -Force flag tells PowerShell to show hidden items).

You should now see a folder named .git.

git status-tells about the files tht have been updated,deleted ,etc but havent been committed

untracked means git doesnt know about the file yet

git add it will help git to track 
git add . command will tell git to track all files 
incase we want for partivular file then
git add filename

git commit -m "change u added" -m "description of the change u added"
here m stands for message 

till this point all changes are done locally, now we have to push the code to repo
git push origin main
now video covers ssh keys so alreay completed tht already(cozz for cloning ssh was required which she missed so she covered later)

we worked with an already existing git repo which we created initially on github

now lets do the same locally from start
git init to initialise a git repo
u do all the same steps make commits, track status , etc but when u push u come across this 

<img width="470" height="196" alt="image" src="https://github.com/user-attachments/assets/06dd3f13-33ba-42a5-898f-ab4ed6f8345c" />

BCOZ WE CREATED THIS REPO LOCALLY GIT HAS NO IDEA WHERE TO PUSH IT TO 
SO INORDER TO CREATE THT CONNECTION WE CAN CREATE AN EMPTY REPO:

ERRORRRRRRRRRRRRRRRRRRRRRRRRRRR!!!!!!!!!!!!!!
<img width="467" height="185" alt="image" src="https://github.com/user-attachments/assets/35121d26-088a-4066-9d4f-41aa0a1bf1e9" />

Start on GitHub: Default is main.

Start locally on your computer: Default is master (unless you changed the global setting I mentioned earlier).
since i strtd locally so im using master
wht if we want only ,aster or main , then in tht case simply juz rename the branchn

If you start on GitHub, it will **always** be `main` by default. GitHub hasn't used `master` as a default for years.

So yes, your understanding is correct:
*   **Start on GitHub:** Default is `main`.
*   **Start locally on your computer:** Default is `master` (unless you changed the global setting I mentioned earlier).

### So how do you avoid renaming all the time?

You have two options depending on which name you prefer:

**Option 1: You want everything to be `main` (Recommended)**
If you want to stop using `master` entirely, run this command **once** in your terminal:
```powershell
git config --global init.defaultBranch main
```
Now, every time you run `git init` locally, it will automatically create a `main` branch. No more renaming needed! You can just do `git push -u origin main` and it will match GitHub perfectly.

**Option 2: You want to keep using `master`**
If you prefer the old-school `master` name, you can't easily change GitHub's default when creating a repo on the website. But you can do this:
1. Create the repo on GitHub (it will make `main`).
2. Clone it to your computer.
3. Immediately run `git branch -M master` to rename it locally.
4. Then push with `git push -u origin master`.

**Honestly, Option 1 is the way to go.** Just set `main` as your global default and forget `master` ever existed. It will save you a lot of headaches!

<img width="470" height="194" alt="image" src="https://github.com/user-attachments/assets/2923b4b1-3478-403c-8328-5748f2d1d637" />


git remote add origin then the ssh part which u copy paste
refer the image

<img width="316" height="295" alt="image" src="https://github.com/user-attachments/assets/ba63f43e-4bcc-4fa4-9648-be7f64a92bef" />





COMINGGGGGGGGGGGG BACKKKKKKKKKKKKKKKKKKKKKK!
git push -u origin master(here u stands for upstream , use of this is basically to be able to juz ryt git push nd ur work shld be done , no need to write origin master and all)

<img width="399" height="359" alt="image" src="https://github.com/user-attachments/assets/1770bb5b-dff4-467f-9d9c-75eb338265dd" />


GIT BRANCHING 

<img width="281" height="163" alt="image" src="https://github.com/user-attachments/assets/b42d6ed1-13c0-409d-9ae0-f5551b879306" />

MASTER/MAIN BRANCH-THE ACTUAL MAIN BRANCH
FEATURE BRANCH- CHNAGES MADE HERE WONT EFFECT MAIN BRANCH UNTIL MERGED
HOT FIX BRANCH-USED TO FIX BUGS IN 1 COMMIT 


















