# curl Basics

Everyday HTTP debugging with curl.

## GET request

```bash
curl -i https://example.com
curl -sS https://httpbin.org/get | python3 -m json.tool
```

## Headers and methods

```bash
curl -X POST https://httpbin.org/post \
  -H "Content-Type: application/json" \
  -d '{"hello":"world"}'

curl -I https://example.com   # headers only
```

## Timing and failures

```bash
curl -o /dev/null -sS -w "http=%{http_code} time=%{time_total}\n" https://example.com
curl --fail --retry 2 --max-time 10 https://example.com/health
```

## Useful flags

| Flag | Meaning |
|------|---------|
| `-sS` | silent but show errors |
| `-L` | follow redirects |
| `-v` | verbose request/response |
| `-k` | skip TLS verify (debug only) |

## Checklist

- Prefer `-sS` over bare `-s` so failures are visible
- Use `--max-time` for scripts
- Do not put secrets in shell history; use env vars or files
