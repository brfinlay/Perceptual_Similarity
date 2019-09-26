
from skimage.measure import compare_ssim as ssim
import matplotlib.pyplot as plt
import numpy as np
import pandas 
import PIL

# To import an image
from PIL import Image
b_1 = Image.open("/Users/brendafinlay/Documents/Cusack Lab/banana1.jpeg")
b_2 = Image.open("/Users/brendafinlay/Documents/Cusack Lab/banana2.jpg")
# Convert to Grayscalce ("L")
banana_1 = b_1.convert("L")
banana_2 = b_2.convert("L")

from matplotlib import image
from matplotlib import pyplot
from numpy import asarray
# Normalize image sizes (Parameters chosen through trial and error)
b1_resize = banana_1.resize((200, 200))
b2_resize = banana_2.resize((200, 200))
# Convert image file to float
data_b1 = asarray(b1_resize)
data_b2 = asarray(b2_resize)

#### Mean squared error ####
def mse(imageA, imageB):
   # for pixel in image:
    err = np.sum((imageA.astype(float) - imageB.astype(float)) ** 2)
    err = float(imageA.shape[0] * imageA.shape[1])
    return err
# Note the smaller the error, the more similar the images are

mse(data_b1, data_b2)

#Lets try the function on images of a lion and a tiger
lion = Image.open("/Users/brendafinlay/Documents/Cusack Lab/Lion.jpeg")
tiger = Image.open("/Users/brendafinlay/Documents/Cusack Lab/Tiger.jpeg")

l_gray = lion.convert("L")
t_gray = tiger.convert("L")
print(l_gray)
# Normalise size
lion_resize = l_gray.resize((200, 200))
tiger_resize = t_gray.resize((200, 200))
l_data = asarray(lion_resize)
t_data = asarray(tiger_resize)
mse(l_data, t_data)

# Compare banana and tiger
mse(data_b1, t_data)

#### Now for SSIM ####
def compare_images(imageA, imageB, title):
    m = mse(imageA, imageB)
    s = ssim(imageA, imageB)
    fig = plt.figure(title)
    plt.suptitle("MSE: %2f, SSIM: %2f" %(m, s))
    # Show imageA
    ax = fig.add_subplot(1, 2, 1)
    plt.imshow(imageA, cmap = plt.cm.gray) 
    plt.axis("off")
    #Show imageB
    ax = fig.add_subplot(1, 2, 2)
    plt.imshow(imageB, cmap = plt.cm.gray)
    plt.axis("off")
    plt.show()

compare_images(data_b1, data_b2, "Two Bananas")
compare_images(t_data, l_data, "Tiger & Lion")
compare_images(data_b1, t_data, "Banana & Tiger")
