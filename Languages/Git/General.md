- To find the user info:-  `git config --list`
- To change the username :-  `git config --global user.name <name>`
- For email:- `git config --global user.email <email>`


- To find help:-  `git help <verb>`

 - git init to start tracking the projec `rm -rf .git  to remove the .git file`

- To clone a repo from github:- `git clone <url> <file destination>`

- git status

- To add all the files in the tracking area:- `git add -A`
- To remove all the files from the staging area:- `git reset`
- To specifically remove one file:-  `git reset <filename>`

- To commit changes into the repo:- `git commit -m “message”`
- To check all the changes made :- `git log`

- Details of the repo:- `git remote -v`
			     					`git branch -a`

- `git diff` to show the changes made in the code.


- To finally push the repo to github:-
	- First pull the github repo:- `git pull origin main`
	- Next push it in:- `git push origin main.`

- To find the contents of remote url:-	`git remote -v`
- To find the contents of branches:- `git remote -vv`