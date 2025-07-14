# 🔀 Git Branching & Merge Conflict Demonstration

This repository demonstrates how to:
- Create and work with Git branches
- Simulate a merge conflict
- Resolve merge conflicts manually
- Maintain a clean and traceable commit history

---

## 📁 Repository Structure

merging_branches_git/
├── README.md
├── file.txt ← File used to simulate conflict

yaml
Copy
Edit

 🛠️ Tools Used

- Git CLI
- VS Code
- GitHub
- Vim (used during merge conflict resolution)

---

## Steps Followed

step1 : Create the repository locally or in github

git clone repo<URL>
cd merging_branches_git
code .

 
 Step 2: Create a File and Make Initial Commit on main
echo "Line from main branch" > file.txt
git add file.txt
git commit -m "Add file.txt with main branch content"
 

Step 3: Create and Switch to a New Branch
git checkout -b feature-branch
Modify the same file:
echo "This line is from feature branch" > file.txt
git add file.txt
git commit -m "Update file.txt from feature branch"

 
 Step 4: Return to main and Make Conflicting Edit
git checkout main
Change file.txt again:


echo "This line is from main branch" > file.txt
git add file.txt
git commit -m "Conflicting change from main"


Step 5: Merge the Feature Branch
git merge feature-branch
This triggers a merge conflict in file.txt.

 Step 6: Resolve the Conflict
Open file.txt, and you’ll see:


<<<<<<< HEAD
This line is from main branch
=======
This line is from feature branch
>>>>>>> feature-branch
Manually edit it to:


Final merged version combining both main and feature changes.
Then:


git add file.txt
git commit
 Git opened Vim for the merge commit message. We saved and exited with:
:wq
 
 Step 7: Push Changes to GitHub
git push origin main
git push origin feature-branch

Result
Conflict was resolved successfully
Merge history preserved with proper commit messages
Repository pushed to GitHub
Visual Git Log (for clarity)

git log --oneline --graph --all

*   4a94558 (HEAD -> main) Merge branch 'feature-branch'
|\
| * c91a4fa (feature-branch) Update file.txt from feature branch
* | b9d7ef0 Conflicting change from main
|/
* b6106ff Initial commit


🏁 Conclusion
Git branching workflow
Safe conflict handling
Best practices for collaborative development

