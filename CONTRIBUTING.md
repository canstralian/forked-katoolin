# Contributing to Forked Katoolin

Thank you for your interest in contributing to forked-katoolin! This guide will walk you through the GitHub Pull Request (PR) workflow for proposing, reviewing, and merging code changes.

## GitHub Pull Request Flow

The GitHub pull request flow is a collaborative process for proposing, reviewing, and merging code changes. It's part of the broader GitHub Flow, which uses branches to isolate work and PRs for discussion. This walkthrough assumes you're familiar with basic Git concepts.

### Prerequisites

- GitHub account and access to the repo (e.g., as owner or collaborator)
- Local Git setup:
  ```bash
  git clone https://github.com/canstralian/forked-katoolin.git
  ```
- Optionally, GitHub CLI (`gh`) or GitHub Desktop for easier management

### Step 1: Create a Branch

Branches keep changes isolated from the main branch (usually `main` or `master`).

**Via GitHub Web Interface:**
1. Go to https://github.com/canstralian/forked-katoolin
2. Click the branch dropdown and select "View all branches"
3. Click "New branch" and name it descriptively (e.g., `fix-install-script`)

**Via Command Line:**
```bash
git checkout main  # Ensure you're on the base branch
git pull origin main  # Sync with upstream
git checkout -b fix-install-script
git push origin fix-install-script
```

**Via VS Code:**
- Use the Git panel to create and switch branches

### Step 2: Make Changes

Edit files in your branch (e.g., modify `katoolin.py` for script improvements).

**Commit incrementally with clear messages:**
```bash
git add katoolin.py
git commit -m "Fix package installation loop in katoolin script"
git push origin fix-install-script
```

**If using VS Code:**
- Stage and commit via the Git panel

**Best Practices:**
- Aim for atomic commits (one logical change per commit)
- Write clear, descriptive commit messages
- Test your changes before committing

### Step 3: Create a Pull Request

**On GitHub:**
1. Go to the "Pull requests" tab
2. Click "New pull request"
3. Set base branch (e.g., `main`) and compare branch (e.g., `fix-install-script`)
4. Add a descriptive title (e.g., "Fix infinite loop in package installer")
5. Write a detailed description:
   - Explain what changes you made
   - Link to related issues (e.g., "Resolves #42")
   - Include testing steps if applicable
6. Mark as draft if not ready for review
7. Request reviewers and suggest labels (e.g., "bug fix", "enhancement")

**CI/CD Checks:**
- If CI/CD is configured (check "Actions" tab), ensure all checks pass
- Fix any failures by pushing updates to your branch

**For Fork Contributors:**
- If contributing to the upstream repository, create the PR on the original repo after forking

### Step 4: Review and Iterate

**During Review:**
- Reviewers will comment on the PR or specific lines
- Address feedback by making additional commits:
  ```bash
  git add .
  git commit -m "Add timeout handling per review feedback"
  git push
  ```
- Use GitHub's suggestion feature to apply changes directly
- Resolve conversation threads as issues are addressed
- Re-request reviews after making significant changes

**Tips:**
- Be responsive to feedback
- Ask questions if review comments are unclear
- Keep the discussion focused and professional

### Step 5: Merge the Pull Request

**When Ready to Merge:**
- Ensure all reviewers have approved
- Verify all CI/CD checks pass
- Choose merge strategy:
  - **Merge commit**: Preserves all commits (default)
  - **Squash and merge**: Combines all commits into one
  - **Rebase and merge**: Replays commits on base branch

**Resolving Merge Conflicts:**
```bash
git checkout fix-install-script
git pull origin main  # Merge base into your branch
# Edit conflicting files manually
git add .
git commit -m "Resolve merge conflicts with main"
git push
```

**Branch Protection Rules:**
- The repository may require:
  - Minimum number of approvals
  - Passing status checks
  - Up-to-date branches before merging
- Check Settings > Branches for current rules

### Step 6: Clean Up

**After Merging:**
- Delete the branch via GitHub's "Delete branch" button, or:
  ```bash
  git checkout main
  git pull origin main
  git branch -d fix-install-script
  git push origin --delete fix-install-script
  ```

**For Fork Maintainers:**
- Sync your fork with upstream periodically
- Keep your main branch up to date

## Code Quality Guidelines

When contributing to katoolin, please ensure:

1. **Python Code Style:**
   - Follow PEP 8 style guidelines
   - Use meaningful variable and function names
   - Add comments for complex logic

2. **Testing:**
   - Test on Ubuntu or compatible Linux distribution
   - Verify package installation works correctly
   - Test both individual tool installation and bulk installation

3. **Documentation:**
   - Update README.md if adding new features
   - Document any new command-line options
   - Update Changelog.txt with your changes

4. **Security:**
   - Be cautious with repository management
   - Validate user input
   - Sanitize all inputs to prevent command injection vulnerabilities.

## Getting Help

- **Questions?** Open an issue at https://github.com/canstralian/forked-katoolin/issues
- **Bugs?** Please include:
  - Your operating system and version
  - Python version
  - Steps to reproduce
  - Expected vs actual behavior

## Additional Resources

- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- [Git Documentation](https://git-scm.com/doc)

---

Thank you for contributing to forked-katoolin! Your efforts help make this tool better for the entire community.
