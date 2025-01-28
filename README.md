## Flux Insert Character
A ComfyUI workflow for inserting a subject (character or stuff) into a new pictures while retaining its feature. It will automatically adapt perspective, light and color tones, and can even change posture according to text prompt. Scroll down for examples.

### LATEST UPDATE: Flux-Insert-Character-V5 (renamed from WorkflowV5 to avoid confusion.)

### Changelog V5:
![V5](https://github.com/user-attachments/assets/54acb11e-afed-4cfa-b9a4-8e3886da6ef6)

- Switch the Inpaint Stitch node and the Face Swap Unit, so the face swap model is less confused after stitching.
- Remove dependency on SDXL in the Upscaler Unit. Much better image fidelity and less RAM required, but longer render time if enabled. (Disabled by default.)

### Changelog V4:
![V4](https://github.com/user-attachments/assets/dd21c26b-8c06-496e-8cba-6626b9132f56)

- Overhaul the whole workflow logic. Now, it will adhere to the prompt more.
- Add Upscaler Unit to heal pixelating effect. Require SDXL 1.0 (Jugglenaut XI) (https://civitai.com/models/133005/juggernaut-xl)
- Require upscaler model 4x_NMKD-Siax_200k.pth (can be download from ComfyUI Manager in download model section.)
- Change default Inpaint Crop and Inpaint Stitch rescale algorithm to bicubic and bislerp, respectively.

### Changelog V3:
![V3](https://github.com/user-attachments/assets/cfab55df-ba20-4950-828c-fd0f10f50754)
- Fixed some issues with LayerColor: Brightness & Contrast node. (replaced with another version.)
- Fixed CropMask node.
- Added ReActer FaceBooster node.
- Removed Image Sharpen node. It worsens image quality.
- Increase context_expand_factor in Inpaint Crop node. More context will be considered in by the models.

### EXAMPLES
![EX1](https://github.com/user-attachments/assets/27167947-af92-4082-912f-5a83c7a8c946)
![EX2](https://github.com/user-attachments/assets/59df0f22-c69f-4fae-bf64-699d15ab7ebc)
![EX3](https://github.com/user-attachments/assets/a36b648a-b646-483b-a8cf-8738de266e0b)
![EX4](https://github.com/user-attachments/assets/2a8c6a97-729a-4764-9c04-b8636ce9a7eb)
![EX5](https://github.com/user-attachments/assets/e9b1fa15-289c-4452-b5c1-94163ef370a8)
![V21](https://github.com/user-attachments/assets/7a1a7d13-a3fb-4eba-b0d5-f10cef76e57e)



Models required
- Flux1-fill-dev
- Flux1-redux-dev
- InsightFace (inswapper_128) and ReActor.
  
How to Start
1. Import the workflow to ComfyUI
2. Make sure you install all missing nodes.
3. If you have never used ReActor before, you will need to install it manually. (Installing from ComfyUI Manager alone is NOT sufficient.) If you already got ReActor working before, you can skip to step 11.

4. Go to ComfyUI Manager, click uninstall or disable ReActor from the manager. (This one implements nsfw detector forced by Github and it causes technical problems to several people.)
5. Go to https://codeberg.org/Gourieff/comfyui-reactor-node, scroll down for the Troubleshooting (I) section, follows its instruction RELIGIOUSLY.
6. After installing insightface-0.7.3-cp31X-cp31X-win_amd64.whl (X is your python version), download inswapper_128.onnx from https://huggingface.co/ezioruan/inswapper_128.onnx/tree/main and put it into the folder \ComfyUI\models\insightface (If you don't have one, just create a new folder and rename it to that.)
7. Go to the folder \ComfyUI\models\facerestore_models (create one if you don't have.) and check if you have GFPGANv1.4.onnx and GPEN-BFR-512.onnx there. If you don't have one, you can download from  https://huggingface.co/datasets/Gourieff/ReActor/tree/main/models/facerestore_models
8. Go to the folder \ComfyUI_windows_portable\python_embeded and type ```cmd``` in the directory to open command prompt, then type ```python.exe -m pip install onnxruntime```
9. After finished installing onnxruntime, go to \ComfyUI\custom_nodes and type ```cmd``` in the file directory to open the command prompt. Enter ```git clone https://codeberg.org/Gourieff/comfyui-reactor-node.git``` and let it install.
10. Voila! you have installed ReActor. Take a moment to breath.
  
11. Now, open the ComfyUI. You can now use the workflow.
12. To use it, load images of the subject, the face (not required if not a person but you need to click disable Face Swap Unit in the Prompt Card), and the destination.
13. Mark the area in the destination image that you want your subject to insert.
15. Type the Prompt.
16. A ready-to-run input should look like this:
    ![Screenshot 2025-01-27 180150](https://github.com/user-attachments/assets/8bfe6761-e216-41c6-91fb-1d1e634af64b)
18. Click Queue.
19. If you are not satisfied with the result, see the Tips notes in some nodes that I found impactful to the results. You will need to experiment on it. There is no universal setting.
