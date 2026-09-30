# GitHub Pages File Manager

A GitHub-only static file manager.

## What it does

- Runs entirely on GitHub Pages.
- Connects directly to GitHub's API from the browser.
- Supports multiple repositories.
- Browse folders.
- Upload/replace files.
- Delete files.
- Open files.
- Choose branch.
- No token is hard-coded into the site.
- Token is kept only in browser memory for the current session.

## Security

GitHub Pages cannot safely store a private GitHub PAT server-side. Therefore this app asks you to paste a fine-grained PAT when you open the dashboard. The token is NOT saved to localStorage, cookies, URL, or source code.

Use a fine-grained PAT with:
- Resource owner: your GitHub account
- Repository access: Only selected repositories
- Repository permissions: Contents = Read and write

Do NOT use an owner/admin token.

Anyone who obtains your PAT can use the permissions granted to it. Treat the token like a password.

## GitHub Pages setup

1. Create a private or public repository for this dashboard.
2. Upload the contents of `docs/` to the repository root, or keep the `docs` folder and configure Pages to use `/docs`.
3. Go to Settings -> Pages.
4. Source: Deploy from a branch.
5. Branch: `main`.
6. Folder: `/docs`.
7. Save.
8. Open the generated GitHub Pages URL.

## Use

1. Enter your GitHub username.
2. Paste your fine-grained PAT.
3. Click Connect.
4. Add repositories by owner/repository/branch.
5. Select a repository.
6. Browse and upload.

## File size

The app has no artificial JavaScript file-size setting.

However, GitHub API and GitHub repository limits still apply. The GitHub Contents API is not an unlimited large-file transport. For very large files, use Git LFS or another object-storage system.

## Important

This is a static GitHub Pages application. It cannot provide a hidden server-side GitHub token. If you need a true server-side secret and a login-protected admin panel, use a backend host such as Vercel/Cloudflare Workers/etc.
