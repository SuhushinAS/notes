# Notes

- [Docker](#docker)
- [GIT](#git)
- [SSH](#ssh)
- [VirtualBox](#virtualbox)
- [Other](#other)

## Docker

- Stop all containers
  ```bash
  docker rm -f $(docker ps -aq)
  ```
- Enter into a container
  ```bash
  docker exec <container> sh
  ```

## GIT

- Ignore file mode
  ```bash
  git config core.fileMode false
  ```
- Clean origin
  ```bash
  git fetch -p
  ```
- Show repository address
  ```bash
  git remote show origin
  ```
- Revert changes
  ```bash
  git checkout <commit> -- <file>
  ```
- Graph log
  ```bash
  git log --graph --all
  ```
- "Undo"
  ```bash
  git reset --hard ORIG_HEAD
  ```
- Rebase commits From `current` to `target`
  ```bash
  git rebase <target>
  ```
- Squash commits from `current-commit` to `target-commit`
  ```bash
  git rebase -i <pre_target-commit>
  ```

## SSH

- Generate key
  ```bash
  ssh-keygen -t rsa -C "<email>"
  ```
- Run SSH Agent
  ```bash
  eval "$(ssh-agent -s)"
  ```
- Add key
  ```bash
  ssh-add ~/.ssh/id_rsa
  ```
- Check connection
  ```bash
  ssh -T git@<server>
  ```

## VirtualBox

- MacOS set resolution
  ```bash
  VBoxManage setextradata "<name>" VBoxInternal2/EfiGraphicsResolution <resolution-x>x<resolution-y>
  ```

## Other

- Set watchers limit
  (https://confluence.jetbrains.com/display/IDEADEV/Inotify+Watches+Limit)
- Chmod
  ```bash
  sudo chmod -R <mode> <path>
  ```
- Find & Kill Process
  - Find Process
    ```bash
    ps ax |grep <search>
    ```
  - Check ports
    ```bash
    netstat -natp
    ```
  - Kill Process by `Id`
    ```bash
    sudo kill -9 <Id>
    ```
- Replace all extensions
  ```bash
  find . -name "*.<from>" -exec rename -v 's/\.<from>$/\.<to>/i' {} \;
  ```
