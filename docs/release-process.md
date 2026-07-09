# Release Process

## Development

```
feature/*
```

↓

```
develop
```

↓

Automatic deployment to DEV

---

## QA

```
release/*
```

↓

```
test
```

↓

Automatic deployment to QA

---

## Production

```
main
```

↓

Automatic deployment to Production

---

## Hotfix

```
main

↓

hotfix/*

↓

main

↓

test

↓

develop
```

---

## Ideal Production Release Checklist

- Build Successful
- Unit Tests Passed
- Quality Gate Passed
- Security Scan Passed
- QA Approved
- Technical Leader Approved
- Architect Approved
- Git Tag Generated
- CHANGELOG Generated
- GitHub Release Generated