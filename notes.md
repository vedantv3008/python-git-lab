# Git + Python Practice Notes

This file documents all the steps, commands, errors, and learnings from the Git + Python practice session.

---

## 1. Repository Setup
- Created a GitHub repository: `python-git-lab`
- Cloned locally:
  
- powershell
    git clone git@github.com:vedantv3008/python-git-lab.git
    cd python-git-lab

## 2. Python Basics

- Created calculator.py with add(a, b):

    def add(a, b):
        print(f"{a} + {b} = {a + b}")

    if __name__ == "__main__":
        add(2, 3)


- Ran the script:

    py calculator.py


- Output:

    2 + 3 = 5

## 3. Branching & Pull Requests

-Created a new branch:

    git checkout -b feature/subtraction


- Added subtract(a, b) in calculator.py and committed.

- Pushed branch:

    git push -u origin feature/subtraction


- Opened Pull Request: feature/subtraction → main.

## 4. Stash & Multiplication

- Started writing multiply(a, b) and stashed unfinished work:

    git stash push -m "WIP: multiply"


- Listed stashes:

    git stash list


- Applied stash:

    git stash apply "stash@{0}"


- Completed multiply(a, b), committed, and pushed on branch feature/multiplication.

## 5. Revert & Reset

- Checked commit history for calculator.py:

    git log --oneline -- calculator.py


- Reverted the subtract commit:

    git revert 14669c5


- Made a mistake commit with print("oops").

- Removed it using:

    git reset --hard HEAD~1

## 6. Merge Conflict Practice

- Created two branches: feature/conflict-A and feature/conflict-B.

- Both added conflict.py with different content.

- Merged A first, then tried merging B → got conflict.

- Resolved conflict manually in conflict.py:

    print("Hello from A")
    print("Hello from B")


- Added, committed, and pushed.

## 7. Errors & Learnings

- Error: python not recognized.
- Fix: Used py calculator.py (Python launcher).

- Error: git stash apply stash@{0} failed in PowerShell.
- Fix: Used quotes:

    git stash apply "stash@{0}"


- Error: Tried git revert <commit-hash> literally.
- Fix: Must use actual commit hash, e.g.:

    git revert 14669c5
