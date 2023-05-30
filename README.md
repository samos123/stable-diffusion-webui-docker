# Stable Diffusion Webui Docker & K8s install

This is based of https://github.com/AbdBarho/stable-diffusion-webui-docker with only some minor changes.

## How to
Build and run the image:
```sh
export IMAGE_TAG=sd-web-ui-docker
docker build -t $IMAGE_TAG .
DOCKER_BUILDKIT=1 docker run --name sd -p 7860:7860 -d --runtime=nvidia --gpus all $IMAGE_TAG
```

Check the logs and ensure stable diffusion UI is running:
```
docker logs sd
```
You should see a line that shows `Running on local URL:  http://0.0.0.0:7860`

Now you can go to your browser at url [http://localhost:7860](http://localhost:7860) and
you should see the Stable Diffusion Web UI.


## Guides
- [Build and deploy the Stable Diffusion Web UI image on GCE T4 GPU](https://samos-it.com/posts/deploying-stable-diffusion-web-ui-with-docker-on-gce-t4-vm.html)
- [Deploy Stable Diffusion Web UI on GKE Autopilot T4 Spot VM](https://samos-it.com/posts/deploying-stable-diffusion-gke-autopilot.html)
