# Contributing Guidelines

## Creating New Repositories

### 1. New Empty Repository (Starting from Scratch)
- **Steps on GitHub**:
  1. Click "New repository"
  2. Choose a descriptive name (e.g., `physics-simulator`)
  3. Select "Initialize this repository with a README"
  4. Add an appropriate `.gitignore` (e.g., Python, Unity, etc.)
  5. Choose a license (MIT recommended for educational projects)

- **Local Cloning**:
  ```bash
  git clone https://github.com/WCLN-Laboratory/repository-name.git
  cd repository-name

### 2. Repository with Existing Code
- **Steps**:
    1. Create an empty repository on GitHub (do not initialize README/.gitignore)
    2. Run locally:
        ```bash
        cd your-existing-project
        git init
        git remote add origin https://github.com/WCLN-Laboratory/repository-name.git
        git add .
        git commit -m "Initial commit: base project"
        git push -u origin main
        ```

## Contribution Workflow

### 1. Clone the repository (if not done before)
```bash
git clone https://github.com/your-username/repository-name.git
```

### 2. Syncing with upstream
```bash
git remote add upstream https://github.com/WCLN-Laboratory/repository-name.git
git fetch upstream
git merge upstream/main   # or upstream/develop if it exists
```

### 3. Creating a Branch

**Correct Base**:
- Use `main`/`master` if no `develop` branch exists (usually for small projects)
- Use `develop` if it exists (complex projects)

**Examples**:
- From terminal:
    ```bash
    git checkout -b feature/new-simulation          # New feature
    git checkout -b fix/energy-calculation-bug      # Bug fix
    ```

- In VSCode:
    1. Click the branch name at the bottom left
    2. Select "Create new branch"
    3. Enter a meaningful name (e.g., docs/update-manual)

### 4. Development and Commits
- Frequent commits with clear messages:
    ```bash
    git add modified-files.txt
    git commit -m "feat: added gravity simulation"
    git commit -m "fix: corrected unit measurement error"
    ```

- Best practices:
    - Atomic commits (one change per commit)
    - Use [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
      for messages:
        - `feat`: New feature
        - `fix`: Bug fix
        - `docs`: Documentation changes
        - `refactor`: Code refactoring without changing functionality

*Note: Alternatively you can use the VSCode extension to commit.*

### 5. Pushing Changes
```bash
git push -u origin branch-name
```

#### In VSCode:
1. Click the Source Control icon (⌃⇧G)
2. Enter commit message
3. Click "..." > Push


## Pull Requests (PR) and Merge
### 1. Creating a Pull Request
1. Go to the GitHub page of the repository
2. Click "Compare & pull request"
3. Fill out the template:
    - **Description**: What you did and why
    - **References**: Related issues (#123)
    - **Checklist**:
        - Tests performed
        - Documentation updated

#### Example of a Good PR:

```markdown
## Proposed Changes
- Added elastic collision simulation
- Optimized matrix calculations

## References
Resolves #45 (Base simulation request)

## Additional Notes
Dependencies need to be updated with `pip install -r requirements.txt`
```

### 2. Review and Merge
- **Only maintainers** can merge after approval
- **Do not self-merge** even if technically possible
- If requested, rebase the branch before merging:
```bash
git fetch upstream
git rebase upstream/main
git push -f
```

## Additional Best Practices
### Recommended Workflow
1. `git fetch --all` before starting work
2. Always work on dedicated branches
3. Pull frequently from upstream
4. Keep history clean with rebase instead of merge

### Useful Tools
1. **VSCode GitLens**: For viewing history
2. **Git Graph (VSCode Extension)**: For visual branch management
3. **GitHub Desktop**: Alternative for those who prefer GUI

### Conflict Resolution
1. Fetch the latest changes
2. Use:
    ```bash
    git mergetool   # Or resolve via VSCode editor (recommended)
    ```

3. Test thoroughly after resolution