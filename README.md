# Unraid Community Application templates

## ComfyUI Nvidia Docker

- [ComfyUI Nvidia Docker](https://github.com/mmartial/ComfyUI-Nvidia-Docker) ([templates/ComfyUI-Nvidia-Docker.xml](templates/ComfyUI-Nvidia-Docker.xml))
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the container, use [https://github.com/mmartial/ComfyUI-Nvidia-Docker/issues](https://github.com/mmartial/ComfyUI-Nvidia-Docker/issues)
  - For issues with ComfyUI, use [https://github.com/comfy-org/ComfyUI/issues](https://github.com/comfy-org/ComfyUI/issues)

## Smart ComfyUI Gallery

- [Smart ComfyUI Gallery](https://github.com/biagiomaf/smart-comfyui-gallery) ([templates/smart-comfyui-gallery.xml](templates/smart-comfyui-gallery.xml))
  - Check the project's documentation for usage information.
  - For Unraid templates issues use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool, use [https://github.com/biagiomaf/smart-comfyui-gallery/issues](https://github.com/biagiomaf/smart-comfyui-gallery/issues)

## Traefik Kop

- [Traefik Kop](https://github.com/jittering/traefik-kop) ([templates/traefik-kop.xml](templates/traefik-kop.xml))
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool, use [https://github.com/jittering/traefik-kop/issues](https://github.com/jittering/traefik-kop/issues)

## Hermes

**20260528 Note**: More updated guidelines for deployment were integrated into the template. Please see https://github.com/mmartial/unraid-templates/issues/8#issuecomment-4570170067 for details. This is also applicable if you updated the container following ANY hermes agent container update.

**20260510 Note**: New guidelines for deployment https://hermes-agent.nousresearch.com/docs/user-guide/docker allowed us to remove the Dashboard container. If you installed before this release, delete both containers and reinstall the agent. A note on the TUI: after some permission issues are resolved (https://github.com/NousResearch/hermes-agent/issues/23402), the TUI within the Dashboard should be functional.

(Advanced Deployment/Virtual Machine alternative: if you are considering running Hermes in its own VM, check [Hermes in a VM](https://www.gkr.one/blg-20260405-openclaw-hermes))

Always start the "Hermes Agent" first before starting the other containers.

To get access to the `hermes` command line (for configuration, update, etc):

```bash
# From unraid host shell
# use "docker container ls" to find the name of your container (if the container name differs)
docker exec --user 99:100 -it Hermes-Agent bash

# Within container
source .venv/bin/activate
hermes
# hermes setup
# hermes update
```

Available components:

- [Hermes Agent](https://github.com/nousresearch/hermes-agent) and its Dashboard
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool or the underlying Docker container, use [https://github.com/nousresearch/hermes-agent/issues](https://github.com/nousresearch/hermes-agent/issues)

- [Hermes Workspace](https://github.com/outsourc-e/hermes-workspace)
  - Check the project's documentation for usage information.
  - For Unraid templates issues, use [https://github.com/mmartial/unraid-templates/issues](https://github.com/mmartial/unraid-templates/issues)
  - For issues with the tool or the underlying Docker container, use [https://github.com/outsourc-e/hermes-workspace/issues](https://github.com/outsourc-e/hermes-workspace/issues)

## Deprecated

Templates can still be found in the `templates/obsolete` folder.

- 20260629: "Hermes WebUI" template

## Misc: Unraid template howto

[My Unraid Template Development notes](https://www.gkr.one/kb-unraid-dev)
