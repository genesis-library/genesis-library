```
git flow release start sprint1-release
git flow release publish sprint1-release
```

other person:
```
git flow release track sprint1-release
```
pulls the code - why not use git pull or something like this? (remember using git tree on vscode)

makes some changes on release branch

```
git checkout develop
git merge release/sprint1-release
git push
```

```
git flow release finish sprint1-release

1. merges to master
2. creates release tag
3. makes you write a commit message.
4. deletes release branch
5. returns back to develop branch


git checkout master
git push --tags
```

what are tags used for?


git flow vs trunk based development

- git flow is strict control.
- Ensures code quality and help eliminate bugs early.
- It slows down software development.
- Features can be long living that might be hard to combine to main project
- Office politics, when merger has lack of confidence.

git flow 
- junior developers
- open source project
- established product

