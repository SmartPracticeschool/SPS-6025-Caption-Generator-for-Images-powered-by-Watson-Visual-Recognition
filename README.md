# SPS-6025-Caption-Generator-for-Images-powered-by-Watson-Visual-Recognition
Caption Generator for Images powered by  Watson Visual Recognition

Services used in our model:
1. Watson services 
2. Text to Speech service
3. Visual Recognition service 
We have attached storage service with it. 
Launch Watson Studio To get credentials: API key : ************************* URL: https://api.us-south.visual-recognition.watson.cloud.ibm.com/instances/250d401e-1b48-4c1b-bc8c-a6e45ca27e65
Choose Prebuild model for our example, General 
The first step GO to test
Overview: 
Model ID default 
Status Ready 
Explanation Generate class keywords that describe the image. 
Use  images, or extract relevant image URLs from publicly accessible webpages for analysis.

Test: Where we can browse any image to get captions now we integrate it with Node-red
for that, we have to start Cloud foundry services to start node-red services

Use the IBM Cloud® command-line interface (CLI) to download, modify, and redeploy Cloud Foundry applications and service instances.
visit app URL
Go to the Node-RED flow editor
and instantiate using manage pallete and install followings
Installing dashboard and browse untils node 

Step – 1: Go to the navigation pane and click on manage palette 

Step – 2: Click on install 

Step – 3: Search for “node-red-dashboard” for dashboard nodes and “node-red-dbrowser-utils and click on install and again click on install on the prompt 

Step – 4: The following message indicates dashboard nodes/ any other node you install are installed, close the manage palette

• node-red-contrib-model-asset-exchange 
• node-red-contrib-camerapi 
• node-red-dashboard 
• node-red-contrib-image-output

Now Configure the following nodes:

1.	Template node
The template node is a widget which can contain any valid html and Angular/Angular-material directives.
Template: type Widget in group Group: Watson Visual Recognition Size: 9 X 8
Template:
Pass through messages from input Add output messages to stored state

2.	Visual Recognition
using the visual recognition v3 node. we have used the watson visual recognition service v3 to identify the scenes and objects in images which are uploaded to the service. We can create and train a custom classifier to identify subjects that suit our needs.
API Key: *******************************
Service Endpoint: https://api.us-south.visual-recognition.watson.cloud.ibm.com/instances/250d401e-1b48-4c1b-bc8c-a6e45ca27e65
Detect: Classify an image

3.	Debug node
print msg.result.images
Print message debug node result images
print.msg.result.images
output: msg.result.images
name: Print msg.result.images

4.	Process Results
Function node
Name: Process Results
Function:
Node Template output
Template type: Widget in group
Group: [IBM]Results Size 9 X 12

5.	Template:
Pass through messages from input Add output messages to stored state.
Msg.payload

6.	Debug node
Payload
Output: msg.payload

7.	text to speech
Text To Speech Node
The text to speech service understands text and natural language to generate synthesized audio output complete with appropriate cadence and intonation.
API Key: *******************************************
Service Endpoint: https://api.us-south.text-to-speech.watson.cloud.ibm.com/instances/614664fa-a093-465e-9da2-c45afc189af6
Place output on msg.payload

8.	Node audio out
play audio or text to speech (TTS) in the dashboard.
Group: [IBM]Results
Now, make all the connections

After all set, we can deploy our model
and execute check result on webpage
https://red-hot-iot.eu-gb.mybluemix.net/ui/#!/0?socketid=BvI9Sp4QepSDzLyBAAAB

Video:
https://drive.google.com/file/d/15k4rqaHDQPhT9X-9lzUwFLOHqWvvMJtL/view?usp=sharing

