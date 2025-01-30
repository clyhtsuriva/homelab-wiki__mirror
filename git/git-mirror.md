# How to create a git mirror on github

## Repository on github

Make sure to create an empty repository on github and have an access from the VPS to it (token or ssh).

```sh
# Making sure ssh works with the user,
# else create an ssh key and add it on github
ssh -T git@github.com
# > Hi <user>! You've successfully authenticated, but GitHub does not provide shell access.
```

## Hook

On the server, within the bare git repository, create a `post-receive` hook and make it executable :

```sh
touch <repository path>/hooks/post-receive
chmod +x <repository path>/hooks/post-receive
```

Add a simple git push in the hook :

```sh
cat << EOF > <repository path>/hooks/post-receive
#!/bin/bash
# Push changes to GitHub
git push --mirror github
EOF
```

## Remote

Configure the remote github repo :

```sh
git remote add github git@github.com:<user>/<repository name>.git
```

## Validate

Now you should be able to make a simple push to the git server and see github updated as well.
