# Git Internals

## Objects

- **blob** — file content
- **tree** — directory listing (blobs + subtrees)
- **commit** — snapshot pointer (tree + parent + metadata)
- **tag** — named reference to a commit

## Key commands

```bash
git cat-file -p HEAD       # inspect object
git hash-object -w file    # write a blob
git ls-tree HEAD           # list tree entries
```

## References

- `.git/HEAD` — current branch pointer
- `.git/refs/heads/` — branch tips
- `.git/objects/` — all objects (zlib compressed)
