# Unraid Community Application templates

## ComfyUI Nvidia Docker

- [ComfyUI Nvidia Docker](https://github.com/mmartial/ComfyUI-Nvidia-Docker) ([templates/ComfyUI-Nvidia-Docker.xml](templates/ComfyUI-Nvidia-Docker.xml))
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with container itself, use [https://github.com/mmartial/ComfyUI-Nvidia-Docker/issues](https://github.com/mmartial/ComfyUI-Nvidia-Docker/issues)
  - For issues with ComfyUI itself, use [https://github.com/comfy-org/ComfyUI/issues](https://github.com/comfy-org/ComfyUI/issues)

## Smart ComfyUI Gallery

- [Smart ComfyUI Gallery](https://github.com/biagiomaf/smart-comfyui-gallery) ([templates/smart-comfyui-gallery.xml](templates/smart-comfyui-gallery.xml))
  - Check the project's documentation for usage information.
  - For Unraid templates issues use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool itself, use [https://github.com/biagiomaf/smart-comfyui-gallery/issues](https://github.com/biagiomaf/smart-comfyui-gallery/issues)

## Traefik Kop

- [Traefik Kop](https://github.com/jittering/traefik-kop) ([templates/traefik-kop.xml](templates/traefik-kop.xml))
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool itself, use [https://github.com/jittering/traefik-kop/issues](https://github.com/jittering/traefik-kop/issues)

## Hermes

(Advanced Deployment/Virtual Machine alternative: if you are considering running Hermes in its own VM, check [Hermes in a VM](https://www.gkr.one/blg-20260405-openclaw-hermes))

Important: To share content across all 3 Docker images, we must use a named Docker volume.
With a named volume, when you start a container and mount a new, empty named volume to a directory that already contains data within the container image, Docker automatically copies the existing files from the image into the volume.
This "auto-copy" feature does not work with bind mounts (linking a specific folder on your host: if you bind mount an empty host folder to /app/data, the container's folder will appear empty).
If the volume already contains data (e.g., from a previous run, an image update, etc), Docker will not overwrite it with the image's content; it will simply mount what is already in the volume. This is important for Hermes in particular, as it is the end-user's responsibility to docker volume rm hermes_shared_volume to get the content to update itself or use hermes update or the WebUI to update it.

The containers MUST be started in the following order:

1. Hermes Agent: this will generate the `hermes_shared_volume` required by the subsequent containers to work
2. Hermes Dashboard: to configure your API keys, ...
3. Hermes WebUI: always start last, it REQUIRES the `hermes_shared_volume` to exist and be populated to work

To start a fresh deployment/repair a broken one, you will need to get a shell on your Unraid system and delete the docker shared volume using `docker volume rm hermes_shared_volume`

To get access to the `hermes` command line (for configuration, update, etc):

```bash
# From unraid host shell
docker exec --user 99:100 -it Hermes-Agent bash

# Within container
source .venv/bin/activate
hermes
# hermes setup
# hermes update
```

Unraid auto-update note: The shared volume is required for Hermes WebUI to work, and it provides an update mechanism for the Agent/Dashboard and itself (you may still have to restart the container after the update). Because Docker shared volumes that already contain content will not have their content updated when a new data source is provided, if you have your container images set to auto-update, disable it for this stack. 

Available components:

- [Hermes Agent](https://github.com/nousresearch/hermes-agent) and its Dashboard
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool itself or the underlying Docker container, use [https://github.com/nousresearch/hermes-agent/issues](https://github.com/nousresearch/hermes-agent/issues)

- [Hermes WebUI](https://github.com/nesquena/hermes-webui)
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool itself or the underlying Docker container, use [https://github.com/nesquena/hermes-webui/issues](https://github.com/nesquena/hermes-webui/issues)

## Misc: Unraid template howto

[My Unraid Template Development notes](https://www.gkr.one/kb-unraid-dev)
