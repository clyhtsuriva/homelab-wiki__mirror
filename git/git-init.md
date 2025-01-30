# How to create a new git repository on git.adjutor.xyz.

1. Client-side creation

```sh
mkdir <repository-name>
cd <repository-name>
git init
git add .
git commit -m "Initial commit"
```

2. Server-side creation

```sh
# As `git`
mkdir /var/www/git/homelab-iac.git
cd /var/www/git/homelab-iac.git
git init --bare
echo "<Short description of the repo>" > description

```

3. Client-side push

```sh
git remote add origin ssh://git@git.adjutor.xyz:8022/var/www/git/<repository-name>.git
git push origin master
```
