# Taiyi stable-diffusion-webui
Stable Diffusion web UI for Taiyi

Make sure the requirement at least, very helpful.

- transformers>=4.24.0
- diffusers>=0.7.2

## step 1

Since Taiyi's text_encoder has been modified (BertModel vs CLIPTextModel), and webui currently only supports stable diffusion in English, it is necessary to use the webui project modified by Fengshenbang's own fork.

```
git clone https://github.com/IDEA-CCNL/stable-diffusion-webui.git
cd stable-diffusion-webui
```

## step 2

Run webui's own commands to check and install the environment, webui will pull down the required repositories in the stable-diffusion-webui/repositories directory, this process will take some time.

```
bash webui.sh
```

This script will then automatically download the required files, back up the original v1_inference.yaml file and replace it with the version needed to start our [taiyi model](https://huggingface.co/IDEA-CCNL/Taiyi-Stable-Diffusion-1B-Chinese-v0.1 ). 

**Notice that**, if you choose to redownload the Taiyi model, the total size of all the files needed is over 10G, the step:  
"Cloning taiyi_model into repositories/Taiyi-Stable-Diffusion-1B-Chinese-v0.1..." will take lots of time, please be patient.  

If you have already downloaded our whole Taiyi model in [https://huggingface.co/IDEA-CCNL/Taiyi-Stable-Diffusion-1B-Chinese-v0.1]() once, follow the path checker and choose "(2)move your downloaded Taiyi model path?", and move your downloaded model folder to ./repositories/Taiyi-Stable-Diffusion-1B-Chinese-v0.1.

After all the progress is done, the web-ui service will be started on port 12345.


<br>

You can run the following command to start the web-ui service.

```
bash webui.sh --listen --port 12345
bash webui.sh --ckpt repositories/Taiyi-Stable-Diffusion-1B-Chinese-v0.1/Taiyi-Stable-Diffusion-1B-Chinese-v0.1.ckpt --listen --port 12345
```
