# Web Programming Reviews
</hr>
# Pull Request Tutorial

## What is a Pull Request?
From Github's [Using Pull Requests Page](https://help.github.com/articles/using-pull-requests)
> Pull requests let you tell others about changes you've pushed to a GitHub repository. Once a pull request is sent, interested parties can review the set of changes, discuss potential modifications, and even push follow-up commits if necessary.

Pull Requests are commonly used by teams and organizations collaborating using the [Shared Repository Model](https://help.github.com/articles/using-pull-requests#article-platform-nav), where everyone shares a single repository and topic branches are used to develop features and isolate changes. Many open source projects on Github use pull requests to manage changes from contributors as they are useful in providing a way to notify project maintainers about changes one has made and in initiating code review and general discussion about a set of changes before being merged into the main branch.

Here's [an example pull request](https://github.com/jquery/jquery/pull/1051) from jQuery's github repo.

## Creating a Pull Request

There are 2 main work flows when dealing with pull requests:

1. Pull Request from a [forked repository](https://help.github.com/articles/fork-a-repo)
2. Pull Request from a branch within a repository

Here we are going to focus on 2.

### Creating a Topical Branch

First, we will need to create a branch from the latest commit on master. Make sure your repository is up to date first using

```bash
git pull origin master
```

*Note:* `git pull` does a `git fetch` followed by a `git merge` to update the local repo with the remote repo. For a more detailed explanation, see [this stackoverflow post](http://stackoverflow.com/questions/292357/whats-the-difference-between-git-pull-and-git-fetch).

To create a branch, use `git checkout -b <new-branch-name> [<base-branch-name>]`, where `base-branch-name` is optional and defaults to `master`. I'm going to create a new branch called `pull-request-demo` from the `master` branch and push it to github.

```bash
git checkout -b pull-request-demo
git push origin pull-request-demo
```

### Creating a Pull Request

To create a pull request, you must have changes committed to your new branch.

Go to the repository page on github. And click on "Pull Request" button in the repo header.

![Pull Request Button](images/pr.png)

Pick the branch you wish to have merged using the "Head branch" dropdown. You should leave the rest of the fields as is, unless you are working from a remote branch. In that case, just make sure that the base repo and base branch are set correctly.

![Head Branch Dropdown](images/head_ref.png)

Enter a **title** and **description** for your pull request. Remember you can use [Github Flavored Markdown](https://help.github.com/articles/github-flavored-markdown) in the description and comments

![Title and Description](images/tensor.png)

Finally, click on the green "Create pull request" button to finish creating the pull request.

![Send Pull Request](images/cpr.png)

You should now see an open pull request.

![Open Pull Request](images/opr.png)

### Using a Pull Request

You can write comments related to a pull request,

![Writing a comment](https://f.cloud.github.com/assets/676185/316903/d9729df8-984b-11e2-9bf6-8fe064957723.png)

view all the commits by all contained by a pull request under the commits tab,

![Commits tab](https://f.cloud.github.com/assets/676185/316908/563073ba-984c-11e2-8bd6-450939fbd7b3.png)

or see all the file changes from the pull request across all the commits under the "Files Changed" tab.

![Files Changed](https://f.cloud.github.com/assets/676185/316911/9e4cbe42-984c-11e2-9636-dd50cb98db44.png)

You can even leave a comment on particular lines in the code changed, simply by hovering to the left of a line and clicking on the blue note icon.

![Comment in line](https://f.cloud.github.com/assets/676185/316916/015be558-984d-11e2-9c4c-2ddc793fac3c.png)

