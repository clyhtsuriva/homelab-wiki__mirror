# How to create a git mirror

## Hook

On the server, within the bare git repository, create a post-receive hook with the following content :

```sh
#!/usr/bin/env bash
# Push changes to GitHub
git push --mirror github
```

And make it executable :

```sh
chmod +x <repository path>/hooks/post-receive
```

## Remote

Configure the remote github repo :

```
# Making sure ssh works with the user,
# else create an ssh key and add it on github
ssh -T git@github.com
# > Hi <user>! You've successfully authenticated, but GitHub does not provide shell access.

# Add the remote github repo
git remote add github git@github.com:<user>/<repository name>.git
```

## Validate

Now you should be able to make a simple push to the git server and see github updated as well.
