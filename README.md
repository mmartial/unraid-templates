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

Important: To share content across all 3 Docker images, we must use a named Docker volume.
With a named volume, when you start a container and mount a new, empty named volume to a directory that already contains data within the container image, Docker automatically copies the existing files from the image into the volume.
This "auto-copy" feature does not work with bind mounts (linking a specific folder on your host: if you bind mount an empty host folder to /app/data, the container's folder will appear empty).
If the volume already contains data (e.g., from a previous run, an image update, etc), Docker will not overwrite it with the image's content; it will simply mount what is already in the volume. This is important for Hermes in particular, as it is the end-user's responsibility to docker volume rm hermes_shared_volume to get the content to update itself or use hermes update or the WebUI to update it.

- [Hermes Agent](https://github.com/nousresearch/hermes-agent) and its Dashboard
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool itself or the underlying Docker container, use [https://github.com/nousresearch/hermes-agent/issues](https://github.com/nousresearch/hermes-agent/issues)

- [Hermes WenUI](https://github.com/nesquena/hermes-webui)
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool itself or the underlying Docker container, use [https://github.com/nesquena/hermes-webui/issues](https://github.com/nesquena/hermes-webui/issues)

## Misc:  Unraid template howto

[https://www.gkr.one/kb-unraid-dev]https://www.gkr.one/kb-unraid-dev)