# Repo: someuser/myframework
# Fork: superteam/myframework

# Track:
git clone https://github.com/superteam/myframework.git
cd myframework
git remote add upstream https://github.com/someuser/myframework.git

# Update:
git fetch upstream
git rebase upstream/master
git push
git push --tags

# checkout the tag
git checkout tag_to_fork_from

# alternatively, create a new branch starting with the tag
git checkout -b mybranch tag_to_fork_on_git
