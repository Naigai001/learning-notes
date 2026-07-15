# Vim Basics

Short notes for day-to-day editing.

## Modes

- `Esc` → Normal
- `i` / `a` / `o` → Insert
- `v` / `V` → Visual

## Motion

- `h j k l` — left / down / up / right
- `w` / `b` — next / previous word
- `0` / `^` / `$` — line start / first non-blank / end
- `gg` / `G` — file start / end
- `Ctrl-d` / `Ctrl-u` — half-page down / up

## Edit

- `x` delete char
- `dd` delete line
- `yy` yank line
- `p` paste after
- `u` undo
- `Ctrl-r` redo
- `.` repeat last change

## Search & replace

```vim
/pattern
n
N
:%s/old/new/g
:%s/old/new/gc
```

## Save & quit

```vim
:w
:q
:wq
:q!
```

## Tips

- Stay in Normal mode by default
- Prefer motions + operators (`d`, `c`, `y`) over pure Insert edits
- Use `*` to search the word under cursor
