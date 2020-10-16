# SPS-6025-Caption-Generator-for-Images-powered-by-Watson-Visual-Recognition
Caption Generator for Images powered by  Watson Visual Recognition

Services used
Watson servces
configure Visual Recognition service
Attached storage service with it.
Launch Watson Studio
To get credentials:
API key : *************************
URL: https://api.us-south.visual-recognition.watson.cloud.ibm.com/instances/250d401e-1b48-4c1b-bc8c-a6e45ca27e65

Choose Prebuild model for our example
General
GO to test

Overview:
Model ID	default
Status		Ready
Explanation	Generate class keywords that describe the image. Use your own images, or extract relevant image URLs from publicly accessible webpages for analysis.

Test:
Where we can browse any image to get captions
now we integrate it with Node-red

for that we have to start 

Cloud foundary services to start node-red services

Use the IBM Cloud® command-line interface (CLI) to download, modify, and redeploy your Cloud Foundry applications and service instances.

visit app url 

Go to your Node-RED flow editor

and instantiate using manage pallete and install followings

Installing dashboard and browse untils node 
Step – 1: Go to navigation pane and click on manage palette
Step – 2: Click on install
Step – 3: Search for “node-red-dashboard” for dashboard nodes and “node-red-dbrowser-utils and click on install and again click on install on the prompt
Step – 4: The following message indicates dashboard nodes/ anyother node you install are installed, close the manage palette

•	node-red-contrib-model-asset-exchange
•	node-red-contrib-camerapi
•	node-red-dashboard
•	node-red-contrib-image-output


Configure the following nodes

Template node

The template node is a widget which can contain any valid html and Angular/Angular-material directives.

Template: type Widget in group
Group: Watson Visual Recognition
Size: 9 X 8

Template:
<CODE>

Pass through messages from input
Add output messages to stored state

Visual Recognition

using the visual recognition v3 node.
we have used the watson visual recognition service v3 to identify the scenes and objects in images which are uploaded to the service.
We can create and train a custom classifier to identify subjects that suit our needs.

API Key: *******************************

 Service Endpoint: 
https://api.us-south.visual-recognition.watson.cloud.ibm.com/instances/250d401e-1b48-4c1b-bc8c-a6e45ca27e65

 Detect:  Classify an image
 
print msg.result.images

Print message debug node result images

print.msg.result.images

output: msg.result.images

name: Print msg.result.images

Process Results

Function node

Name: Process Results


Function:

<CODE>


Node Template output

Template type: Widget in group

Group: [IBM]Results
Size 9 X 12

Template: 
<div ng-bind-html="msg.template"></div>


Pass through messages from input
Add output messages to stored state.

Msg.payload

Debug node

Payload 

Output: msg.payload


text to speech

Text To Speech Node


The text to speech service understands text and natural language to generate synthesized audio output complete with appropriate cadence and intonation.


API Key: *******************************************

Service Endpoint: https://api.us-south.text-to-speech.watson.cloud.ibm.com/instances/614664fa-a093-465e-9da2-c45afc189af6

Place output on msg.payload

Node audio out

play audio or text to speech (TTS) in the dashboard.

Group: [IBM]Results


after making all the connections

deploy

and execute check result on webpage


https://red-hot-iot.eu-gb.mybluemix.net/ui/#!/0?socketid=BvI9Sp4QepSDzLyBAAAB

Video:

https://drive.google.com/file/d/15k4rqaHDQPhT9X-9lzUwFLOHqWvvMJtL/view?usp=sharing
