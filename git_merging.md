What is merging?
Merging means combining changes from one branch into another branch.

Most commonly:
👉 merge a feature branch into main

Think like this:

main → stable code
feature-login → new work
Merge = bring feature changes into main
main      A──B──C
              \
feature         D──E

After merge:

main      A──B──C────F
              \    /
feature         D──E


Basic Merge Command
git switch main
git merge feature-login

📌 You always merge INTO the branch you are currently on

Types of Merges
1️⃣ Fast-forward merge (no conflict)

Happens when main has not changed

main      A──B
feature        C──D

Command:

git merge feature

Result:

main      A──B──C──D


2️⃣ 3-way merge (normal merge)

Happens when both branches changed

main      A──B──C
              \
feature         D

Result:

main      A──B──C──M
              \    /
feature         D

M = merge commit

Merge conflicts
A merge conflict happens when Git cannot decide which change to keep.

This usually happens when:

Same file
Same lines
Modified in both branches

What Git Shows During Conflict
<<<<<<< HEAD
Welcome to Git
=======
Welcome to GitHub
>>>>>>> feature-login  
Meaning:

HEAD → current branch (main)
======= → separator
feature-login → incoming changes
1️⃣ Open conflicted file

Decide what to keep:


2️⃣ Mark as resolved
git add filename.txt


3️⃣ Complete merge
git commit

✔ Conflict resolved
✔ Merge completed


❌ Abort a merge (if confused)
git merge --abort

Goes back to pre-merge state

📌 Best Practices to Avoid Conflicts

✅ Pull latest main before starting

git pull origin main

✅ Keep branches small
✅ Communicate with team
✅ Rebase before merge (carefully)

🆚 Merge vs Rebase (Quick)
Merge	Rebase
Keeps full history	Makes linear history
Safer for teams	Cleaner
Creates merge commit	No merge commit