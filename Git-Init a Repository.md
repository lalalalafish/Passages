Yujie Liu 20240723

-----
# Main Steps

Step0: Open the terminal at the local repository location
Step1: Init a empty git repository. It will create a directory `.git` under the repository
```terminal
git init
```
Step2: 
```terminal
git remote add origin [ADDRESS]
```
Step3: 
```terminal
git add .
```
Step4:
```terminal
git commit -m "[COMMENT]"
```
Step5:
```terminal
git push origin master
```

------
# Useful Commands


- Pull:
  ```terminal
  git pull
  ```
- Display the local branch:
  ```terminal
  git branch 
  ```
- Display the remote branch:
  ```terminal
  git branch -r
  ```
- Display both the local and remote branch:
  ```terminal
  git branch -a
  ```
- Create a local branch:
  ```terminal
  git branch [NAME]
  ```
- Create a remote branch:
  ```terminal
  git push --set-upstream origin [REMOTENAME]
  git push origin [REMOTENAME]
  ```

----
# Common Issues
## Issue1-Push: Update is rejected because the tip of the current branch is behind

**Solution1:**  Pull the latest version of this branch from the remote repository
```terminal
git pull
```


**Solution2:** For reserve both remote repository and local repository,
1. Create a new branch to save this local repository:
```terminal
git branch [NAME]
```
2. And then push to this new branch:
```terminal
git push -u origin [NAME]
```

**Solution3:** Force git to update without this warning.**(CAUTION USE!)**
```terminal
git push --force
```

## Issue2-Push: Authentication failed because the support for password authentication was removed on August 13, 2021

Solution: Use the personal access token to replace the password:
1. Open the Github: `setting`--> `Developer settings` --> `Personal access token`
2. Click `Generate new token`
3. Enter the token name and select `repo`
4. Copy the token
5. Use the token to replace the password when `git push`


# Issue3-Push: Fatal: Unable to access '`https://github/xxx`': Failed to connect to github.com port 443: Timed out

Solution1: Open the terminal with VPN
Solution2: Enter this proxy command: and then push again
```terminal
git config --global https.proxy
```
If you want to unset the proxy:
```terminal
git config --unset https.proxy
```

# Issue4-Init: '[`SUBDIRECTORY`]' does not have a commit check out

Reason: this sub directory is already have a `.git`
Solution: Delete the `.git` of the sub directory


---
[END]