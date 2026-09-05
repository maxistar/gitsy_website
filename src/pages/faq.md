---
layout: ../layouts/MarkdownLayout.astro
title: Frequently Asked Questions
---

## Getting Started

> What is GitSy?

GitSy is an Android app that synchronizes a folder you select on your device with an HTTPS or SSH Git repository. It works as a synchronization layer between that folder and a repository you control.

> Is GitSy a note editor?

No. GitSy synchronizes files, but it does not create or edit notes. Use another Android app that can open and edit files in the same selected folder.

> Which platforms are supported?

The GitSy app is available for Android 7.0 and newer. There is no GitSy app for iPhone, Windows, macOS, or Linux. On desktop systems, you can access the same repository with standard Git tools and edit its files with your preferred application.

> Can I synchronize files between Android and a desktop computer?

Yes. GitSy can synchronize the Android folder with a Git repository, and a desktop computer can clone and synchronize that repository using standard Git software. GitSy itself only runs on Android.

> Why must the selected folder be empty?

When you add a project, GitSy clones the repository and copies its contents into the selected folder. Requiring an empty folder avoids mixing unrelated local files with the initial clone.

## Repositories and Authentication

> Which Git services are supported?

GitSy supports HTTPS repositories with username/token authentication and SSH repositories with a private key. GitHub, GitLab, and compatible self-hosted Git servers are documented options. See the [repository setup documentation](/documentation/#repositories) for URL examples.

> Can I use an existing repository?

Yes. Enter its HTTPS or SSH clone URL and select an empty Android folder. GitSy clones the repository into its internal working copy and then copies the files to the selected folder.

> Does GitSy support SSH repository URLs?

Yes. In Settings, import one RSA or Ed25519 private key, then select SSH key authentication when you add a project. GitSy accepts SCP-like URLs such as <code>git@host:owner/repository.git</code> and canonical <code>ssh://</code> URLs. Confirm the displayed host fingerprint on the first connection; OAuth authentication is still planned. See the [repository setup documentation](/documentation/#authentication) for details.

> Why can I not use my GitHub or GitLab account password?

GitHub and GitLab require a personal access token for HTTPS Git operations. Enter your account name as the username and the token as the password. Follow the [GitHub guide](/docs/github/) or [GitLab guide](/docs/gitlab/) for provider-specific setup.

> Which permissions does my access token need?

The token needs permission to read and write the repository. Use the narrowest repository scope your provider offers, and revoke or replace the token if it is exposed.

> Should I use a private repository?

Yes, if the repository contains personal notes or other private files. GitSy works with public and private repositories, but the repository provider controls who can access them.

## Synchronization

> What happens when I synchronize a project?

GitSy copies changes from the selected Android folder to its internal Git working copy, commits local changes, pulls remote changes, pushes the synchronized state, and copies the result back to the selected folder.

> Is synchronization automatic?

You can manually synchronize one project or all projects. When GitSy opens, it may also queue ready projects according to your startup setting. In Settings you can optionally enable daily background synchronization and choose a local time (02:00 by default). Android runs scheduled work on a best-effort basis, so it may start later; a network connection is required. Each project gets at most one attempt per daily run, and errors that need authentication, SSH, or folder-access changes remain visible in GitSy for you to resolve.

> Can I edit files while offline?

Yes. You can edit files in the selected folder while offline. GitSy needs a network connection when you synchronize with the remote repository.

> Can I configure multiple folders or repositories?

Yes. Each GitSy project connects one selected Android folder to one Git repository. You can create multiple projects and synchronize them individually or together.

> Can several devices use the same repository?

Yes, but synchronize before and after editing the same files on another device. Concurrent changes to the same file can create Git conflicts.

> How does GitSy handle conflicts?

Conflict handling currently depends on Git/JGit behavior during synchronization. GitSy does not yet provide an interactive conflict-resolution interface. Keep another clone of the repository available when manual Git conflict resolution is required.

> What should I do if synchronization is interrupted?

Keep GitSy open while synchronization is running. If Android stops the app, GitSy may warn that the previous operation did not finish. Review the selected folder and remote repository before synchronizing again, especially if the same files were changed elsewhere.

## Files, Storage, and Privacy

> Which file types can GitSy synchronize?

GitSy synchronizes files and folders rather than a particular note format. Plain text and Markdown are common choices. Large binary files are subject to the normal limits and performance characteristics of Git and your repository provider.

> Where are my files stored?

Files are stored in the Android folder you select, in an app-managed Git working copy on the device, and in your remote Git repository after a successful push.

> Does GitSy upload my files to its own servers?

No. GitSy does not operate a hosted notes backend. Network transfers go to the Git repository that you configure. See the [Privacy Policy](/privacy/) for more details.

> Can GitSy access files from other apps?

GitSy can access the folder that you explicitly select through Android's system folder picker. It does not request access to every file on the device. Another app must also be able to work with that selected folder if you want to edit the files there.

> What happens when I delete a project from GitSy?

Deleting a project removes it from GitSy's configured project list. It does not delete the selected folder or the remote Git repository.

> How can I restore an older version of a file?

GitSy does not currently include a version-history interface. Use your Git provider or standard Git tools to inspect commits and restore an earlier revision.

## Troubleshooting

> Why does authentication fail?

For HTTPS, check the repository URL, username, token value, token expiration, and repository read/write permissions; account passwords normally do not work with GitHub or GitLab. For SSH, check that a supported private key is configured and that the repository URL and trusted host fingerprint are correct.

> Why do I see a cloning or synchronization error?

Check the network connection, repository URL, credentials, available device storage, and access to the selected folder. For a new project, also confirm that the selected folder is empty.

> Why are changes missing on another device?

Confirm that the first device completed synchronization and pushed its commit. Then synchronize or pull the repository on the other device. If both devices changed the same file, inspect the repository for a conflict.

> What information should I include in a bug report?

Include the GitSy version, Android version, Git provider, operation that failed, displayed error message, and whether the problem can be repeated. Do not include access tokens or private file contents. Use the [Contact page](/contact/) for support options.
