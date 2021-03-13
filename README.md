# IOT 101
Internet of things is one of the most booming areas of the 21st century. It is present in every device we use and is shaping our lives.

![Screenshot](imgs/img1.jpg)

## Content
1. RTSP Video Stream
2. Cloud push
3. BLE aggrigator architecture
4. Machine Learning processing
5. Applying Deep Learning on Video Streams
6. Using Color Space transformations to build a simple day and night detector

### 1.RTSP Video Stream
In this project we will use RTSP to stream video over a Wi-Fi interface. The main hardware we would use is going to be a raspberry pi. The only requirement is that the raspi should have a camera and Wi-Fi capability. The image below is a raspberry pi zero configure as a stream device.

![Screenshot](imgs/raspi_stream.jpg)

Steps to stream over RTSP:

            1.sudo raspi-config
                1.1 Go to interfaces
                1.2 Turn on or Enable Camera
            2. sudo apt-get install vlc
            3. raspivid -o – -t 0 -n | cvlc -vvv stream:///dev/stdin –sout ‘#rtp{sdp=rtsp://:8554/}’ :demux=h264

This starts the datastream then open a mobile phone or laptop connected to the same Wi-Fi. Open VLC media player, goto network and type :

            rtsp://ip address of your pi:8554/
                        
To find out the ip of the raspi you can use :

            hostname -I

With the following steps you would have successfully created a video stream over your local Wi-Fi network. This could later be used for video detection.

#### Applications
1. Intrusion Detection
2. Computer Vision based automation

