<opencv_storage>
<cascade type_id="opencv-cascade-classifier"><stageType>BOOST</stageType>
  <featureType>HAAR</featureType>
  haar_cascade = 'cars.xml'
video = 'video.avi'      
cap = cv2.VideoCapture(video) 
car_cascade = cv2.CascadeClassifier(haar_cascade)
    # reads frames from a video 
ret, frames = cap.read() 
        
# convert frames to gray scale  
gray = cv2.cvtColor(frames, cv2.COLOR_BGR2GRAY) 
        
# Detects cars of different sizes in the input image 
cars = car_cascade.detectMultiScale
  <internalNodes>  
      (gray, 1.1, 1)
          <leafValues>
            cv2.rectangle(frames(0,0,255),2)</leafValues></_>
        <_>
          <internalNodes>
           # Display frames in a window 
              cv2.imshow('video', frames)</internalNodes>
          <leafValues>
        # loop runs if capturing has been initialized. 
while True: 
    # reads frames from a video 
    ret, frames = cap.read() 
        
    # convert to gray scale of each frames 
    gray = cv2.cvtColor(frames, cv2.COLOR_BGR2GRAY) 
        
    
    # Detects cars of different sizes in the input image 
    cars = car_cascade.detectMultiScale(gray, 1.1, 1) 
        
    # To draw a rectangle in each cars 
    for (x,y,w,h) in cars: 
        cv2.rectangle(frames,(x,y),(x+w,y+h),(0,0,255),2) 
    
    # Display frames in a window  
    cv2.imshow('video', frames) 
        
    # Wait for Esc key to stop 
    if cv2.waitKey(33) == 27: 
        break
    
# De-allocate any associated memory usage 
cv2.destroyAllWindows()</leafValues></_>
            
</opencv_storage>

