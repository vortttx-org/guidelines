# Commits, Pushs, Pull Requests & Merging

This section covers the essential steps of contributing to the codebase at Vortx, including making commits, pushing changes, creating pull requests, and handling merges. Following these guidelines ensures that the workflow is smooth, the code is well-organized, and collaboration between team members is efficient.

## Commit & Push

- Keep commits small and focused on a single change;
- Commit frequently to avoid large, hard-to-review commits;

**1. Follow the Process:**

- Always check for updates before making any changes. Ensure your local branch is up-to-date with the remote before starting any work:

```bash
git pull origin branch-name
```

- Also ensure your branch is up-to-date with the `dev` branch before starting any work:

```bash
git pull origin dev
```

- After working on the code, check the status of your local branch:

```bash
git status
```

- After making any code changes, stage them before commiting.

```bash
git add ./path/to/the/file/with/changes
```

- Commit your changes. Write clear and concise commit messages that describe exactly what was changed:

```bash
git commit -m "add feature to user authentication"
```

- Push the changes to the remote repository:

```bash
git push origin feat/branch-name
```

## Pull Requests

A Pull Request (PR) is a request to merge changes from one branch into another. It allows other team members to review and discuss the changes before they are incorporated into the main codebase.

**1. Create a PR on GitHub:**

- Push your local branch to GitHub using `git push`:

```bash
git push origin feat/branch-name
```

- Go to the repository on GitHub and click the `Compare & Pull Request` button that appears next to your branch;
- Fill in the title following the naming guidelines at the end of this document, and description, providing a brief explanation of what was done, the problem solved, and a link to the related `JIRA` ticket;

**2. Requesting Reviews and Adding Labels:**

- After opening the PR, request a review from the leads by using the `Reviewers` section;

### PR Naming Guideline

At Vortx, we use `JIRA` to manage tasks, such as features, bugs, and other project-related activities. To maintain consistency and improve traceability, similarly to Branch Naming Guidelines, we name our PRs based on the corresponding JIRA ticket IDs. This approach helps us easily track and locate specific pull requests related to a particular task, even when dealing with a large number of PRs.

Be sure to use this PR naming strategy:

**1. Stories:**

```bash
[VRTXXX-YYYY] title matching jira ticket title
```

- Replace XXX with the `JIRA` project ID;
- Replace YYYY with the ticket number;

**2. Bugs:**

```bash
[BUG][VRTXXX-YYYY] title matching jira ticket title
```

- Replace XXX with the `JIRA` project ID;
- Replace YYYY with the ticket number;

## Code Review

**1. How to Review PRs:**

- The person who made the changes cannot review their own PR;
- Use constructive comments, focusing on improving the code, not the individual;
- Check for logic errors, code clarity, and adherence to standards;

**2. Checklist for Reviewers:**

- Verify that it has all tests necessary and they all pass;
- Ensure the code is clear and easy to maintain;
- Check if the code adheres to the project's style guidelines;
- Ensure the code changes are in line with the `JIRA` ticket goal;
- Add labels at the end of the review for better control and traceability;

## Merge & Closing PRs

**1. Who is Authorized to Merge:**

- `Leads` are responsible for merging into the `dev` branch;
- `Admins` are responsible for merging into the `master` branch;
- `Developers` are not allowed to merge PRs;

**2. Merge Requirements:**

A PR will only be eligible for merging after:

- Two complete reviews from authorized team members;
- All `CI/CD` pipelines pass without errors or warnings;
- The changes meet all verification needs;
- Unit tests are complete and match at least the minimal coverage required;

**3. When to Delete Branches:**

- Simple, <ins>NEVER!</ins>

## Conflict Resolution

**1. Using GitHub Desktop (_Recommended_):**

- If a conflict occurs, GitHub Desktop will notify you during the merge process;
- Click the `Resolve Conflicts` button and manually resolve each conflict;
- Once resolved, commit the changes and proceed with the merge;

**2. Using Command Line / Terminal:**

- Fetch the latest changes:

```bash
git fetch origin
```

- Rebase or merge the conflicting branch:

```bash
git pull origin branch-name --rebase
```

- Manually resolve conflicts by editing the conflicting files;
- Once conflicts are resolved, stage the changes and continue the rebase:

```bash
git add -A
git rebase --continue
```

## Labels

When creating a PR, developers must assign appropriate labels following our label guideline via GitHub. These labels will be used to categorize the PRs. During code reviews, leads must also assign appropriate labels via GitHub to keep track of new changes, priority status, among other things.

**1. Admin / Leads Labels:**

Labels that should only be used by admins and leads.

- <ins>comments to address</ins>: Used when there are unresolved comments or feedback that need to be addressed.
- <ins>do not merge</ins>: Prevents the PR from being merged, usually due to outstanding issues.
- <ins>next to merge</ins>: This PR is next in line to be merged once it passes all checks.
- <ins>priority - low</ins>: The PR has low urgency and can be handled later.
- <ins>priority - medium</ins>: The PR has medium priority and should be addressed in due time.
- <ins>priority - high</ins>: The PR has high urgency and requires immediate attention.
- <ins>review complete</ins>: Indicates that the code review process has been completed and is ready for the next step.

**1. General Labels:**

Labels that should be used mostly by developers, but can be used by admins and leads if they see the need.

- <ins>bug</ins>: Indicates that the PR addresses a bug or issue in the code.
- <ins>build issues - failing tests/sonar checks</ins>: Marks PRs where tests or SonarQube checks are failing and need to be fixed.
- <ins>documentation</ins>: The PR relates to changes or updates in documentation.
- <ins>do not review</ins>: Signals that the PR is not ready for review yet.
- <ins>help wanted</ins>: Indicates that assistance is needed on the PR, either for resolving issues or adding functionality.
- <ins>merge conflicts</ins>: Highlights that the PR has conflicts with the base branch that must be resolved.
- <ins>needs review</ins>: The PR is ready for review and requires attention from reviewers.

## Tests & Code Quality

**1. Testing:**

- All new code must be covered by unit tests to ensure it's correct functionality;
- Tests will go through our `CI/CD` pipeline, so ensure your tests will pass before making a PR;

**2. Code Quality:**

- Every commit and PR will trigger the `CI/CD` pipeline, which includes tests and code quality checks. These checks ensure that the codebase remains stable and high-quality;
