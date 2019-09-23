# Perceptual_Similarity

This script allows you to measure the perceptual similarity between two images, using Python imaging library's (PIL) **"structural similarity index"** (SSIM).

SSIM measures the perceptual difference between two images by quantifying the **perceived change** in **image structure**. SSIM processing is more similar to human perception compared to perceptual distance metrics e.g. the mean squared error (MSE), and peak signal to noise ratio (PSNR).

A SSIM score of 1 = perfect percetual similarity (www.imatest.com/docs/ssim/)

Two images of a banana were compared with an expected high perceptual similarity score. Images of a lion and tiger were compared and expected to score moderate perceptual similarity.
