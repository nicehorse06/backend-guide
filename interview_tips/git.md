## 🧭 Git

### 🧩 Keywords
- Repository (local / remote)
- Commit / Branch / Merge / Tag
- HEAD / Detached HEAD
- Working directory / Staging area (index)
- `.gitignore`
- SHA-1 commit hash
- Remote (origin / upstream)
- Rebase vs Merge
- Fast-forward vs Non-fast-forward
- Conflict resolution
- Stash / Cherry-pick / Revert / Reset
- Branching strategies: Git Flow, Trunk-based, Feature Branch
- Fork / Pull Request (PR) / Merge Request (MR)
- Git hooks / pre-commit hooks
- Submodules / Subtrees
- Git LFS (Large File Storage)
- Signed commits / GPG verification

---

### 💬 Common Interview Questions
- Explain how **Git works internally** (staging area, commit tree, SHA-1 hashes).  
- What is the difference between **merge** and **rebase**?  
- How do you undo a commit? (`revert` vs `reset`)  
- What happens in a **merge conflict**, and how do you resolve it?  
- What is a **detached HEAD state**, and how do you fix it?  
- What’s the difference between `git fetch` and `git pull`?  
- How do you delete a local or remote branch?  
- How do you recover a deleted commit? (`reflog`)  
- Explain the difference between **soft**, **mixed**, and **hard** reset.  
- When would you use `cherry-pick`?  
- How does **branch protection** work in team environments?  
- What’s the use of `.gitignore`?  
- How would you manage **binary files or large datasets** in Git?  
- How does **Git LFS** differ from normal Git tracking?  
- Describe a **feature branching workflow** vs **trunk-based development**.  
- How do you squash commits before merging a PR?  
- What is the difference between `git merge --squash` and `git rebase -i`?  

---

### ⚙️ Practical Insights
- **Git’s data model** is based on a *DAG (Directed Acyclic Graph)* of commits, each referencing parent commits.  
- A commit = snapshot of files + metadata (author, message, hash).  
- **Three states:**
  - Working Directory → modified files
  - Staging Area → `git add`
  - Repository → `git commit`
- **HEAD** points to the current branch or commit. Detached HEAD = working directly on a commit without a branch pointer.  
- **Branching & Merging**
  - `merge`: preserves history (creates merge commits)
  - `rebase`: rewrites history (linearizes commits)
  - Rebase is cleaner but avoid on shared branches.
- **Undo operations**
  - `git revert`: creates a new commit that undoes previous changes
  - `git reset`: moves branch pointer (dangerous if pushed)
  - `git reflog`: lifesaver for lost commits
- **Stash workflow**
  - Save uncommitted changes temporarily (`git stash push`)
  - Apply later (`git stash pop`)
- **Cherry-pick**
  - Apply a specific commit to another branch.
- **Reset types**
  - `--soft`: keep changes staged
  - `--mixed`: keep changes unstaged
  - `--hard`: discard changes entirely
- **Tagging**
  - Lightweight vs annotated tags (signed tags with GPG)
  - Useful for version releases.
- **Git LFS**
  - Stores large files outside Git; only references (pointers) kept in repo.
- **Hooks**
  - Automation scripts for actions like pre-commit checks, formatting, or enforcing policy.
- **Best Practices**
  - Write meaningful commit messages (imperative mood)
  - Keep commits small and logical
  - Regularly rebase feature branches on `main` or `develop`
  - Protect main branches; enforce code review via PR/MR

---

### 🚀 Advanced / Extended Topics
- **Rebase strategies**
  - Interactive rebase (`git rebase -i`) for squashing/fixing commits
  - `git pull --rebase` for cleaner history
- **Conflict resolution**
  - Understand conflict markers (`<<<<<<< HEAD`)
  - Use `git diff --merge` to analyze conflicts
- **Submodules**
  - Link external repositories inside your project
  - Keep pinned to specific commit SHA
- **Subtree merge**
  - Useful for importing external libraries into a monorepo
- **Reflog**
  - Tracks all movements of HEAD
  - Restore lost commits via `git reflog` + `git checkout <hash>`
- **Git Internals**
  - `.git/objects` stores compressed file snapshots
  - `git cat-file -p <hash>` inspects objects
  - Commit = Tree + Blob references
- **Automation**
  - Pre-commit hook → run `flake8` / `pytest` before commit
  - CI/CD integrations → auto-lint, test, deploy on PR
- **Large Repo Optimization**
  - Shallow clone (`--depth 1`)
  - Partial clone / sparse-checkout
  - Git garbage collection (`git gc`)
- **Security**
  - Signed commits for verification
  - Remove secrets using `git filter-repo` or `BFG Repo-Cleaner`

---

### ⚡ Quick Summary
> **Git is a distributed version control system using snapshots (commits) and hashes.**  
> Mastery means understanding staging, branches, merges, and history rewriting.  
> Use **merge** to preserve history, **rebase** for linear workflows, and **revert/reset** for recovery.  
> In teams, enforce branch protection and use clear commit messages.  
> Know how to debug with `reflog`, optimize large repos, and automate with hooks.
