# Coding3 Final Project
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
### Compare fake images trained at different image sizes

## Evaluation
## Reference
