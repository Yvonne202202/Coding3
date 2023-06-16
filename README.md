# Coding3 Final Project
Project URL: https://drive.google.com/drive/folders/1qek9t_AS9DHp-xvxtd1AsjAWqHWOUDxC?usp=drive_link
<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/下载 (5).png" width="100%">
</div>

### Source of the data set
URL: https://www.kaggle.com/datasets/peymannejat/ovarian-cancer-pathology-patches
<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/1.png" width="80%">
</div>
This dataset contains images associated with human cells. I selected 600 images from this database as the real images. I would like to create works of art related to cells because I believe that the morphology and texture of cells in microstructures have a unique visual effect. These patterns show beauty even though they are made by nature, which is the wonder of life.

### Code reference
URL: https://github.com/ayan-aji-nair/art-generation-gan

The reference code used DCGAN to generate 64x64 and 128x128 color Chinese art images.This author has successfully trained high quality images that show clear landscapes and floral patterns.

## The process of project development
### Train the model on the cell dataset
I first ran the reference code in Jupyter. The way to read the data set in the source code is to extract 'data.zip' and put the extracted contents into the 'images' folder, thus reading the contents of the 'images' folder. I got an error while running this step. So I asked ChatGPT for help.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/2.jpg" width="60%">
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/3.png" width="60%">
</div>

I need to ensure that the dataset files are in the right place. So, I created the 'images' folder in the same directory as the code and placed the dataset I was using inside the 'images' folder. I removed the code used to extract the dataset and create the images folder, and changed the path to read the dataset to '.images/data/'. After making these changes, I was able to load the dataset correctly.

I got another error when I ran the saved trained model status word. 

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/4.png" width="60%">
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/6.png" width="60%">
</div>

According to ChatGPT, 'torch.save(gen.state_dict(), params_path + '/van-gogh-gen-64-650')' is used to gen the generator model's status word into a file. 'gen.load_state_dict(torch.load(params_path + '/model-gen-64-850', map_location=torch.device('cpu')))' is used to load the model status word. I get an error when I use the save path of the source code. I changed the save path to the current path to solve this problem.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/7.png" width="60%">
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/8.png" width="60%">
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/9.png" width="60%">
</div>
After modifying these, the source code can be successfully run down. And I was able to load the replacement data set successfully.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/10.png" width="80%">
</div>

### Compare fake images trained at different image sizes
The reference code contains two code files with image sizes of 64 and 128. To more directly observe the training effect of images of different sizes, I added code after the training loop to create a folder named 'generated_images' and 'generated_images_128' in the current directory to save the fake images generated by each epoch.
<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/11.png" width="60%">
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/12.png" width="60%">
</div>

After running, I could see the generated fake image in real time in the folder.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/12.jpg" width="60%">
</div>

When the image size is 64 pixels, the resulting fake image is only 8kb in size. I found the images to be very low definition.
<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/13.png" width="80%">
</div>

When the number of iterations is 50,150,250,350,450,550,650, the observed false images are as follows:
<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_150.png" width="10%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_250.png" width="10%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_350.png" width="10%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_450.png" width="10%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_550.png" width="10%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_650.png" width="10%">
</div>

When the image size is 128, the sharpness of the fake images are greatly improved.


<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/14.png" width="80%">
</div>

When the number of iterations is 50,150,250,350,450,550,650, the observed false images are as follows:

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_150 2.png" width="20%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_250 2.png" width="20%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_350 2.png" width="20%">
  
 <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_450 2.png" width="20%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_550 2.png" width="20%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_650 2.png" width="20%">
</div>

When epoch is 282 and 284, the trained images looks like a lady carrying a dress.
<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_282.png" width="20%"> <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/generated_image_284.png" width="20%">
</div>

To get a higher quality image, I changed the image size to 256.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/15.png" width="80%">
</div>

My code was modified based on an image size of 128 pixels, so I modified the network architecture of the model. Since the size of the input image doubled, I added a convolutional layer to the discriminator. In addition to this, I also added a deconvolution layer to the generator.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/16.jpg" width="45%">   <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/17.jpg" width="45%">
</div>


However, even after changing the image size to 256, the model still does not converge after 650 epochs. I need to perform more iterations to achieve better results. Due to the high number of iterations, I did not have enough time for training.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/18.png" width="100%">
</div>

To expedite the training process, I attempted to run the code using Colab's GPU. After uploading the folder to Google Drive, I needed to adjust the path where the dataset was loaded to the path of the dataset in the cloud repository in order to load the dataset correctly.

<div align=center>
  <img src="https://github.com/Yvonne202202/Coding3/blob/main/images/19.png" width="80%">
</div>

## Evaluation
Convergence is an ongoing process that necessitates numerous training iterations to evaluate the model. Running 650 epoch programs on my local Jupyter took nearly 20 hours, and I encountered several interruptions while training with Colab due to inadequate GPU allocation. Consequently, I could not train the model sufficiently for this project. Nonetheless, through continuous attempts, I acquired a deeper understanding of deep learning. Although I do not consider DCGAN as the optimal framework for creating art, it's still worth exploring.

## Reference
Turn Your Computer into an Artist with AI: https://medium.com/mlearning-ai/turn-your-computer-into-an-artist-with-ai-8a58014bb5d4

Guide to Generative Adversarial Networks (GANs) in 2023: https://viso.ai/deep-learning/generative-adversarial-networks-gan/

DCGAN TUTORIAL: https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html
