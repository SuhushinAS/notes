# Notes

[SSH](#ssh)

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
  ```bash
  ssh-add ~/.ssh/id_rsa
  ```

