---
layout: ../../layouts/MarkdownLayout.astro
title: Creating a Private GitHub Repository and Setting Up HTTPS Access
---




## Creating a Private Repository

1. Go to [GitHub](https://github.com) and sign in to your account
2. Click the "+" icon in the top right corner and select "New repository"
3. In the repository name field, enter your desired repository name
4. Select "Private" under "Repository visibility"
5. Click the "Create repository" button

## Setting Up HTTPS Access

1. Generate a Personal Access Token (PAT):
   - Click on your profile picture in the top right
   - Go to "Settings"
   - In the sidebar, click "Developer settings"
   - Click "Personal access tokens" > "Tokens (classic)"
   - Click "Generate new token (classic)"
   - Give your token a descriptive name
   - Select "repo" scope under "Repository access"
   - Click "Generate token"
   - Copy the generated token immediately (you won't be able to see it again)

2. Using the token for HTTPS access:
   - When cloning or pushing to your repository, use this format:
   ```bash
   https://YOUR_USERNAME:YOUR_PAT@github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
   ```

   - Replace:
     - `YOUR_USERNAME` with your GitHub username
     - `YOUR_PAT` with your personal access token
     - `YOUR_REPOSITORY` with your repository name


## Important Notes

- Keep your Personal Access Token secure and never share it
- The token has full access to your repositories based on the scopes you selected
- You can revoke tokens at any time in your GitHub settings if needed
- Consider using a password manager to store your token securely

