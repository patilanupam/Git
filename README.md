# Git

REBASE FROM MAIN

git checkout main
git pull
git checkout "your branch"
git rebase main
git push -f


When COMMITS made on same day
git add -A
git commit --amend --no-edit 
git push -f

When need to RESET to last commit:
git reset --hard feature/feature_name 
