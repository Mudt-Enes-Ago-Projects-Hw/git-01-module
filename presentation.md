# Git Project 01

Made By Enes, Nevval and Vesanja

---

## Step 1: Initial Project Setup


**Commands used (before screenshot):**
```bash
git init

git remote add origin https://github.com/Mudt-Enes-Ago-Projects-Hw/git-01-module.git

git branch -M main
```

![Initial Project Setup](images/Screenshot%202025-11-12%20at%2000.05.55.png)

**Commands shown in screenshot:**
```bash
git add README.md
git commit -m "chore: initial project setup with README file"
```

---

## Step 2: Add Application File

![Add Application File](images/Screenshot%202025-11-12%20at%2000.08.53.png)

**What happened:**
- Added `app.js` file to the project
- Committed the new file to main branch
- Commit: `418a24d - feat: add app.js file`

**Commands used:**
```bash
git add app.js
git commit -m "feat: add app.js file"
```

---

## Step 3: Update Documentation

![Update Documentation](images/Screenshot%202025-11-12%20at%2000.12.00.png)

**What happened:**
- Updated README.md with project description
- Added descriptive content about the project
- Commit: `355e776 - docs: add project description to README`

**Commands used:**
```bash
git add README.md
git commit -m "docs: add project description to README"
```

---

## Step 4: Modify Main Branch

![Modify Main Branch](images/Screenshot%202025-11-12%20at%2000.12.39.png)

**What happened:**
- Created `collide.txt` file with base content
- Modified it on the main branch
- This file will later cause merge conflicts
- Commit: `c1c5d99 - chore(main): modify collide.txt on main`

**Commands used:**
```bash
git add collide.txt
git commit -m "chore(main): modify collide.txt on main"
```

**Note:** This is the common ancestor for both feature branches that will be created next.

---

## Step 5: Create Feature A Branch

![Create Feature A Branch](images/Screenshot%202025-11-12%20at%2000.15.51.png)

**What happened:**
- Created and switched to `feature/a` branch
- This branch will develop Feature A independently

**Commands used:**
```bash
git checkout -b feature/a
# or
git branch feature/a
git checkout feature/a
```

---

## Step 6: Implement Feature A

![Implement Feature A](images/Screenshot%202025-11-12%20at%2000.16.07.png)

**What happened:**
- Added `featureA.js` and `featureA.txt` files
- Implemented Feature A functionality
- Commit: `acac12c - feat(feature/a): add featureA files and implementation`

**Commands used:**
```bash
git add featureA.js featureA.txt
git commit -m "feat(feature/a): add featureA files and implementation"
```

---

## Step 7: Document Feature A

![Document Feature A](images/Screenshot%202025-11-12%20at%2000.18.19.png)

**What happened:**
- Updated README.md to document Feature A work
- Added Feature A description
- Commit: `406fdf6 - docs(feature/a): document initial feature A work`

**Commands used:**
```bash
git add README.md
git commit -m "docs(feature/a): document initial feature A work"
```

---

## Step 8: Feature A Modifies collide.txt

![Feature A Modifies collide.txt](images/Screenshot%202025-11-12%20at%2000.20.41.png)

**What happened:**
- Modified `collide.txt` in feature/a branch
- Added "Feature A: change from feature/a" line
- This will cause a merge conflict later
- Commit: `7683659 - feat(feature/a): change collide.txt to add Feature A line`

**Commands used:**
```bash
git add collide.txt
git commit -m "feat(feature/a): change collide.txt to add Feature A line"
```

**Important:** At this point, feature/a has diverged from main with changes to the same file (collide.txt).

---

## Step 9: Create Feature B Branch

![Create Feature B Branch](images/Screenshot%202025-11-12%20at%2000.27.47.png)

**What happened:**
- Switched back to main branch
- Created and switched to `feature/b` branch
- This branch will develop Feature B independently

**Commands used:**
```bash
git checkout main
git checkout -b feature/b
```

---

## Step 10: Document Feature B

![Document Feature B](images/Screenshot%202025-11-12%20at%2000.31.05.png)

**What happened:**
- Updated README.md to document Feature B work
- Added Feature B description
- Commit: `60264c9 - docs(feature/b): document initial feature B work`

**Commands used:**
```bash
git add README.md
git commit -m "docs(feature/b): document initial feature B work"
```

---

## Step 11: Feature B Modifies collide.txt

![Feature B Modifies collide.txt](images/Screenshot%202025-11-12%20at%2000.31.38.png)

**What happened:**
- Modified `collide.txt` in feature/b branch
- Added "Feature B: change from feature/b" line
- This creates a three-way conflict scenario
- Commit: `12da99f - feat(feature/b): change collide.txt to add Feature B line`

**Commands used:**
```bash
git add collide.txt
git commit -m "feat(feature/b): change collide.txt to add Feature B line"
```

