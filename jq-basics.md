# jq Basics

Quick JSON filtering notes for shell pipelines.

## Pretty print

```bash
curl -sS https://httpbin.org/json | jq .
cat data.json | jq .
```

## Select fields

```bash
# object field
jq '.name' user.json

# nested path
jq '.user.email' payload.json

# array items
jq '.[0].id' items.json
jq '.[] | .name' items.json
```

## Filters you will reuse

```bash
# keys only
jq 'keys' obj.json

# length
jq 'length' arr.json

# map / select
jq '[.[] | select(.active == true) | .id]' users.json

# rebuild object
jq '{id, name: .full_name}' user.json
```

## With curl

```bash
curl -sS https://api.github.com/repos/cli/cli | jq '{name, stars: .stargazers_count, lang: .language}'
```

## Checklist

- Prefer `jq -r` when you need raw strings without quotes
- Use single quotes around filters so the shell does not expand `$`
- Validate input is JSON before piping complex filters
