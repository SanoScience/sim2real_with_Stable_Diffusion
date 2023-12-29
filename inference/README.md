UPDATE: ControlNet pipelines are out  
TODO: move code to diffusers

---

We use webui for inference since currently it is a recommended by official ControlNet repository way to merge ControlNet weights with Custom SD weights:  
https://github.com/lllyasviel/ControlNet/discussions/12  

To run inference we fisrt have to run WebUI + ControlNet extension
- https://github.com/AUTOMATIC1111/stable-diffusion-webui   
- https://github.com/Mikubill/sd-webui-controlnet  
Please follow the guidance on official repository explaining how to run webui, extensions and where to put ControlNet models.  
To use WebUI API:
- https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/API

We use following ControlNet 1.1 checkpoints:
- https://huggingface.co/lllyasviel/ControlNet-v1-1/resolve/main/control_v11p_sd15_softedge.pth
- https://huggingface.co/lllyasviel/ControlNet-v1-1/resolve/main/control_v11f1e_sd15_tile.pth 

For inference we use Dreambooth model trained with Diffusers package.   
**Please remember, you have to first convert diffusers_checkpoint to original_stable_diffusion_checkpoint. Then you have to place your checkpoint in `stable-diffusion-webui/models/Stable-diffusion/` folder. Both these operations can be done as a last step in `training/train_dreambooth.ipynb`.**   
Next, select proper checkpoint in WebUI (upper left corner). Having the server running, you can run inference notebook.

