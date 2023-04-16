# Notes

- [Docker](#docker)
- [GIT](#git)
- [NPM](#npm)
- [SSH](#ssh)
- [VirtualBox](#virtualbox)
- [Windows](#windows)
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

## NPM
- Show active npm links
  ```shell
  npm ls -g --depth=0 --link=true
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

- Enable "Nested VT-x/AMD-V"
  ```shell
  VBoxManage modifyvm "<name>" --nested-hw-virt on
  ```
- MacOS set resolution
  ```shell
  VBoxManage setextradata "<name>" VBoxInternal2/EfiGraphicsResolution <resolution-x>x<resolution-y>

## Windows

- Проверка всех приложений и их полные имена.
  ```shell
  Get-AppxPackage | Select Name, PackageFullName
  ```
- Удаление приложения по названию
  ```shell
  Get-AppxPackage -allusers <название> | Remove-AppxPackage
  ```

## Other

- Inotify Watches Limit (https://youtrack.jetbrains.com/articles/IDEA-A-2/Inotify-Watches-Limit)
  - Add the following line to either `/etc/sysctl.conf` file or a new `*.conf` file (e.g. `idea.conf`) under `/etc/sysctl.d/` directory:
    ```ini
    fs.inotify.max_user_watches = 524288
    ```
  - Then run this command to apply the change:
    ```shell
    sudo sysctl -p --system
    ```
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
