---
layout: ../../layouts/MarkdownLayout.astro
title: Creating a Private GitLab Repository and Setting Up HTTPS Access
---




## Creating a Private Repository

1. Go to [GitLab](https://gitlab.com) and sign in to your account
2. Click the "+" button in the top navigation bar and select "New project"
3. Enter your project name and description
4. Select "Private" under "Visibility Level"
5. Click "Create project"

## Setting Up HTTPS Access

1. Generate a Personal Access Token:
   - Click on your profile picture in the top right
   - Go to "Preferences"
   - In the left sidebar, click "Access Tokens"
   - Enter a name for the token (e.g., "HTTPS Access")
   - Select "read_repository" and "write_repository" scopes
   - Click "Create personal access token"
   - Copy the generated token immediately (you won't be able to see it again)

2. Using the token for HTTPS access:
   - When cloning or pushing to your repository, use this format:

   ```bash
   https://YOUR_USERNAME:YOUR_TOKEN@gitlab.com/YOUR_USERNAME/YOUR_PROJECT.git
   ```

   - Replace:
     - `YOUR_USERNAME` with your GitLab username
     - `YOUR_TOKEN` with your personal access token
     - `YOUR_PROJECT` with your project name

## Important Notes

- Keep your Personal Access Token secure and never share it
- The token has access to your repositories based on the scopes you selected
- You can revoke tokens at any time in your GitLab settings if needed
- Consider using a password manager to store your token securely
- GitLab tokens expire after 1 year by default

## Example Commands

- Clone a repository:

```bash
git clone https://YOUR_USERNAME:YOUR_TOKEN@gitlab.com/YOUR_USERNAME/YOUR_PROJECT.git
```

- Push to a repository:

```bash
git push https://YOUR_USERNAME:YOUR_TOKEN@gitlab.com/YOUR_USERNAME/YOUR_PROJECT.git
```
