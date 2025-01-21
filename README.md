## A Workflow For Transfering Subjects into New Pictures While Retaining Features


![V21](https://github.com/user-attachments/assets/7a1a7d13-a3fb-4eba-b0d5-f10cef76e57e)

Model required
- Flux1-fill-dev
- Flux1-redux-dev
- InsightFace (innswapper128) and ReActor.

How to use
1. Import the workflow to ComfyUI
2. Make sure you install all missing nodes.
3. If you have never used ReActor or innswapper128 before, you will need to install manually. (Installing from ComfyUI Manager alone is NOT sufficient.) See more at https://github.com/Gourieff/ComfyUI-ReActor
4. Load images of the subject, the face (not required if not a person but you need to click disable Face Swap Unit in the Prompt Card), and the destination.
5. Mark the area in the destination image that you want your subject to insert.
6. Insert the Prompt.
7. Click Run.
8. If you are not satisfied with the result, see the Tips notes in some nodes that I found impactful to the results. You will need to experiment on it. There is no universal setting.
