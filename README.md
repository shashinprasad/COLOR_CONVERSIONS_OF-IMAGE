# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:Choose an image and save it as a filename.jpg ,
### Step2:Use imread(filename, flags) to read the file.
### Step3:Use imshow(window_name, image) to display the image.
### Step4:Use imwrite(filename, image) to write the image.
### Step5:End the program and close the output image windows.
### Step6:Convert BGR and RGB to HSV and GRAY
### Step7:Convert HSV to RGB and BGR
### Step8:Convert RGB and BGR to YCrCb
### Step9:Split and Merge RGB Image
### Step10:Split and merge HSV Image

##### Program:
```
### Developed By: SHASHIN PRASAD S
### Register Number: 212222230144
```
<table>
  <tr>
    <td width=50%>


### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('pic.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('pic',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
#### OUTPUT:

![Screenshot 2024-02-16 094008](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/e4c54ad9-99b9-4670-a8e7-153a89a661f8)
</td>
</tr>



<tr>
  <td width=50%>


### ii)Write the image
```Python
    import cv2
    image=cv2.imread('pic.jpg',0)
    cv2.imwrite('nemo.jpg',image)
```
  </td>
  <td>

#### OUTPUT:

![Screenshot 2024-02-16 094051](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/89a4250d-57f1-463c-90d0-b03531c79154)
</td>
</tr> 
<tr> 
  <td width=50%>

### iii)Shape of the Image
```Python
     import cv2
    image=cv2.imread('pic.jpg',1)
    print(image.shape)
```
  </td> 
  <td>

#### OUTPUT:

![Screenshot 2024-02-16 094117](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/641a69b0-b34f-4773-ac65-2fa48471a8a4)
  </td>
  </tr> 
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
     import random
     import cv2
     image=cv2.imread('pic.jpg',1)
     image=cv2.resize(image,(400,400))
     for i in range (150,200):
       for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td width="50%">

#### OUTPUT:

![Screenshot 2024-02-16 094252](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/7f8353ce-c130-4ff8-a0bb-48d791549a81)
 </td>
 </tr>
 <tr>
  <td width=50%>

### v)Cut and paste portion of image
```Python
     import cv2
     image=cv2.imread('pic.jpg',1)
     image=cv2.resize(image,(400,400))
     tag =image[150:200,110:160]
     image[110:160,150:200] = tag
     cv2.imshow('partimage1',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
  </td>
  <td>

#### OUTPUT:

![Screenshot 2024-02-16 094343](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/b9a67b3f-cd07-4c31-92b1-2ac92a916761)
 </td>
 </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
    import cv2
    img = cv2.imread('pic.jpg',1)
    img = cv2.resize(img,(300,200))
    cv2.imshow('Original Image',img)

    hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
    cv2.imshow('BGR2HSV',hsv1)

    hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
    cv2.imshow('RGB2HSV',hsv2)

    gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    cv2.imshow('BGR2GRAY',gray1)

    gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
    cv2.imshow('RGB2GRAY',gray2)

    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
#### OUTPUT:

![Screenshot 2024-02-16 094432](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/8f8f77b6-a4bf-4fac-abe3-e4ebfcd82a1e)

### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('pic.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:

![Screenshot 2024-02-16 094531](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/c380e0a8-e8db-4515-86e2-d9b51dc1acc8)

### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('pic.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:

![Screenshot 2024-02-16 094634](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/acaf5328-ad18-43e9-8e43-7a1ee5cce6fe)

### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('pic.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:

![Screenshot 2024-02-16 094739](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/88b69ede-8e9c-477e-9b26-ac9ed982451d)

### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("pic.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:

![Screenshot 2024-02-16 094830](https://github.com/chaitanya18c/COLOR_CONVERSIONS_OF-IMAGE/assets/119392724/11b376db-9ef3-435d-9707-451c86fc0600)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







