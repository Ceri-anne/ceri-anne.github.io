---
layout: post
title: "Working with a forked git repo"
date: "2018-08-29"
categories: 
  - "development"
  - "git"
---

Found a cool project on Github you would like to contribute to? Here’s how to fork the repo, keep it up to date and make a pull request.

**FORK THE REPO**

Click 'Fork' in the original repo![](images/2018/08/github-fork.png)

This will create a forked version in your own Github account so you have your own copy of the repo.

**CLONE THE FORKED REPO**

1\. In your forked repo, click the `Clone or download` button

![](/images/2018/08/clone-or-download.png)

2\. Copy the git address

3\. In terminal, navigate to a folder you want to save the repo then enter `git clone` followed by the copied git address and hit enter

{% highlight console %}
$ git clone <your-repo-address>
{% endhighlight %}

You now have a local version of your forked repo.

**KEEP YOUR FORK UP TO DATE**

You can work on your forked version of the project completely separately from the original, but if you want to keep your version up to date then you need to link yours to the original by adding it as an \`upstream\`.

**Set up (only need to do once):**

1\. In the original repo, click on `Clone or download` and copy the original repo address

2\. In terminal, `cd` into your project folder

3\. Type \`git remote add upstream\`, paste in the original repo address and hit Enter

{% highlight console %}
$ git remote add upstream <original-repo-address>
{% endhighlight %}

**Update:**

1\. To update the upstream branches:

{% highlight console %}
$ git fetch upstream
{% endhighlight %}

This fetches all the changes made in the original repo.

2\. Update your local master:

{% highlight console %}
$ git pull upstream master
{% endhighlight %}

This pulls the upstream changes into your local master branch.

3\. Then git push to your remote repo

{% highlight console %}
$ git push
{% endhighlight %}

This updates your forked remote repo with the changes.

**SUBMIT A PULL REQUEST**

Once you have made changes to your fork, you can request for those changes to be merged into the original project.

1\. Click on `New pull request`

![](/images/2018/08/new-pull-request.png)

2\. On the compare changes page, check the base fork is the original repo and the head fork is your repo with the correct branch selected

3\. Add a title and description

4\. `Allow edits from maintainers` will be checked. If you're not happy with this then de-select

5\. Click `Create pull request`

Then it's up to the maintainers of the original repo to ask questions, request changes or merge it in! 🤞🏼
