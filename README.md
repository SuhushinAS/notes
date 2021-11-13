# Notes

[SSH](#ssh)

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

