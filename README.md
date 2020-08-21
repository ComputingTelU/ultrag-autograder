# ultrag-autograder
Autograder to help practicum grading in School of Computing, Telkom University

# Getting Started to Ultrag Autograder
1. Make sure you have python 3 and pip installed
2. Create new virtual environment inside ultrag-autograder directory
`virtualenv env`
3. Activate the virtual environment
`source env/bin/activate`
4. The terminal now should be looked like this
`(env) [username]$`
5. Install required packages
`pip install -r requirements.txt`
6. Run the server
`python ultrag_api/manage.py`
7. When you're done working deactivate your virtualenv
`deactivate`

# Branching Guide
1. There are two main branches, `master` and `develop`. Developers **are not allowed** to push directly to main branches.
2. There are three types of supporting branches, `feature`, `release`, and `hotfix`. You should create a supporting branch and push your work there and create a pull request into the main branches.
3. `feature` branches are used to develop new features. The branch name is also a card name in trello, say we have card `be-001`, so the `feature` branches will be `feature/be-001`. You should create `feature` branch out from `develop`:
`git checkout -b feature/be-001 develop`
4. `release` branches support preparation of a new production release. They allow for minor bug fixes and preparing meta-data for a release (version number, build dates, etc.). By doing all of this work on a release branch, the `develop` branch is cleared to receive features for the next big release. For example, say version 1.1.5 is the current production release and we have a big release coming up. The state of `develop` is ready for the “next release” and we have decided that this will become version 1.2:
`git checkout -b release/1.2 develop`
6. `hotfix` branches are very much like release branches in that they are also meant to prepare for a new production release, albeit unplanned. They arise from the necessity to act immediately upon an undesired state of a live production version. When a critical bug in a production version must be resolved immediately, a hotfix branch may be branched off from the corresponding tag on the master branch that marks the production version. A `hotfix` should be created out from `master`. For example, version 1.2 is the current production release running live and causing troubles due to a severe bug. But changes on `develop` are yet unstable. We may then branch off a hotfix branch and start fixing the problem:
`git checkout -b hotfix/be-002 master`

[Reference](https://nvie.com/posts/a-successful-git-branching-model/)

# Merge/Pull Request
1. Before doing a pull request, your code should at least pass the unit test.
2. Your code will be reviewed by your pair reviewer, and if your code works well in their machine, they will give you a PR-approved tag.
3. Since we don't have QA, so we skip the testing process.
4. Lastly, you need approval from PM to merge your branch.
