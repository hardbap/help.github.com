---
layout: default
title: Import from Subversion
categories: intermediate
---

<p class="intro">Importing a repository from Subversion retains all
history and makes past versions available to GitHub and various git tools.
Choose a tool from the list below to get started.
</p>

Manual import
-------------

### svn2git

[svn2git](http://github.com/nirvdrum/svn2git) is designed to provide a complete svn import.  Unlike git-svn, it will create proper git tags from your svn "tags".

### git-svn

[git-svn](http://www.kernel.org/pub/software/scm/git/docs/git-svn.html) can be used to import as well.  Note that there may be issues if you have branches or tags (they won't be imported over).  If you only have a trunk, like many svn repositories, this method should work for you without issue.

First, be sure to [create your repository on GitHub](http://github.com/repositories/new)

<pre class="terminal">$ git svn clone -s SVN_REPO_URL LOCAL_DIR
$ cd LOCAL_DIR
$ git remote add origin git@github.com:GITHUB_USERNAME/REPO_NAME.git
$ git push origin master</pre>

Note that the `-s` switch implies that your svn repo is set up with the standard branches/tags/trunk structure.

git-svn adds a note to every commit message it copies over from svn. To get rid of that note, add `--no-metadata` to the command.

You can pull in later commits by running `git-svn rebase` from within your repo.  If you ever lose your local copy, just run the import again with the same settings and you'll get another working directory with all the necessary git-svn settings saved.

#### Author mapping

When migrating a Subversion repository to Git, you can map the Subversion users to Git users. You have to create an authors file which contains the mappings:

    tekkub = Tekkub <tekkub@github.com>

The format is `svnuser = gituser_name <gituser_email>`.  To automatically generate an authors file, check out [this guide](http://technicalpickles.com/posts/creating-a-svn-authorsfile-when-migrating-from-subversion-to-git/).

Once your authors file is complete, clone the subversion repository with the authors file:

<pre class="terminal">$ git svn --authors-file=path/to/authors_file clone SVN_REPO_URL LOCAL_DIR</pre>


Automatic import
----------------

**NOTE:** The automatic Subversion import feature has been removed from
github.com due to potential security risks and performance issues. Please use
one of the manual import methods described above instead.

Other guides
------------

* [Guide by Frederick Giasson: Moving Projects from Google Code to GitHub](http://fgiasson.com/blog/index.php/2011/11/21/moving-projects-from-google-code-to-github/)
* [Guide by Yuval Kogman](http://blog.woobling.org/2009/06/git-svn-abandon.html)
* [Guide by John Goulah](http://blog.johngoulah.com/2009/11/migrating-svn-to-git)
* [Guide by Jon Maddox](http://www.simplisticcomplexity.com/2008/03/05/cleanly-migrate-your-subversion-repository-to-a-git-repository/) -- doesn't deal with branches
* [Guide by Bob McWhirter](http://www.fnokd.com/2008/08/20/mirroring-svn-repository-to-github) -- doesn't deal with branches
