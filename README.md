# git-collaboration-demo
3) Git Branching, Merging and Remote Repository Collaboration
All commands in order (a to f)
Repository: git-collaboration-demo
GitHub username: SHAIKMEHANAZ
a. Create a GitHub repository and clone it locally
First, create git-collaboration-demo on GitHub with a README file.
git --version
mkdir devops
cd devops
git clone https://github.com/SHAIKMEHANAZ/git-collaboration-demo.git
cd git-collaboration-demo
git status
git branch
Create the initial file on main:
echo "welcome to git collaboration" > index.txt
git add index.txt
git commit -m "Add initial file"
git push origin main
b. Create a feature branch and switch to it
git checkout -b feature
git branch
c. Make changes in the feature branch and commit them
echo "welcome to feature branch" > index.txt
cat index.txt
git add index.txt
git commit -m "Updated feature branch"
d. Push the feature branch to the remote repository
git push -u origin feature
e. Switch to main, make a conflicting change and commit it
git checkout main
echo "welcome to main branch" > index.txt
cat index.txt
git add index.txt
git commit -m "Updated file in main branch"
f. Merge the feature branch and resolve the conflict manually
1. Merge feature into main:
git merge feature
Git should display a conflict in index.txt.
2. Open the file:
code index.txt
If VS Code is unavailable, open the file manually using Notepad.
You may see:
<<<<<<< HEAD
welcome to main branch
=======
welcome to feature branch
>>>>>>> feature
3. Remove the conflict markers and keep both lines:
welcome to main branch
welcome to feature branch
Save the file.
4. Add and commit the resolved file:
git add index.txt
git commit -m "Resolved merge conflict"
5. Push the final merged code:
git push origin main
6. Verify the final result:
git branch
git status
git log --oneline --graph --all
