Data avaliable here: https://drive.google.com/file/d/1oMOcvgn-pDfRAqJvbp1soz_IwYLYib7v/view?usp=drive_link. 

"Training and Inference" file includes the training and inference pipeline. 
If using local environment to run the code, please ignore the first three cells and start by installing the corresponding dependencies.

In the training pipeline, please set the path of the dataset and the LoRA saving path. The "condscale" parameter is used to adjust the control intensity of different control map. 
In the "LoRA Configuration" section, "target_modules" parameter is used to control the inject location. The default setting select the up-sampling layers and mid-sampling layers as inject location. 
The "get_down_blocks_linear_modules" function can select the down-sampling layers if needed. Replace the "target_location" with ["to_q","to_k","to_v","to_out.0"] can select all available layer. 
The loss configuration section allows you to adjust the weights of different losses. The default settings will automatically adjust the loss weight based on the style text.

In the inference pipeline, please set the LoRA path to load trained LoRA matrix, the "source_image_path" is the input image path,  the "result_path" is the location to save output sketch. 
Change the style prompt to achieve generation of different styles. The "cond_scale" parameter is used to adjust the control intensity. Please ensure that it is consistent with the one used in the training.
The "inference" section provides the code for fixing the seeds.

"Evaluation" file for calculate the evaluation metric.Please set the paths for the source image and the target image.
