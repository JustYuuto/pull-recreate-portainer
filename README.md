# Pull & Recreate to Portainer

This GitHub Action allows you to recreate a container and pull the latest image from a Docker registry in Portainer. It is useful for automating the deployment of updated images to your containers.

I created this for personal use (build the Docker image on GitHub Actions and deploy it to my server).

## Usage

```yaml
# ...
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Pull & Recreate to Portainer
      uses: justyuuto/pull-recreate-portainer@v1
      with:
        portainer_url: https://your-portainer-url
        portainer_access_token: ${{ secrets.PORTAINER_ACCESS_TOKEN }}
        container_name: your_container_name
```

## Inputs

| Input                    | Description                                                                                |
|--------------------------|--------------------------------------------------------------------------------------------|
| `portainer_url`          | The URL of your Portainer instance.                                                        |
| `portainer_access_token` | The access token for your Portainer instance. This should be stored as a secret in GitHub. |
| `container_name`         | The name of the container you want to recreate.                                            |
