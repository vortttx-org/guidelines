# Setup

Before you start contributing to projects, it’s essential to configure Git with your username and email address. These details are attached to your commits. If you’re going to use GitHub or other remote repositories, SSH keys allow secure authentication without needing to enter your credentials every time.

## Configuring Username and Email

**1. Set Your Username:**

- Open your terminal (or `Git Bash` on Windows) and enter the following command to set your Git username:

```bash
git config --global user.name "Your Name"
```

- Replace `Your Name` with your actual name. This name will appear in your commits;

**2. Set Your Email:**

- Similarly, set your email address with this command:

```bash
git config --global user.email "youremail@example.com"
```

- Make sure to use the same email linked to your GitHub account;

**3. Verify the Configuration:**

- You can check that your name and email have been set correctly with the following command:

```bash
git config --global --list
```

- This will display your current Git configuration, including the username and email;

## Generating and Configuring SSH Keys

SSH keys allow you to connect to a remote repository like GitHub securely. Here’s how to generate and configure your SSH keys:

**1. Check for existing SSH Keys:**

- Before generating a new SSH key, check if you already have one:

```bash
ls -al ~/.ssh
```

- If you see files like `id_rsa` and `id_rsa.pub`, it means you already have SSH Keys, and you can skip to step 4;

**2. Generate a New SSH Key:**

- If you don't have an existing key, generate a new one with this command:

```bash
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
```

- When prompted, you can press Enter to accept the default file location. You~ll also be asked to create a passphrase for added security.

**3. Add your SSH Key to the SSH Agent:**

- Start the SSH Agent:

```bash
eval "$(ssh-agent -s)"
```

- Add your SSH private key to the agent:

```bash
ssh-add ~/.ssh/id_rsa
```

**4. Add your SSH Key to your GitHub Account:**

- Copy the SSH Public Key to your clipboard:

```bash
cat ~/.ssh/id_rsa.pub
```

- Go to your GitHub account settings, find `SSH and GPG keys`, and paste the key there;

**5. Test Your SSH Connection:**

- To ensure everything is set up correctly, test your connection to GitHub:

```bash
ssh -T git@github.com
```

- If everything is configured properly, you'll see a message confirming the connection;
