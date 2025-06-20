Gitea Action Pull Request
===

A small and simple github action that is designed for an image that contains the gitea cli and is run within a gitea ci system. 
The script simplifies the automatic creation of pull requests from a development branch towards a base branch. 

The action requires the gitea cli to be installed. When using it in your action workflow please install the cli from here [https://dl.gitea.com/tea/](https://dl.gitea.com/tea/) or use a prepared image like my ci-helm-image [https://github.com/deB4SH/ci-helm-image/blob/main/Dockerfile](https://github.com/deB4SH/ci-helm-image/blob/main/Dockerfile).

### Functionality and Limitations

2025-06-20:
* Pull Request is created on basic string
* There is currently no functionality for adding a description 
* There is no functionality for adding an reviewer automatically
* There is no functionality for adding labels automatically


### Usage

The following listing describes an example usage.

```
- name: Create PR
  uses: deb4sh/tea-pr@main
  with:
    token: ${{ secrets.CLI_TOKEN }}
    base: 'main'
```

### Configuration Values

token: A required PAT from your gitea instance with the following rights. (user: read, repository: read & write, issues: read)

base: your designated base branch to merge branches towards