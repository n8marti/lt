# Git Basics
### Preparations
1. Create GitHub account and add your local system's ssh key. Follow this [guide](https://wastalinux.org/home/customizing/github-setup/) from the wasta devs. (But don't worry about step 4, "Contact the Wasta-Linux team".)
1. Configure git on your system.
```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
1. Clone git repo to your system. See the first command given below.

### Git Command Examples
```bash
# Clone remote repo "lt" locally via ssh.
~$ git clone git@github.com:n8marti/lt.git
Cloning into 'lt'...
The authenticity of host 'github.com (140.82.121.4)' can\'t be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com,140.82.121.4' (RSA) to the list of known hosts.
remote: Enumerating objects: 28, done.
remote: Counting objects: 100% (28/28), done.
remote: Compressing objects: 100% (21/21), done.
remote: Total 28 (delta 12), reused 19 (delta 6), pack-reused 0
Receiving objects: 100% (28/28), 16.61 KiB | 27.00 KiB/s, done.
Resolving deltas: 100% (12/12), done.
~$

# Change directory into local repo root.
~$ cd lt
~/lt$

# Check local repo status.
~/lt$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
~/lt$

# Add a file, e.g.:
#   - create "GIT BASICS.md" and save to ~/lt
#   - open "GIT BASICS.md"
#   - add text
#   - save file

# A. Check local repo status to verify that a file has been created.
~/lt$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	GIT BASICS.md

nothing added to commit but untracked files present (use "git add" to track)
~/lt$

# or B. Check local repo status to verify that a file has been modified.
~/lt$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   GIT BASICS.md

no changes added to commit (use "git add" and/or "git commit -a")
~/lt$

# If a new file has been created or modified, add (or "stage") it in preparation for a commit.
~/lt$ git add "GIT BASICS.md"
~/lt$

# Check status to verify staging (new file added or existing file modified).
~/lt$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   GIT BASICS.md

~/lt$

# Commit changes to make them "official" in the local repo.
~/lt$ git commit -m "added GIT BASICS.md"
[main 2d693bf] added GIT BASICS.md
 1 file changed, 52 insertions(+)
 create mode 100644 GIT BASICS.md
~/lt$

# Check status to verify commit.
~/lt$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

~/lt$

# Periodically "push" the changes in your local repo up to the remote (online) repo.
~/lt$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 689 bytes | 689.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:n8marti/lt.git
   3c2037d..a806604  main -> main
~/lt$
```
