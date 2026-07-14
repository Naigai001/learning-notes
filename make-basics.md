# Make Basics

Short notes for everyday Makefile usage.

## Minimal Makefile

```makefile
.PHONY: help build test clean

help:
	@echo "make build | test | clean"

build:
	@echo "building..."

test:
	@echo "running tests..."

clean:
	@rm -rf dist build
```

## Patterns I use often

```makefile
SRC := $(wildcard src/*.py)
OUT := dist

$(OUT):
	mkdir -p $@

run: $(OUT)
	python3 main.py
```

## Tips

- Prefer `.PHONY` for non-file targets
- Keep targets small and composable
- Use `make -n` to dry-run
- Avoid putting secrets in Makefiles
