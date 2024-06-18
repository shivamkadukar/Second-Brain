
__Remove a entire file from commit history__

```
git filter-repo --use-base-name --path [FILENAME] --invert-paths
```

__Edit some part of the file from the commit history__

- create a replacements.txt and add the text you want to replace and text you want to replace with
```
ORIGINAL==>REPLACEMENT
```
```
git filter-repo --replace-text ../replacements.txt
```
This will search for original text in your commit history and replace it.

__Link a local branch to already existing branch on remote__

```bash
git push --set-upstream origin main --force
```
This can be used if reference to remote branch is lost from your local clone. this has happened with me after using filter-repo command

__Set remote repo link to a local branch__
```bash
git remote add origin {branch https link}
```

you can check current reference of remote repo with
```bash
git remote -v
```
