# User & Organization Pages

GitHub username = lockevn
Create a GitHub repository named lockevn.github.com
Commit a file named index.html into the master branch, and push it to GitHub, it's automatically published to http://alice.github.com/.

(On the first push, it can take up to ten minutes before the content is available)


github.com/lockevn/lockevn.github.com → http://lockevn.github.com/


# Project Pages

Let’s say your GitHub username is “bob” and you have an existing repository named fancypants. If you create a new root branch named gh-pages in your repository, any content pushed there will be published to http://bob.github.com/fancypants/.

In order to create a new root branch, first ensure that your working directory is clean by committing or stashing any changes. The following operation will lose any uncommitted files! You might want to run this in a fresh clone of your repo.

$ cd /path/to/fancypants
$ git symbolic-ref HEAD refs/heads/gh-pages
$ rm .git/index
$ git clean -fdx

After running this you’ll have an empty working directory (don’t worry, your main repo is still on the master branch). Now you can create some content in this branch and push it to GitHub. For example:

$ echo "My GitHub Page" > index.html
$ git add .
$ git commit -a -m "First pages commit"
$ git push origin gh-pages

On the first push, it can take up to ten minutes before the content is available.

Real World Example: github.com/defunkt/ambition@gh-pages → http://defunkt.github.com/ambition.



# Custom Domains
GitHub Pages allows you to direct a domain name of your choice at your Page.
User Page at http://lockevn.github.com/
Point http://git.lockevn.gurucore.com to http://lockevn.github.com/ 
Start by creating a file named CNAME in the root of your repository. It should contain your domain name like so:

> git.lockevn.gurucore.com

Visit your domain registrar or DNS host and add a record for your domain name.
For a sub-domain, create a CNAME record pointing at lockevn.github.com

If you are using a top-level domain like example.com, you must use an A record pointing to 207.97.227.245 (Do not use a CNAME record with a top-level domain)


# Custom 404 Pages
If you provide a 404.html file in the root of your repo, it will be served instead of the default 404 page
