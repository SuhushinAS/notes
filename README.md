# Notes

- [Docker](#docker)
- [GIT](#git)
- [SSH](#ssh)
- [VirtualBox](#virtualbox)
- [Other](#other)

## Docker

- Stop all containers
  ```shell
  docker rm -f $(docker ps -aq)
  ```
- Enter into a container
  ```shell
  docker exec <container> sh
  ```

## GIT

- Ignore file mode
  ```shell
  git config core.fileMode false
  ```
- Clean origin
  ```shell
  git fetch -p
  ```
- Show repository address
  ```shell
  git remote show origin
  ```
- Revert changes
  ```shell
  git checkout <commit> -- <file>
  ```
- Graph log
  ```shell
  git log --graph --all
  ```
- "Undo"
  ```shell
  git reset --hard ORIG_HEAD
  ```
- Rebase commits From `current` to `target`
  ```shell
  git rebase <target>
  ```
- Squash commits from `current-commit` to `target-commit`
  ```shell
  git rebase -i <pre_target-commit>
  ```

## SSH

- Generate key
  ```shell
  ssh-keygen -t rsa -C "<email>"
  ```
- Run SSH Agent
  ```shell
  eval "$(ssh-agent -s)"
  ```
- Add key
  ```shell
  ssh-add ~/.ssh/id_rsa
  ```
- Check connection
  ```shell
  ssh -T git@<server>
  ```

## VirtualBox

- MacOS set resolution
  ```shell
  VBoxManage setextradata "<name>" VBoxInternal2/EfiGraphicsResolution <resolution-x>x<resolution-y>
  ```

## Other

- Set watchers limit
  (https://confluence.jetbrains.com/display/IDEADEV/Inotify+Watches+Limit)
- Chmod
  ```shell
  sudo chmod -R <mode> <path>
  ```
- Find & Kill Process
  - Find Process
    ```shell
    ps ax |grep <search>
    ```
  - Check ports
    ```shell
    netstat -natp
    ```
  - Kill Process by `Id`
    ```shell
    sudo kill -9 <Id>
    ```
- Replace all extensions
  ```shell
  find . -name "*.<from>" -exec rename -v 's/\.<from>$/\.<to>/i' {} \;
  ```
