Developed By : Pavithra D

Register Number : 212223230146

# COLOR_CONVERSIONS_OF-IMAGE

AIM

To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.

Software Required:
Anaconda - Python 3.7

Algorithm:
Step1:
Choose an image and save it as a filename.jpg ,

Step2:
Use imread(filename, flags) to read the file.

Step3:
Use imshow(window_name, image) to display the image.

Step4:
Use imwrite(filename, image) to write the image.

Step5:
End the program and close the output image windows.

Step6:
Convert BGR and RGB to HSV and GRAY

Step7:
Convert HSV to RGB and BGR

Step8:
Convert RGB and BGR to YCrCb

Step9:
Split and Merge RGB Image

Step10:
Split and merge HSV Image

Program:
1) Read and display the image
```
image = cv2.imread('lokesh2.jpg')
image_resized = cv2.resize(image, (500,500))
plt.imshow(image_resized)
plt.show()
```
![image](https://github.com/user-attachments/assets/cb244456-5a9f-4c96-bcac-be0cdc67e49c)


 2)Draw Shapes and add text
 
a)Draw line from top-left to the bottom-right
```
image1=image_resized.copy()
res = cv2.line(image1,(0,0),(500,500),(200,100,205),10)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows() 
```  
![image](https://github.com/user-attachments/assets/43976827-e851-43db-bc40-41c6d0576ec1)


b) Draw a circle at the centre of the image
```
image2=image_resized.copy()
res1=cv2.circle(image2,(250,225),150,(240,0,0),10)
cv2.imshow('Image Window', res1)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/77c9745e-92e7-4087-b2e7-a14ac1637df8)

c)Draw a rectangle around a specific region in interest
```
image3=image_resized.copy()
start=(180,150)
stop=(320,400)
color=(100,255,100)
thickness=10
res2=cv2.rectangle(image3,start,stop,color,thickness)
cv2.imshow('Image Window', res2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/9180f2f1-c7e0-44bd-bcb2-6fe28a9bd67e)


d)Add the text "OpenCV Drawing" at the top-left corner of the image
```
image4=image_resized.copy()
org=(10,30)
fontface=cv2.FONT_HERSHEY_SIMPLEX
fontScale=1
res3=cv2.putText(image4,"OpenCV Drawing",org,fontface,fontScale,(255,0,0),2)
cv2.imshow('Image Window', res3)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/94c0ae55-7827-4ff8-bbc3-a4af8e14c15a)

3)Image color conversion
```
a) RGB TO HSV
image5=image_resized.copy()
hsv_image = cv2.cvtColor(image5, cv2.COLOR_RGB2HSV)
cv2.imshow('HSV Image', hsv_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/b4d11221-1786-4588-aa1f-c981f0957819)

b) RGB TO GRAY
```
image6=image_resized.copy()
gray_image = cv2.cvtColor(image6, cv2.COLOR_RGB2GRAY)
cv2.imshow('GrayScale Image', gray_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/5bf9b856-67d2-4b56-9862-f75b674c2d70)

c) RGB TO YCrCb
```
image7=image_resized.copy()
ycrcb_image = cv2.cvtColor(image7, cv2.COLOR_RGB2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/3b9146c9-cea9-45ce-97ea-5e0a611fddb9)

d)HSV TO RGB
```
rgb_image=cv2.cvtColor(hsv_image, cv2.COLOR_HSV2RGB)
cv2.imshow('RBG Image', rgb_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/46386318-4574-48b6-99dd-992983670428)

4) Access and manipulate image pixels
   
a)Accessing pixel at cooridinate (100,100)
```
image8=image_resized.copy()
(b,g,r)=image8[100,100]
print(f"Red: {r}\nGreen: {g}\nBlue: {b}")
```
![image](https://github.com/user-attachments/assets/1f0fc872-a21d-4055-8f3b-79f1ac767f76)

b)Modify the color of the pixel at coordinate(200,200) to white
```
image8[200,200]=(255,255,255)
(b,g,r)=image8[200,200]
print(f"Red: {r}\nGreen: {g}\nBlue: {b}")
```
![image](https://github.com/user-attachments/assets/45bb0c0c-1d76-4a7e-919a-4343c98b51b1)

5) Image Resizing
```
image9=image_resized.copy()
resized_image=cv2.resize(image9,(image9.shape[0]//2,image9.shape[1]//2))
cv2.imshow('Original image',image_resized)
cv2.imshow('Resized image',resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/7b0390fc-b6dd-4d84-8135-73b0898cae16)

![image](https://github.com/user-attachments/assets/a8f055fc-5042-48d2-b98b-ebf679e65424)

6) Image Cropping
```
image10=image_resized.copy()
x, y = 50, 50
width, height = 250, 250
roi = image10[y:y + height, x:x + width]
cv2.imshow('CROPPED IMAGE', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/819191bb-8649-40b8-a612-6d84fd23793f)

7) Image Flipping

a) Flip the original image horizontally and display it.
```
image11=image_resized.copy()
res=cv2.rotate(image11,cv2.ROTATE_180)
cv2.imshow('ORIGINAL IMAGE',image11)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
````
![image](https://github.com/user-attachments/assets/ad8d5ef8-0795-481b-819e-8677e2db780e)

![image](https://github.com/user-attachments/assets/1e31a241-941a-4f49-9460-acd90c2f6fda)

b) Flip the original image vertically and display it.
```
image12=image_resized.copy()
res=cv2.rotate(image12,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image12)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/4b2e2e56-cd43-4169-b5c0-22fe5c58ba41)

![image](https://github.com/user-attachments/assets/d2a6b060-ae15-487d-92ea-b031d9e27e52)

8) Write and Save the Modified Image
```   
image13=image_resized.copy()
cv2.imwrite('lokesh2.jpg',image13)
```
![image](https://github.com/user-attachments/assets/75222625-e003-4094-84f5-bc094fc01e28)

Result:

Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
