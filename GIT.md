#### Creating a Branch from Another Branch

In Git, you can create a new branch explicitly from another branch using the `git checkout -b` command. This is useful when you want to specify the source branch explicitly.

##### Syntax
```bash
git checkout -b new_branch source_branch
```

##### Explanation
- `git checkout -b`: Creates a new branch.
- `new_branch`: The name of the new branch you want to create.
- `source_branch`: The name of the source branch you want to base the new branch on.

##### Common Use Cases
```bach
# Move to the source branch
git checkout source_branch

# Pull the latest changes
git pull

# Create a new branch based on the source branch
git checkout -b new_branch source_branch
```
-----
#### Updating Your Branch from the Source Branch using `git merge`

To update your branch (`new_branch`) from the source branch (`source_branch`) using `git merge` with a custom commit message, follow these steps:

##### Syntax
```bash
# Merge changes from the source branch into your current branch with a custom commit message
git merge source_branch -m "Get the latest changes from source_branch"
```

##### Explanation
- `git merge`: Merges changes from the source branch into your current branch.
- `source_branch`: The name of the source branch from which you want to merge changes.
- `-m "Get the latest changes from source_branch"`: The option to include a custom commit message that describes the purpose of the merge.

##### Common Use Cases
```bash
# Step 1: Ensure you are on your local branch (new_branch)
git checkout new_branch

# Step 2: Merge changes from the source branch into your current branch with a custom commit message
git merge source_branch -m "Custom commit message"
```