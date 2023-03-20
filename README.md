# Image Acquisition from Web Camera

## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
1. Write the frame as JPG 
2. Display the video 
3. Display the video by resizing the window
4. Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)

### Step 3:
Resize the image using cv2.resize() to get a four-split screen.

### Step 4:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

### Step 5:
Display the image until the key to close the window is pressed.
</br>
</br>
</br>
## Program:
Developed By: **Srijith. R**
</br>
Register No: **212221240054**

## i) Write the frame as JPG file
```py
vidobj = cv2.VideoCapture(0)
while(True):
    ret,frame = vidobj.read()
    cv2.imshow('video_image',frame)
    #cv2.imwrite("capture.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
    result = False
vidobj.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```py
vidobj = cv2.VideoCapture(0)
while(True):
    ret,frame = vidobj.read()
    cv2.imshow('video_image',frame)
    cv2.imwrite("capture1.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
vidobj.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```py
obj = cv2.VideoCapture(0)
vidobj = cv2.VideoCapture(0)
while(True):
    ret,frame=vidobj.read()
    width = int(vidobj.get(3))
    height = int(vidobj.get(4))
    
    image = np.zeros(frame.shape,np.uint8)
    smallf = cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2] = smallf
    image[height//2:,:width//2] = smallf
    image[:height//2,width//2:] = smallf
    image[height//2:,width//2:] = smallf
    
    cv2.imshow('quad_screen',image)
    #cv2.imwrite("quad.jpg",image)
    if cv2.waitKey(1) == ord('q'):
        break
vidobj.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```py
vidobj = cv2.VideoCapture(0)
while(True):
    ret,frame=vidobj.read()
    width = int(vidobj.get(3))
    height = int(vidobj.get(4))
    
    image = np.zeros(frame.shape,np.uint8)
    smallf = cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallf,cv2.ROTATE_180)
    image[height//2:,:width//2] = smallf
    image[:height//2,width//2:] = cv2.rotate(smallf,cv2.ROTATE_180)
    image[height//2:,width//2:] = smallf
    
    cv2.imshow('quad_screen',image)
    #cv2.imwrite("quad_r.jpg",image)
    if cv2.waitKey(1) == ord('q'):
        break
vidobj.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![capture](https://user-images.githubusercontent.com/86846530/226261858-45d1f716-581e-44fb-9d1e-6e31ed4a6776.jpg)

### ii) Display the video
![capture1](https://user-images.githubusercontent.com/86846530/226261859-086d0353-2aa6-494b-bedb-de31a21851db.jpg)

### iii) Display the video by resizing the window
![quad](https://user-images.githubusercontent.com/86846530/226261868-958d96d1-22e2-438a-a4d7-ee3c088706ec.jpg)

### iv) Rotate and display the video
![quad_r](https://user-images.githubusercontent.com/86846530/226261871-76d95aa9-f22b-48f3-b9c3-525f8be6b43b.jpg)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
