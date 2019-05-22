# Git

## Clone Tag

```
git clone --branch <tag> <repo>
```

## Delete remote GIT tag

```
git push --delete origin v-xxxx-release
```

## Change commit message (last)

```
git commit --amend
```

## Compare Branches

```
git diff feature-x..develop
```

## File changes history

```
git log <file>
```

## Logs

```
git log --stat
git log -p
```

## Go back + fix + add to master

Same can be dome with branchs + merge (new_commit_id can be taken from reflog)

```
git checkout commit_id
git commit -am "xxx"
git checkout master
git cherry-pick new_commit_id
```
