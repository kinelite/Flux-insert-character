## A Workflow For Transfering Subjects into New Pictures While Retaining Features


![V21](https://github.com/user-attachments/assets/7a1a7d13-a3fb-4eba-b0d5-f10cef76e57e)

Model required
- Flux1-fill-dev
- Flux1-redux-dev
- InsightFace (innswapper128) and ReActor.

How to Use
1. Import the workflow to ComfyUI
2. Make sure you install all missing nodes.
3. If you have never used ReActor before, you will need to install it manually. (Installing from ComfyUI Manager alone is NOT sufficient.) If you already got ReActor working before, you can skip to step 11.

4. Go to ComfyUI Manager, click uninstall or disable ReActor from the manager. (This one implements nsfw detector forced by Github and it causes technical problems to several people.)
5. Go to https://codeberg.org/Gourieff/comfyui-reactor-node, scroll down for the Troubleshooting (I) section, follows its instruction RELIGIOUSLY.
6. After installing insightface-0.7.3-cp31X-cp31X-win_amd64.whl (X is your python version), download inswapper_128.onnx from https://huggingface.co/ezioruan/inswapper_128.onnx/tree/main and put it into the folder \ComfyUI\models\insightface (If you don't have one, just create a new folder and rename it to that.)
7. Go to the folder \ComfyUI\models\facerestore_models (create one if you don't have.) and check if you have GFPGANv1.4.onnx there. If you don't have one, you can download from  https://huggingface.co/datasets/Gourieff/ReActor/tree/main/models/facerestore_models
8. Go to the folder \ComfyUI_windows_portable\python_embeded and type CMD in the directory to open command prompt, then type ```python.exe -m pip install onnxruntime```
9. After finished installing onnxruntime, go to \ComfyUI\custom_nodes and type CMD in the file directory to open the command prompt. Enter ```git clone https://codeberg.org/Gourieff/comfyui-reactor-node.git``` and let it install.
10. Voila! you have installed ReActor. Take a moment to breath.
  
11. Load images of the subject, the face (not required if not a person but you need to click disable Face Swap Unit in the Prompt Card), and the destination.
12. Mark the area in the destination image that you want your subject to insert.
13. Type the Prompt.
14. Click Queue.
15. If you are not satisfied with the result, see the Tips notes in some nodes that I found impactful to the results. You will need to experiment on it. There is no universal setting.
