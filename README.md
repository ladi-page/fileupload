# GitHub File Manager — GitHub Pages

## Install

1. Create a GitHub repository, for example `github-file-manager`.
2. Upload `index.html` to the repository root.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and `/ (root)`.
6. Save.
7. Open the Pages URL after GitHub publishes it.

## GitHub token

Create a **Fine-grained Personal Access Token**:
- Repository access: Only selected repositories
- Repository permission: Contents → Read and write

The dashboard asks for the token when you connect. It is not embedded in `index.html`, not placed in the URL, and not written to localStorage. It exists only in JavaScript memory while the page is open.

## Features

- Multiple repositories
- Repository add/remove
- Branch selection per repository
- Browse folders
- Open GitHub file
- Upload multiple files
- Replace existing files
- Delete files
- Drag/drop upload
- Commit message
- Session-only repository list
- No artificial application file-size limit

## Important file-size limitation

There is no artificial file-size setting in the dashboard, but GitHub's API, Git/Git LFS and repository limits still apply. A GitHub Pages app cannot make GitHub accept unlimited-size files.

## Security

Never put a PAT in this HTML source. Use a fine-grained token with access only to the repositories you need. Anyone who gets the token can perform the actions allowed by that token.

For a truly server-side hidden token and stronger admin authentication, a backend is required; GitHub Pages alone cannot provide that.
