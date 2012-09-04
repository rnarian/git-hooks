# Deploy Hook 

---

Copy *post-receive.deploy* to `yourrepo.git/hooks`.

Rename *post-receive.deploy* to *post-receive* and make it executable `chmod +x yourrepo.git/hooks/post-receive`

Edit $tree to match your working tree

---

In `yourrepo.git`:

    git config core.worktree /path/to/working-tree
    git config receive.denycurrentbranch ignore

