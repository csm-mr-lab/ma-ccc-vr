# CCC VR

A plain HTML static site, using Vite for local development and production builds.

## Local development

```sh
npm install
npm run dev
```

Open the local URL printed by Vite. Edit `index.html` to develop the page.

## 3D model assets

Put models and their textures in `public/assets/`. Reference them from the page
with paths such as `/assets/model.glb`. Vite copies this folder unchanged into
`dist/assets/` on build. Keep asset filenames and references consistent in case.
A model viewer is not included yet.

The assets folder starts empty. Git does not track empty folders; adding your
first asset will make the folder part of the repository.

## Build and preview

```sh
npm run build
npm run preview
```

The deployable static site is generated in `dist/`.

## GitHub account and repository

Before the first push, run these commands in Git Bash, replacing placeholders:

```sh
cd "/c/Users/sionf/Desktop/CCC VR"
git init -b main
git config --local credential.https://github.com.username YOUR_GITHUB_USERNAME
git config --local user.name "YOUR_NAME"
git config --local user.email "YOUR_GITHUB_COMMIT_EMAIL"
git credential-manager github login --username YOUR_GITHUB_USERNAME --force
```

Complete the sign-in using the intended GitHub account. The local credential
setting selects the account for this project without changing other projects.
The name and email settings control commit attribution, not authentication.
GitHub CLI (`gh`) has separate account settings; switching it alone may not
switch the account used by Git Credential Manager.

Create an empty GitHub repository under the intended account, then run:

```sh
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY.git
git add .
git commit -m "Set up static CCC VR site"
git push -u origin main
```

## Vercel

Import the new GitHub repository into the intended Vercel account/team.
Ensure Vercel's GitHub integration has access to that repository.
The checked-in `vercel.json` selects Vite, `npm run build`, and `dist`.
Keep the project root directory at the repository root.

GitHub authentication for pushing and Vercel's GitHub integration are separate.
This scaffold does not create a remote repository or deploy the site.
