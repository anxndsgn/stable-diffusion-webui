# Taiyi stable-diffusion-webui
Stable Diffusion web UI for Taiyi

Make sure the requirement at least, very helpful.

- transformers>=4.24.0
- diffusers>=0.7.2

## step 1

Since Taiyi's text_encoder has been modified (BertModel vs CLIPTextModel), and webui currently only supports stable diffusion in English, it is necessary to use the webui project modified by Fengshenbang's own fork.

```
git clone git@github.com:IDEA-CCNL/stable-diffusion-webui.git
cd stable-diffusion-webui
```

## step 2

Run webui's own commands to check and install the environment, webui will pull down the required repositories in the stable-diffusion-webui/repositories directory, this process will take some time.

```
bash webui.sh
```

This script will then automatically download the required files, back up the original v1_inference.yaml file and replace it with the version needed to start our [taiyi model](https://huggingface.co/IDEA-CCNL/Taiyi-Stable-Diffusion-1B-Chinese-v0.1 ). After all the progress is done, the web-ui service will be started on port 12345.

After that, you can run the following command to to start the web-ui service

```
python launch.py --ckpt local_path/Taiyi-Stable-Diffusion-1B-Chinese-EN-v0.1.ckpt --listen --port 12345
```
