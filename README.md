Aging your picture: Face Aging with GANs
it is a deep learning model for face aging, using CycleGAN to translate young faces to older versions and vice versa. This model enables realistic, high-speed aging effects on facial images without requiring face detection, making it ideal for real-time applications.

Table of Contents
Overview
Examples
Performance
Quick Start
Running Inference
Training Your Own Model
Data Preparation
Configuring and Training
Monitoring with TensorBoard
Acknowledgments
Overview
Aging is a CycleGAN-based model designed for transforming young faces into older ones and vice versa. The model achieves high frame rates and can process images without requiring face detection, as long as the input contains a central face region of 256x256 within a 512x512 image.

Examples
Top row: Input (young face)
Bottom row: Output (aged face from GAN)



Performance
Speed: 66 FPS on an NVIDIA GTX1080 for 512x512 images.
Detection-Free: No need for a face detection pipeline; the model works with any 512x512 image containing a face of size 256x256 or larger.
Quick Start
Running Inference
To apply the pre-trained model on your images:

bash
Copy code
python infer.py --image_dir 'path/to/your/image/directory'
Training Your Own Model
Data Preparation
To train Fast-AgingGAN, you’ll need to preprocess your dataset. Supported datasets include CACD and UTK Faces. Use the preprocessing scripts available in the preprocessing/ directory:

Preprocess CACD Dataset:
bash
Copy code
python preprocessing/preprocess_cacd.py --image_dir '/path/to/cacd/images' --metadata '/path/to/cacd/metadata/file' --output_dir 'path/to/save/processed/data'
Preprocess UTK Faces Dataset:
bash
Copy code
python preprocessing/preprocess_utk.py --data_dir '/path/to/utk/images' --output_dir 'path/to/save/processed/data'
Configuring and Training
Update Configurations: Modify configs/aging_gan.yaml to set the correct paths to your preprocessed data. Adjust other hyperparameters if needed.
Run Training: Start the training process:
bash
Copy code
python main.py
Monitoring with TensorBoard
To monitor the training progress, including loss values and generated images, use TensorBoard:

bash
Copy code
tensorboard --logdir=lightning_logs --bind_all
Acknowledgments
This project is based on CycleGAN and leverages various face aging datasets, including CACD and UTK Faces. Special thanks to contributors in the deep learning and GANs community for making resources and datasets publicly available.