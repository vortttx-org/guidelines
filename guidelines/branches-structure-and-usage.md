# Branches: Structure and Usage

Branches allow for parallel development without affecting the main codebase. At Vortx, we work with two primary environments: `master` (production) and `dev` (development/testing).

## Our Branches

**1. Master:**

- The `master` branch is our `production` branch. All code in `master` is considered stable, ready for deployment, and should never be touched;

**2. Dev:**

- The `dev` branch is our development environment. New features, bug fixes, and changes are tested here before merged into `master`;

**1. Feats or Fixes:**

- All new features or fixes are developed in individual branches created by the developer from the code on `dev` branch. Those branches follow a specific naming convention that will talk about later in this document;

## Creating Branches

When working on new features or fixing bugs, you should always create a new branch. This allows you to work independently of the main codebase until your changes are ready to be merged.

**1. From the Command Line / Terminal (_Recommended_):**

- Open the terminal and move into the repository folder:

```bash
cd /path/to/repository
```

- Always start from the `dev` branch before creating a new branch. So switch to the dev branch:

```bash
git checkout dev
```

- Always check if the your local `dev` branch is up-to-date with the origin `dev` branch:

```bash
git pull origin dev
```

- Use the following command to create and switch to a new branch:

```bash
git checkout -b feat/branch-name
```

- Replace `feat/branch-name` with a descriptive name following our naming guidelines;

**2. From GitHub Desktop:**

- Launch GitHub Desktop and open the repository you need to make changes;
- At the top of the GitHub Desktop window, you'll see a branch menu. Make sure you're on the `dev` branch;
- If not, click on the branch dropdown and select `dev`;
- Always check if the your local `dev` branch is up-to-date with the origin `dev` branch by clicking `Pull from Origin`;
- Click on the branch dropdown, then click `New Branch`;
- Name your branch, ensuring it follows our naming conventions;
- GitHub Desktop will automatically switch to the new branch;

## Branch Naming Conventions

At Vortx, we use `JIRA` to manage tasks, such as features, bugs, and other project-related activities. To maintain consistency and improve traceability, we name our branches based on the corresponding JIRA ticket IDs. This approach helps us easily track and locate specific pull requests related to a particular task, even when dealing with a large number of PRs.

Be sure to use this Branch naming strategy:

**1. Stories:**

```bash
feat/VRTXXX-YYYY-title-matching-jira-ticket-title
```

- Replace XXX with the `JIRA` project ID;
- Replace YYYY with the ticket number;

**1. Bugs:**

```bash
fix/VRTXXX-YYYY-title-matching-jira-ticket-title
```

- Replace XXX with the `JIRA` project ID;
- Replace YYYY with the ticket number;
