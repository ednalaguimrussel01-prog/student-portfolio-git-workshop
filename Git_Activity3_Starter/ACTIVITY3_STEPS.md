# Git Workshop Activity 3 – Step-by-step guide

## Before starting
This is a NEW sample project. If your instructor requires the exact Activity 1 project, use that project folder instead.

Open this folder in VS Code, then open Terminal > New Terminal.

## 1. Initialize the local repository (only if this folder is not already a Git repository)
```bash
git init
git add .
git commit -m "Initial student portfolio project"
git branch -M main
git status
git log --oneline
```

## 2. Create an empty GitHub repository
On GitHub, create a repository named `student-portfolio-git-workshop`.
Do NOT add a README, license, or .gitignore on GitHub. Copy its HTTPS URL.

## 3. Connect and push
Replace the URL below with your own repository URL:
```bash
git remote add origin https://github.com/YOUR-USERNAME/student-portfolio-git-workshop.git
git remote -v
git push -u origin main
```
If `origin` already exists, use `git remote set-url origin YOUR-REPOSITORY-URL` instead of adding it again.

## 4. Make a remote-only change
On GitHub, open `README.md`, click Edit, and add this sentence at the end:
`This repository demonstrates remote synchronization using GitHub.`
Commit directly to the `main` branch on GitHub.

## 5. Fetch and compare
Back in VS Code terminal:
```bash
git fetch origin
git log --oneline main
git log --oneline origin/main
git diff main..origin/main
```
The remote branch should show the GitHub README commit that is not yet in your local main branch.

## 6. Pull the remote change
```bash
git pull
git status
```
Open README.md and verify that the sentence added on GitHub is now present locally.

## 7. Create the feature branch
```bash
git switch -c feature-about
git branch
```

## 8. Add the feature on feature-about
Edit `index.html`. Add this section after the My Skills section and before `</main>`:
```html
<section class="card" id="about">
  <h2>About Me</h2>
  <p>I am a student learning web development and version control with Git and GitHub.</p>
</section>
```
Save, then review:
```bash
git status
git diff
```

## 9. Commit the feature
```bash
git add .
git commit -m "Add about feature"
git log --oneline --all --graph
```

## 10. Verify branch separation
```bash
git switch main
```
Open `index.html`: the About Me section should NOT be present.
Then:
```bash
git switch feature-about
```
Open `index.html`: the About Me section SHOULD be present.

## 11. Push the feature branch
```bash
git push -u origin feature-about
```
On GitHub, open the branch selector and verify that `feature-about` appears.

IMPORTANT: Do NOT merge the feature branch and do NOT create a Pull Request for this activity.

## Required submission
1. Your GitHub repository URL.
2. One PDF containing these four screenshots:
   - Evidence 1: GitHub account logged in with username visible.
   - Evidence 2: Terminal showing `git fetch origin` and comparison of `main` and `origin/main`.
   - Evidence 3: Terminal showing `git pull` and the local update.
   - Evidence 4: Show `index.html` on `feature-about` with About Me, then on `main` without About Me. You may capture both branch states in separate screenshots.

## Useful checks
```bash
git status
git branch -a
git remote -v
```
