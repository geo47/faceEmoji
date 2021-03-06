**Important details when trying to install openCV 3.0.0 on Mac El Capitan**

when trying to install openCV on mac El Capitan, instead of Yostmite, you may encounter such problem of 

```
>>> import cv2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ImportError: dlopen(./cv2.so, 2): Library not loaded: lib/libopencv_reg.3.0.dylib
  Referenced from: /Users/yushunzhe/.virtualenvs/cv/lib/python2.7/site-packages/cv2.so
  Reason: image not found
```

such unable to load some libraries, and that's due to  SIP (System Integrity Protection) introduced in El Capitan. Thus you will have to copy the folder `cv2.so` by yourself! which is critical to be able to load libraries later on. 

For other part of installing, if you are in Mac El Capitan, you will finally encounter a problem I mentioned above. To make your life eaiser, I recommend use such command to go over that:

```
cp /usr/local/Cellar/opencv3/3.1.0/lib/python2.7/site-packages/cv2.so /usr/local/lib
```

as discussed in [this post](https://github.com/Itseez/opencv/issues/5447). And That's all, hope you enjoyed using openCV!

## Run the project
cd to the folder, then did:
```
python face_detect.py IMG_0244.jpg facecascade.xml
```
you should receieve the result like "1 face found" and found a funny Emoji overlaid. The final result looks like this: ![project result](http://ww2.sinaimg.cn/large/c5ee78b5jw1f21qpw6q8oj20ki0b7wez.jpg)