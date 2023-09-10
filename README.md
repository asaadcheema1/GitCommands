# Git Commands and SSH Key Setup for Beginners

Welcome to the realm of Git and GitHub! This guide will take you through the creation of a GitHub account, setting up SSH keys, and essential Git commands.

## 1. Creating a GitHub Account

- **Navigate** to [GitHub's homepage](https://github.com/).
- **Click** on "Sign in/Sign up" at the top right corner.
- **Input** your preferred email and password.
- **Complete** the CAPTCHA verification.
- **Verify** your email address.
- Create a `ReadMe.md` file by clicking on 'create', naming it, and committing it. You can add a description or other text for demonstration purposes.

🎉 Cool! You now have a GitHub account.

## 2. Setting Up SSH Key for GitHub

### Generate SSH Key (RSA):
1. **Open** your terminal.
2. Generate a new RSA key with:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

### Configure SSH to Use the Key:
3. **Start the SSH agent** in the background:
    ```bash
    eval "$(ssh-agent -s)"
    ```

4. **Add your SSH private key** to the `ssh-agent`:
    ```bash
    ssh-add ~/.ssh/id_rsa
    ```

### Modify SSH Config:
5. **Edit or create the `config` file** in the `~/.ssh` directory:
    ```bash
    nano ~/.ssh/config
    ```

   Add these lines to the file:
   ```
   Host *
     AddKeysToAgent yes
     UseKeychain yes
     IdentityFile ~/.ssh/id_rsa
   ```

### Link SSH Key to GitHub:
6. **Copy** the SSH public key to your clipboard:
   ```bash
   pbcopy < ~/.ssh/id_rsa.pub
   ```

7. **Navigate** to GitHub and open "Settings".
8. Go to "SSH and GPG keys" > "New SSH key".
9. **Paste** your key, give it a descriptive title, and click "Add SSH key".

## 3. Cloning and Managing Your Repository

### Installing Git:
- **Mac/Linux**: Git often comes pre-installed. Verify with:
   ```bash
   git --version
   ```
- **Windows**: Download and install Git from [git-scm](https://git-scm.com/downloads). For guidance, refer to this [Atlassian tutorial](https://www.atlassian.com/git/tutorials/install-git).

### Cloning a Repository:
1. **Go** to your repository on GitHub.
2. Click "Clone" and **copy the SSH link**.
3. In your terminal or code editor's terminal, **clone** the repo:
   ```bash
   git clone <copied_repository_link>
   ```

## 4. Tracking and Updating with Git

### Add - Staging Your Changes:
1. **Navigate** to your cloned repository's directory:
    ```bash
    cd path_to_your_repository
    ```
2. **Stage** your changes:
    ```bash
    git add .
    ```

### Commit - Saving Changes Locally:
3. **Commit** your changes:
    ```bash
    git commit -m "Describe your changes here"
    ```

### Push - Updating Your GitHub Repository:
4. **Push** your committed changes:
    ```bash
    git push origin main
    ```

### Pull - Syncing Local Repository:
5. **Sync** your local repository with the remote one:
    ```bash
    git pull origin main
    ```

---

With these steps, you're prepared to embark on your Git and GitHub journey. Keep exploring, and happy coding!