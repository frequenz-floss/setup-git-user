# Archived!

> [!WARNING]
> To set up the Git user you can now use the more general purpose [frequenz-floss/gh-action-setup-git](https://github.com/frequenz-floss/gh-action-setup-git/) action.

# setup-git-user

> GitHub Action that sets git user and email to enable committing

If you try to use `git commit` or `git tag` on GitHub Actions, it will throw an error:

<img src="https://user-images.githubusercontent.com/1402241/96522622-59905880-1239-11eb-9993-07b64bebb282.png" alt="Please tell me who you are. Run git config to set your account's default identity" width="489">

This action is a convenience action which sets the user and email in one line.

# Usage

```yaml
    steps:
      - uses: actions/checkout@v3
      - uses: fregante/setup-git-user@v2
      - run: git commit --message 'Something cool'
      - run: git push
```

New commits and tags will be assigned to the [@actions](https://github.com/actions) user. If you want to customize the user, **you don't need this action**. Just use:

```yaml
    steps:
      - uses: actions/checkout@v3
      - run: git config --global user.email "you@example.com"
      - run: git config --global user.name "Your Name"
      - run: git commit --message 'Something cool'
      - run: git push
```

## Related

- [daily-version-action](https://github.com/fregante/daily-version-action) - Creates a new tag using the format Y.M.D, but only if HEAD isn’t already tagged.
- [title-to-labels-action](https://github.com/fregante/title-to-labels-action) - Cleans up the titles of issues and PRs from common opening keywords.
