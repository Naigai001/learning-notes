# SSH Basics

Quick notes for day-to-day SSH usage.

## Key pair

```bash
ssh-keygen -t ed25519 -C "you@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Copy public key:

```bash
pbcopy < ~/.ssh/id_ed25519.pub   # macOS
# or
cat ~/.ssh/id_ed25519.pub
```

## Config file

`~/.ssh/config`:

```
Host github
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes

Host box
  HostName 203.0.113.10
  User ubuntu
  Port 22
  IdentityFile ~/.ssh/id_ed25519
```

## Common commands

```bash
ssh box
ssh -L 8080:127.0.0.1:80 box
scp ./file box:/tmp/
rsync -avz ./dir box:/tmp/dir
```

## Security checklist

- Prefer `ed25519` keys
- Disable password login on servers after key auth works
- Keep private keys out of git repos
- Use `IdentitiesOnly yes` to avoid offering the wrong key