**Important:** Now we have three versions of collide.txt:
- Main branch: "Main: change from main branch"
- Feature A: "Feature A: change from feature/a"
- Feature B: "Feature B: change from feature/b"

---

## Step 12: Merge Feature A into Main

![Merge Feature A into Main](images/Screenshot%202025-11-12%20at%2000.32.25.png)

**What happened:**
- Switched to main branch
- Attempted to merge feature/a
- **MERGE CONFLICT** occurred in `collide.txt`
- Git detected conflicting changes to the same file

**Commands used:**
```bash
git checkout main
git merge feature/a
```

---

## Step 13: Resolve Feature A Merge Conflict

![Resolve Feature A Merge Conflict](images/Screenshot%202025-11-12%20at%2000.33.32.png)

**What happened:**
- Opened `collide.txt` to resolve conflicts
- Git marked the conflicts with `<<<<<<<`, `=======`, and `>>>>>>>`
- Manually edited the file to keep both changes
- Kept both "Main" and "Feature A" lines

**Conflict markers in collide.txt:**
```
Base content
<<<<<<< HEAD
Main: change from main branch
=======
Feature A: change from feature/a
>>>>>>> feature/a
```

**Resolved version:**
```
Base content
Main: change from main branch
Feature A: change from feature/a
```

**Commands used:**
```bash
# Edit collide.txt to resolve conflicts
git add collide.txt
git commit -m "fix: resolve merge conflict merging feature/a into main"
```

**Result:** Commit `1bd667f - fix: resolve merge conflict merging feature/a into main`

---

## Step 14: Merge Feature B into Main

![Merge Feature B into Main](images/Screenshot%202025-11-12%20at%2000.36.24.png)

**What happened:**
- Attempted to merge feature/b into main
- **ANOTHER MERGE CONFLICT** occurred in `collide.txt`
- This time, the conflict is between the merged result and feature/b

**Commands used:**
```bash
git merge feature/b
```

---

## Step 15: Resolve Feature B Merge Conflict

![Resolve Feature B Merge Conflict](images/Screenshot%202025-11-12%20at%2000.39.14.png)

**What happened:**
- Opened `collide.txt` again to resolve the second conflict
- Now the conflict is between main (with Feature A merged) and Feature B
- Manually edited to keep all three changes

**Conflict markers:**
```
Base content
<<<<<<< HEAD
Main: change from main branch
Feature A: change from feature/a
=======
Main: change from main branch
Feature B: change from feature/b
>>>>>>> feature/b
```

**Resolved version:**
```
Base content
Main: change from main branch
Feature A: change from feature/a
Feature B: change from feature/b
```

**Commands used:**
```bash
# Edit collide.txt to resolve conflicts
git add collide.txt
git commit -m "fix: resolve merge conflict merging feature/b into main"
```

**Result:** Commit `68709d1 - fix: resolve merge conflict merging feature/b into main`

---

## Step 16: Final README Update

![Final README Update](images/Screenshot%202025-11-12%20at%2000.40.55.png)

**What happened:**
- Made final updates to README.md
- Added comprehensive documentation about both features
- Commit: `429f37a - fix README`

**Commands used:**
```bash
git add README.md
git commit -m "fix README"
```

---

## Step 17: View Git History 

![View Git History](images/Screenshot%202025-11-12%20at%2000.41.26.png)

**What happened:**
- Used `git log` to view commit history
- Shows linear view of commits

**Commands used:**
```bash
git log --oneline --graph --decorate --all
```

---

## Step 18: Push to Github

![Push to Github](images/Screenshot%202025-11-12%20at%2000.41.57.png)

**Commands used:**
```bash
git push origin head
# or with more details
git push -u origin main
```

**Final Git Graph:**
```
* 429f37a (HEAD -> main, origin/main, origin/HEAD) fix README
*   68709d1 fix: resolve merge conflict merging feature/b into main
|\  
| * 12da99f (origin/feature/b, feature/b) feat(feature/b): change collide.txt to add Feature B line
| * 60264c9 docs(feature/b): document initial feature B work
* |   1bd667f fix: resolve merge conflict merging feature/a into main
|\ \  
| * | 7683659 (origin/feature/a, feature/a) feat(feature/a): change collide.txt to add Feature A line
| * | 406fdf6 docs(feature/a): document initial feature A work
| * | acac12c feat(feature/a): add featureA files and implementation
| |/  
* / c1c5d99 chore(main): modify collide.txt on main
|/  
* 355e776 docs: add project description to README
* 418a24d feat: add app.js file
* c52c514 chore: initial project setup with README file
```

---

## Usefull Git Commit Message types (Conventional Commit)  

```
type(scope): short description
```

- `feat`: → new feature

- `fix`: → bug fix

- `docs`: → documentation

- `style`: → formatting

- `refactor`: → refactoring code

- `test`: → adding tests