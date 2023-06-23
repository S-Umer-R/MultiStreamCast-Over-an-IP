# MultiStreamCast Over an IP using Python


## Introduction: 
 
The purpose of this project is to mimic the real life working of a Radio where each Station provides separate content to connected client, but instead of providing audio data to client we serve video to client. It’s kind of a combination of Radio and Video Streaming. Our Program Implements a multi-station video streaming application that utilizes Python sockets and OpenCV library. The application involves a server and connected client, where a client can select a video station and start streaming video from it. The server handles the incoming request from a client, sends video stream data to the multicast group, and client receives the video stream data and displays it in a window. 
 
 
## Project Files: 
 
1)	“server.py” 
2)	“client.py” 
3)	“video.mp4” → Hosted on Station 1 on Server Side. 
4)	“sample.mp4” → Hosted on Station 2 on Server Side. 
 
## Implementation: 
 
The application is implemented in Python language and uses OpenCV library for video streaming and processing, and socket programming for communication between the server and the client. The server and client code are separated into two files, "server.py" and "client.py", respectively, 
 
## Server Side: 
 
•	Creates a UDP socket to receive data from clients. 
•	Sets up a multicast group to send data to multiple clients simultaneously. 
•	Uses the videoprops library to extract video properties like resolution, aspect ratio and frame rate from two stations. 
•	Waits for a "start" message from the client to initiate communication. 
•	Sends the extracted video properties to the client. 
•	Waits for the Client to select one of the two stations to send the Video Stream of that station to the Client. 
•	Breaks the video into jpg frames and sends the frames to the multicast group at the rate of 30 FPS. 
•	Allows Client to change Station at any time and sends the Video Stream of the Selected Station. 
 
## Client Side: 
 
•	Creates a UDP socket to send data to the server and receive data from the multicast group. 
•	Joins the multicast group set up by the server. 
•	Sends a "start" message to the server to initiate communication. 
•	Receives the station information from the server. 
•	Displays the station information. 
•	Prompts the user to select one of the two stations to stream the video file from that station. 
•	Sends the user’s input for Station selection to the Server. 
•	Receives jpg frames of the selected video file from the multicast group and displays them in GUI window at the rate of 30 FPS. 
 
•	During playback of video stream in GUI window, User can press ‘p’ to pause the video stream. 
 
•	During Paused state of the video stream, User is allowed to Select one of the following choices, 
1)	Exit  
2)	Change the Station  
3)	Resume 
 
•	Exit terminates client and closes the client connection to the server. 
•	Change the Station Client will notify Server for switching to different Station and Server the sends Video Stream of that Station to Client. 
•	Resume Resumes the Current Paused Video Stream. 
 
Overall, the Program allows a Client to Stream Video from a Selected Station from the Server over a Multicast group. 

## Prerequisites

- Python 3.x
- OpenCV (cv2) library
- videoprops library

## Getting Started

**NOTE: To run the application, the Server program and the Client program should be run separately on different terminals. The following Steps can be followed to run the application: **

1. Install the required dependencies:

   ```
   pip install opencv-python videoprops
   ```

2. Run the server-side application on the streaming server:

   ```
   python server.py
   ```

3. Run the client-side application on the receiving client:

   ```
   python client.py
   ```

4. Follow the prompts on the client-side application to select a station and control the streaming.

## Usage

1. The server-side application captures video from the specified sources (video files) and streams them over a multicast group.

2. The client-side application receives the video streams from the multicast group and displays them on the screen.

3. The client can select a station from the available options and switch between stations for viewing different video sources.

4. Press 'p' to pause the video stream and display available options (exit, change station, resume). Select the desired option by entering the corresponding choice.

5. The server and client communicate through UDP sockets, sending and receiving data packets containing video frames.

## Conclusion: 
 
In conclusion, this Project has Successfully Implemented a Multi-Station Video Streaming application using Python sockets and OpenCV library. The application allows a Client to select a Station and Start streaming video from it. The Server sends Video stream data to the multicast group, and clients receive the video Stream data and Plays it in a GUI window. The application can be used for Video Streaming applications that require Streaming from Multiple Stations simultaneously. 



 

  
