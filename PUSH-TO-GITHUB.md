# Push this to your GitHub account

The git repository is already initialised with the first commit made, so you only
need to create the remote and push.

## Option A — one command (if you have the GitHub CLI)

```bash
cd gcp-pca-mock-exam
gh repo create gcp-pca-mock-exam --public --source=. --remote=origin --push
```

That creates the repo under your account and pushes `main` in a single step.

## Option B — without the GitHub CLI

1. Create an empty repo at <https://github.com/new>
   - Owner: **Fady120**
   - Name: **gcp-pca-mock-exam**
   - Visibility: **Public**
   - Do **not** tick "Add a README", "Add .gitignore" or "Choose a license" —
     this repo already has all three, and pre-adding them causes a push conflict.

2. Then:

```bash
cd gcp-pca-mock-exam
git remote add origin https://github.com/Fady120/gcp-pca-mock-exam.git
git push -u origin main
```

## Suggested repo description

> Offline practice exam for the current Google Cloud Professional Cloud Architect
> certification — 92 original questions, official domain weightings, 4 case studies,
> no backend.

## Suggested topics

`gcp` `google-cloud` `certification` `professional-cloud-architect` `practice-exam`
`exam-preparation` `pca`

## Optional — publish it as a live site

Because the app is plain static files, GitHub Pages will host it for free:

**Settings → Pages → Source: Deploy from a branch → Branch: `main`, folder: `/ (root)` → Save**

After a minute it will be live at
`https://fady120.github.io/gcp-pca-mock-exam/` — no local web server needed, and you
can practise from your phone.
