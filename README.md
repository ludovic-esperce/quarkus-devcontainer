# Création d'un projet

1. Installation de [Quarkus CLI](https://quarkus.io/get-started/)
2. Création d'un projet :
```
quarkus create
```

Alternative sans Quarkus Cli ->  [quarkus.io](https://code.quarkus.io/)

# Mise en place d'un devcontainer (ouai, ouai)

Fonctionne avec VSCode. A tester avec d'autres IDE.

1. Création d'un dossier `.devcontainer` dans le projet Quarkus
2. Ajout d'un fichier  `devcontainer.json` tel que :
```json
{
    "name": "Quarkus - 21-jdk-bookworm",
    "image": "mcr.microsoft.com/devcontainers/java:21-jdk-bookworm",
    "workspaceFolder": "/workspaces/${localWorkspaceFolderBasename}",
    "features": {
        "ghcr.io/devcontainers/features/common-utils:2": {},
        "ghcr.io/devcontainers/features/github-cli:1": {},
        "ghcr.io/devcontainers/features/sshd:1": {},
        "ghcr.io/devcontainers/features/java:1": {
            "installMaven": "true",
            "installGradle": "false"
        },
        "ghcr.io/ebaskoro/devcontainer-features/sdkman:1": {
			"candidate" : "quarkus"
			}
    },
    "postCreateCommand": "mvn clean",
    "customizations": {
        "vscode": {
            "extensions": [
                "esbenp.prettier-vscode",
                "msjsdiag.debugger-for-chrome",
                "oderwat.indent-rainbow",
                "visualstudioexptteam.vscodeintellicode",
                "ritwickdey.liveserver",
                "shengchen.vscode-checkstyle",
                "dhruv.maven-dependency-explorer",
                "JoseVSeb.google-java-format-for-vs-code",
                "ms-azuretools.vscode-docker",
                "redhat.fabric8-analytics",
                "redhat.java",
                "redhat.vscode-microprofile",
                "redhat.vscode-quarkus",
                "redhat.vscode-xml",
                "visualstudioexptteam.vscodeintellicode",
                "vscjava.vscode-java-debug",
                "vscjava.vscode-java-dependency",
                "vscjava.vscode-java-pack",
                "vscjava.vscode-java-test",
                "vscjava.vscode-maven"
            ]
        }
    },
    "forwardPorts": [
        8080
    ]
}
```

Puis "reopen" le dev container, plus d'informations [ici](https://code.visualstudio.com/docs/devcontainers/tutorial)

# Démarrer l'application en "dev mode"

```shell script
./mvnw quarkus:dev
```

> [!NOTE]
> Dev UI intégrée accessible en utilisant l'adresse suivante : [http://localhost:8080/q/dev/](http://localhost:8080/q/dev/)