# MyProofContainer_VSCode

Dockerfile for proofreading markdown files.
Auto-proofreading is implemented with [textlint](https://github.com/textlint/textlint).
You can use this repository on Visual Studio Code.

![images](./Screen%20Shot%200004-10-01%20at%2017.34.20.png)

## How to use

I'm sorry if there are any changes...

1. Download [Visual Studio Code](https://code.visualstudio.com/Download), [Git](https://git-scm.com/downloads), [Docker Desktop](https://www.docker.com/products/docker-desktop/).
2. Set configuration variables. ([git-First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup#_first_time))

```shell
git config --global user.name "<your_name>"
git config --global user.email "<your_email>"
```

3. Fork this repository and clone to your devices.
4. Open your cloned repository on Visual Studio Code.
5. Install [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) that is the extension of Visual Studio Code.
6. `Ctrl` (`command`) + `Shift` + `P`
7. Select `Remote-Containers: Reopen in Container`

## If you want to add new rules

You should add textlint rules you want to add in `Dockerfile` and also edit `.textlintrc`.
