Documentation: https://github.com/git-ecosystem/git-credential-manager/blob/main/docs/multiple-users.md  

When there is multiple identities on a single hosting service, git often asks to choose an account. To avoid this we can set default account for particular remote as:
```shell
# if cloning for first time
git clone https://<account-name>@github.com/<repo-account>/<repo>.git
# if repo name contains `@` escape with `%40`

# updating an existing clone
git remote set-url origin https://<account-name>@github.com/<repo-account>/<repo>.git
```
