# Push to OCI Registry

Set up your GitHub Actions workflow with ability to push to OCI Registry
To use this GitHub Action, follow these steps:

1. Create a new workflow file in your repository, for example `.github/workflows/push-to-oci.yml`.

2. Add the following code to the workflow file:

```yaml
name: Push to OCI Registry

on:
    push:
        branches:
            - main
        paths:
            - /path/to/your/folder/**

jobs:
    push-to-oci:
        runs-on: ubuntu-latest

        steps:
            - name: Push to OCI Registry
              uses: bivas/push-to-oci-action@v1
              with:
                path: /path/to/your/folder
                image_repository: registry/repository # Don't include tag infromation, will be added by action
                registry: docker.io
                registry_username: username
                registry_password: password
```

3. Include information for `registry_username`, and `registry_password` with your OCI registry details. Make sure to store these secrets securely in your repository's settings.

4. Commit and push the workflow file to your repository.

Now, whenever you push changes to the `main` branch, this workflow will be triggered and your code will be pushed to your OCI registry.

For more information on configuring and customizing this GitHub Action, refer to the action's documentation.
