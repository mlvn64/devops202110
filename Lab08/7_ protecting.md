## Protecting branch

1. En el repositorio, seleccionar Settings > Branches
1. En la sección ”Branch protection rules”, clic en "Add rule"
1. En la sección "Branch name pattern”, ingresar "main"
1. Habilitar los siguiente settings:
    * Require a pull request before merging
        * Require approvals
        * Seleccionar: 1
    * Dismiss stale pull request approvals when new commits are pushed
    * Include administrators