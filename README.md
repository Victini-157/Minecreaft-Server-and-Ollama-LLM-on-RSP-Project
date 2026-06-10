# Project Title
Minecraft Server and Ollama LLM on RSP Project
## Table of Contents
[About](#about)

[Features](#features)

[Prerequisites](#prerequisites)

[How to set everything up](#howto)

[Setting up the dockers](#dockers)

[Node RED Nodes](#nodered)

[Set up the Ollama bot](#ollamabot)

[Set up the Discord bot](#discordbot)

[Set up the Minecraft server](#minecraftserver)

[Usage](#usage)

[Configuration](config)

[Authors and Acknowledgments](#AaA)

## About
This is a project that aims to use an Ollama LLM on a rasberry pi along with NodeRED and a Minecraft Server on seperate computer.
Almost all of it is on a discord front-end to chat with the bot, ask questions and to output detailed commands to the minecraft server
It also includes a dashboard that displays a multitude of information useful for the user
All in all this project is for funsies.

## Features
-Interactive Discord Bot
-Minecraft Server
-Bot interacts with Minecraft Server
-Everything controlled on Discord

## Prerequisites
Docker for laptop/ PC
Download: https://www.docker.com/products/docker-desktop/

NODE RED:
node-red-contrib-discord-updated
@flowfuse/node-red-dashboard
@tomsith/node-red-contrib-minecraft

### How to set everything up

## Setting up the dockers
On widnows:
Open powershell
Make a folder and make sure it is on the directory of the folder. (Makes sure to change the names to something you can remember)
mkdir Change name please
cd Change Name please

Now build the container by pasting these commands:
docker build -t my-app . (Change "my-app" to whatever name you like)
docker run -p 25575 :25575  my-app 

(Don't change the .yml file yet, you'll see why)

On Linux (Ubuntu or debian and based only):

Make sure to first ssh into it.
Don't know how to do that?
Watch this tutorial: https://youtu.be/vVZuadit2Sw?si=ekfBQMdiHJz3cypj

Done? Good!
Everything else will be down in that ssh connection on powershell or tails.

run these commands:
sudo apt update
sudo apt install docker.io docker-compose
sudo systemctl start docker
sudo systemctl enable docker


This updates your system and installs docker.

Now paste the commands to make your container (Make sure to change "my-docker-app") :
mkdir my-docker-app
cd my-docker-app

Make a file in the folder with:

nano Dockerfile (Change the name also)

Put in the code of the .yml file "compose RAsberryPi.yml" in the file.

Start everything up with:

sudo docker compose up 

(only works if ou are in the directory of the folder)


## Node RED Nodes
Before we begin make sure to download the libraries mentioned in Prerequisites.
Click on the 3 bars on the upper right.
Then click on "Settings".
Then on "Palletes" and on the menu when you click on it, click "Install".
Once the search bar, copy and paste each name of the library seperatly and install them.
When you installed everything, make sure you put the flows.json file somewhere where you can find it.
Click on the 3 lines again and click "Import".
Then click on "Select a file to import" and select the flows.json file, then you'll have al the NODES you need.

## Set up the Ollama bot
On NodeRED you don't need to change the http link in the http Node. The only thing you need to do is click on "Java object converter" and "function 3" on there you'll see a json, change the model name to the bot you have installed on the pi. 
Bot recommendations:

Recommended(Will Work just fine no issues):
Llama3.2:1b(or better 3b),
Mistral 7B,
Neural Chat, 
Phi 2

Daredevil(Warning long response time):
Dolphin Mistral 8x7B,
Mistral Large,
Llama 2 13B

On Rasberry pi when you are in the directory of your docker name use this command : "ollama pull ***NAME OF THE BOT YOU WANTED TO CHOOSE**" and download it.

## Set up the Discord bot
For the Discord bot you need a bot token, watch this video to make a Discord bot and to get the Token:
https://youtu.be/2jOzQWnKc-o?si=46OR0fDfaeMK8iD9
Once you have it make sure do not share it with anyone else.
Make sure you have turned on the same settings shown in the video and save.
Once you have it, click on a NODE that has discord on it and paste the key and give it a name and make sure the rest of the discord NODES has them.
You don't need to nake a new profile everytime, once you have have already pasted the token, gave a name and save it, it saves it as a profile.

## Set up the Minecraft server
Open the compose Server.yml file, but don't copy and paste it to the .yml in the docker container yet.
Go to the RCON password atribute and type the password in the Password you want to use (very important).
Then going back to NODE RED, click on the Server info NODE or rcon NODE, there you need to put in an IP Adress, RCON port and the password.
Make sure to put in the IP Adress of your laptop/PC that you are running the Server Docker on.
For the RCON port, put in this: 25575 
And the RCON password, the passwaord you put in the yml file.

Now you have everything you need to chat, play on a server and have a helper with commands.

PS:
To open the Dashboard, on the right of the screen in the middle, there is an arrow you can click.
Once you have clicked it, click on the arrow that is pointing down, then Dashboard 2.0.
Then on the upper part of the menu you'll see "My Dashboard", look on the left, there is a button called "open dashboard", click on it and you have the Dashboard open.


## Usage
This can be useful in many ways.
You have a Minecraft server that can be accessed to anyone in your local network, which means friends and family can all play on it no problem.
With NodeRED you can expand it to fit what you want without any coding knowledge without any fear of breaking it.
If you have specific commands or want something specfic in the Minecraft server, the ai can adapt your prompt without you needing to do research.
It is also a great ai front end, as you can put the bot in your private discord server and use it like chatGPT.

## Configuration
To configure it, use the Nodes on the left of the screen.
You can even open a new flow in NodeRED incase you don't want to touch it and experiment.

## Authors and Acknowledgments
Kimiko/Victini-157

My networking Teacher






