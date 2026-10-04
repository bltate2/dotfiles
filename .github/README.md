# Dotfiles

## New Machine Setup

1. `git clone https://github.com/bltate2/dotfiles $HOME/.cfg`

1. Add an alias (`~/.bash_aliases`)
    ```shell
    alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
    ```

    Then `source ~/.bashrc`

1. Set up the `config` alias to not show untracked files
    ```shell
    config config --local status.showUntrackedFiles no
    ```

1. Pull tracked files out of git directory and place in the worktree
    ```shell
    git checkout
    ```

    If this fails due to `untracked working tree files would be overwritten by checkout`, then backup or remove the offending files and run `git checkout` again.

## Making Changes

1. Add specific files
    ```shell
    config add <path/to/your/files>
    ```
1. Commit it
    ```shell
    config commit -m "Added <whatever>"
    ```
1. Push
    ```shell
    config push -u origin main
    ```


References: https://www.ackama.com/articles/the-best-way-to-store-your-dotfiles-a-bare-git-repository-explained/#footnote-1
