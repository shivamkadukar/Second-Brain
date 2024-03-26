Listing tags
```bash
git tag

git tag -l "v1.8.5*"
```

Creating tags

Annotated tags
```bash
git tag -a {version} -m {version description}
```

Lightweight tags
```bash
git tag {version}
```

Tagging later
```bash
git tag -a {version} {commit hash}
```

Publishing tags
```bash
git push origin {version} # push specific tag

git push origin --tags # push all tags
```



