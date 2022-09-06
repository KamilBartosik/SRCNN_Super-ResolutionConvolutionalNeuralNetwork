# SRCNN_Super-ResolutionConvolutionalNeuralNetwork
This project is the practical part of my Bachelor of Science thesis `Enhancement of aerial photographies' spatial resolution using convolutional neural networks` defended on 5.02.2021 on Warsaw University of Technology [[Repo]](https://repo.pw.edu.pl/info/bachelor/WUTd0c99a6433524f3195c5fa158a72e3ac/)

Thesis got awarded with 2nd place in nationwide competition for the best thesis in geodesy and cartography [[government geoportal]](https://www.geoportal.gov.pl/o-geoportalu/aktualnosci/-/asset_publisher/HCHq0YGNRszn/content/04-04-2022-konkurs-na-najlepsza-prace-dyplomowa-obronione-na-kierunku-geodezja-i-kartografia-w-2020-2021-roku?redirect=%2Fo-geoportalu%2Faktualnosci%3Fp_p_id%3D101_INSTANCE_HCHq0YGNRszn%26p_p_lifecycle%3D0%26p_p_state%3Dnormal%26p_p_mode%3Dview%26p_p_col_id%3Dcolumn-1%26p_p_col_count%3D1%26_101_INSTANCE_HCHq0YGNRszn_delta%3D3%26_101_INSTANCE_HCHq0YGNRszn_keywords%3D%26_101_INSTANCE_HCHq0YGNRszn_advancedSearch%3Dfalse%26_101_INSTANCE_HCHq0YGNRszn_andOperator%3Dtrue%26p_r_p_564233524_resetCur%3Dfalse%26_101_INSTANCE_HCHq0YGNRszn_cur%3D3&inheritRedirect=true) [[gisplay]](https://gisplay.pl/geo/9827-wyniki-konkursu-na-na-najlepsza-prace-dyplomowa-z-geodezji-i-kartografii-edycja-2020-21.html) *websites in polish language*

**_Code cannot be shared due to copyrights reasons but the results and brief decription of the experiment are available below_**

## Introduction
Point of the experiment was to create algorithm that is capable of enhancing the aerial images' spatial resolution from GSD=10cm to GSD=5cm (scale=2). Moreover the scales 3, 4, 6 were also tested but with smaller dataset. To achieve such thing, architecture of the created network was a bit upraged convolutional neural network that instead of returing some detection/categorization result returned an input image with enhanced resolution. My work was inspired by [Dong et al., 2015](https://arxiv.org/abs/1501.00092).

## Training and performance
For the main task of image resolution enhancement by the scale of 2 the five different datasets' sizes were used (315, 450, 1350, 2700, 4500 images). Thanks to that the figure that shows how resolution enhancement is getting better (PSNR [dB]) over bigger datasets were created:

![alt text](https://github.com/KamilBartosik/SRCNN_Super-ResolutionConvolutionalNeuralNetwork/blob/main/training_figures/Dataset_size.png "Size of the dataset")

The process of the best performing training with scale of 2 and dataset of 4500 images (600x450 px):

![alt text](https://github.com/KamilBartosik/SRCNN_Super-ResolutionConvolutionalNeuralNetwork/blob/main/training_figures/Training_MSE.png "SRCNN training (MSE per epoch)")
![alt text](https://github.com/KamilBartosik/SRCNN_Super-ResolutionConvolutionalNeuralNetwork/blob/main/training_figures/Training_PSNR.png "SRCNN training (PSNR per epoch)")

Difference of PSNR between train and test sets:
Scale|Image nb in dataset|PSNR [dB] training|PSNR [dB] test
:---: | :---: | :---: | :---:
2 | 4500 | 37.12 | 36.43
3 | 450 | 32.26 | 32.02
4 | 450 | 30.44 | 30.65
6 | 450 | 28.23 | 28.72

Numeric results (PSNR and SSIM):
Scale|PSNR [dB] input|SSIM input|PSNR [dB] output|SSIM output
:---: | :---: | :---: | :---: | :---:
2 | 34.41 | 0.8151 | 36.43 | 0.8439 
3 | 30.45 | 0.5792 | 32.02 | 0.6307
4 | 28.61 | 0.4997 | 30.65 | 0.5100
6 | 26.30 | 0.3213 | 28.72 | 0.3313

## Results
TBD
