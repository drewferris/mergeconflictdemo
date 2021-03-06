# Handling Merge Conflicts
### Issue
* Some one on your project has merged a **_Pull Request_** into the `master` branch.
* You push your code to your remote branch named `branch_name` and open a **_Pull Request_** to the `master` branch.
* _GitHub_ informs you your code can not automaticly merge into the `master` branch.

### make an overview

### Step by Step Solution
1. Navigate to your project in your shell (*the command line*).
  * `$ cd /path/to/your/project`
2. Make sure you are in the correct branch.
 * `$ git branch`  
  _git will list local branches and put a * infront of the branch you are in_
3. Make sure you have notthing to commit. If you have un commited changes, commit them.
 * `$ git status`  
  _nothing to commit, working directory clean_
4. Update local copy of origin repository
 * `$ git fetch origin`  
5. Merge local copy of `origin/master` into your local branch called `branch_name`.
  * `$ git merge origin/master`  
   *git will tell you what files have failed to automaticly merge* 
6. Open the files with conflicts in your _text editor_.
7. In each file with conflict delete the code that is unwanted.
8. In each file Update the code to reflect the correct changes.
  * Delete the lines that say `<<< HEAD`, `====`, and `>>> master`
  * Delete lines from `master` or your `branch_name` that are unwanted.
  ```javascript
 <<<<<<<<<<< HEAD 
   this is where the conflicting code from your branch is
 ===========
   this is where the conflicting code from the master branch is
 >>>>>>>>>>> master 
``` 
8. **_RUN YOUR CODE_**.
 * **This is possibly the most important step!**
 * **Just becuse you "handled" your merge conflict does not mean your haven't broken your app.**
9. Add your changes and commit.
  * `$ git add .`
  * `$ git commit -m  "handled merge conflict from master"`
10. Push to your `branch_name` on origin.
  * `$ git push origin <branch_name>`
11. **Your _Pull Request_ should be able to merge!**
 