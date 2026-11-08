# Security audit: descope/python-sdk

Date: 2026-11-08 | Auditor: [mutsuumii](https://github.com/mutsuumii)

## Summary

Found 3 issue(s): 3 high.

## Findings

### 1. [HIGH] Hardcoded credentials

**CWE-798** | `tests/test_auth.py` line 301

Credentials hardcoded in source. Anyone with repo access can extract them.

```
dummy_refresh_token = "dummy refresh token"
```

**Fix:** Use os.environ.get('SECRET') or a secrets manager. Never commit credentials.
---

### 2. [HIGH] Hardcoded credentials

**CWE-798** | `tests/test_auth.py` line 392

Credentials hardcoded in source. Anyone with repo access can extract them.

```
valid_jwt_token = "eyJhbGciOiJFUzM4NCIsImtpZCI6IlAyQ3R6VWhkcXBJRjJ5czlnZzdtczA2VXZ0QzQiLCJ0eXAiOiJKV1QifQ.eyJkcm4iOiJEU1IiLCJleHAiOjIyNjQ0Mzc1OTYsImlhdCI6MTY1OTYzNzU5NiwiaXNzIjoiUDJDdHpVaGRxcElGMnlzOWdnN21zMDZVdnRDNCIsInN1YiI6IlUyQ3UwajBXUHczWU9pUElTSmI1Mkwwd1VWTWcifQ.WLnlHugvzZtrV9OzBB7SjpCLNRvKF3ImFpVyIN5orkrjO2iyAKg_Rb4XHk9sXGC1aW8puYzLbhE1Jv3kk2hDcKggfE8OaRNRm8byhGFZHnvPJwcP_Ya-aRmfAvCLcKOL"
```

**Fix:** Use os.environ.get('SECRET') or a secrets manager. Never commit credentials.
---

### 3. [HIGH] Hardcoded credentials

**CWE-798** | `tests/test_totp.py` line 44

Credentials hardcoded in source. Anyone with repo access can extract them.

```
refresh_token = "dummy refresh token"
```

**Fix:** Use os.environ.get('SECRET') or a secrets manager. Never commit credentials.
---
