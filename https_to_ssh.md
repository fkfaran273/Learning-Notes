<!-- Step 1: Check Your Git Remote URL -->
# If it shows an HTTPS URL, you need to change it to SSH.
> git remote -v

#Example of incorrect output:
origin  https://github.com/user/example.git (fetch)
origin  https://github.com/user/example.git (push)


<!-- Step 2: Change Remote URL to SSH -->
# Remove the old HTTPS remote:
git remote remove origin

#  Add the correct SSH remote:
> git remote add origin git@github.com:user/example.git


#  Verify the change:
> git remote -v

# Output should now show:
origin  git@github.com:user/example.git (fetch)
origin  git@github.com:user/example.git (push)

# Step 3: Push Your Code via SSH
#  If successful, your code will be uploaded to GitHub!
> git push origin main





