#Visually a branching looks like:
![Screenshot](Screenshot%202026-05-03%20221445.png)


#Branch->an independent line of development
🔹 main -> stable, working code
🔹feature-login ->feature page made ,can be used for experimenting/actually making a PR

#Why is branching needed?
👉 Branching lets you:
Branching lets you work independently without breaking the main codebase.
🔹work safely
🔹avoid breaking main
🔹collaborate with others
🔹submit clean PRs

use->git branch

#Create a branch :
ex: git switch -c practice-branch


1️⃣ Check existing branches
git branch
👉 Shows local branches
* = current branch

git branch -a

👉 Shows all branches (local + remote)

2️⃣ Create a new branch
git branch feature-login (ex)

3️⃣ Switch to a branch
git checkout feature-login

OR (modern & recommended)

git switch feature-login

4️⃣ Create + switch (MOST USED)
git checkout -b feature-login

OR

git switch -c feature-login

5️⃣ Rename a branch
git branch -m new-name

Rename another branch:

git branch -m old-name new-name

6️⃣ Delete a branch
Safe delete
git branch -d feature-login

❌ Won’t delete if not merged

Force delete
git branch -D feature-login

⚠️ Deletes even if not merged

7️⃣ Merge a branch
git switch main
git merge feature-login

📌 Merges feature into main

8️⃣ Rebase a branch (clean history)
git switch feature-login
git rebase main

👉 Replays feature commits on top of main
⚠️ Use only on your own branch

9️⃣ See branch history (VERY HELPFUL)
git log --oneline --graph --all

Shows branch structure visually 🌳

🔟 Push a branch to remote (GitHub)
git push origin feature-login

First time push:

git push -u origin feature-login

(-u links local & remote branch)

1️⃣1️⃣ Delete remote branch
git push origin --delete feature-login

1️⃣2️⃣ Track a remote branch
git branch --set-upstream-to=origin/feature-login

1️⃣3️⃣ Checkout a remote branch
git checkout -b feature-login origin/feature-login

OR

git switch --track origin/feature-login

