# Repositories & Branches

At Vortx, repositories are essential for organizing and managing our codebase. However, it’s important to follow specific guidelines when working with repositories and branches to ensure consistency, security, and smooth collaboration across the team.

### Quick Note!

**<ins>Only Admins can create repositories!</ins>**

To maintain structure and control over our codebase, only admins have permission to create new repositories. This ensures that all projects are well-organized and follow our development guidelines.

If you need a new repository for a specific project, please communicate with the admin to have it created.

## Creating Repositories

**1. Creating a Repository on GitHub:**

- Go to GitHub and sign in with your account;
- In the top-right corner, click the `+` and select `New Repository`;
- Fill in the following details:
  - <ins>Repository Name</ins>: Choose a clear, short, and descriptive name;
  - <ins>Description</ins>? Optionally, add a brief description of what the repository is for;
  - <ins>Privacy Settings</ins>: Always private at first;
  - <ins>Initialize with a README</ins>: Always check this option to start with a basic README file;
- Click `Create Repository`;

**2. Configure Repository Settings:**

- After the repository is created, go to the `Settings` tab;
- Set up branch protection rules to enforce pull requests and review policies;
- Ensure our main branches are created and properly configured;

## Cloning Repositories

Cloning a repository allows you to download a copy of a GitHub repository onto your local machine so you can work on the code. Here’s how to do it both via the command line and GitHub Desktop.

**1. From the Command Line / Terminal:**

- Go to the repository you want to clone on GitHub;
- Click the `Code` button, then copy the URL (either HTTPS or SSH, depending on your setup);
- Use the following command to navigate to the folder where you want to store the repository:

```bash
cd path/to/your/directory
```

- Use the `git clone` command followed by the repository URL:

```bash
git clone https://github.com/vortttx/repository-name.git
```

- This will download the entire repository into a folder on your local machine;

**1. From the GitHub Desktop (_Recommended_):**

- Launch GitHub Desktop on your machine;
- If you haven't signed in yet, go to `File -> Options` and sign in using your GitHub credentials;
- Go to `File -> Clone Repository` or click the `Clone a Repository` button on the main screen;
- In the window that opens, you can either select a repository from your GitHub account or paste the URL of the repository;
- Choose the local directory where you want to store the repository and click `Clone`;
