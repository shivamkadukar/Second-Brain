- Create patch file from a specific commit
```bash
git diff --patch <commit hash> HEAD > mypatch.patch

git apply mypatch.patch
```

