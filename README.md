# Notes

- [Docker](#docker)
- [GIT](#git)
- [SSH](#ssh)

## Docker

- Stop all containers
  ```bash
  docker rm -f $(docker ps -aq)
  ```
- Enter into a container
  ```bash
  docker exec -it <container> bash
  ```

## GIT

- Disable check file mode
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
