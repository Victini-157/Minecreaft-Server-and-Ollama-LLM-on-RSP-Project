# Project Title
Minecraft Server and Ollama LLM on RSP Project
## Table of Contents

## About

## Features
-Interactive Discord Bot
-Minecraft Server
-Bot interacts with Minecraft Server
-Everything controlled on Discord

## Prerequisites
Docker for laptop/ PC
Download: https://www.docker.com/products/docker-desktop/
### How to set everything up
## Setting up the dockers

## Node RED Nodes

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

## Set up the Discord bot
For the Discord bot you need a bot token, watch this video to make a Discord bot and to get the Token:
https://youtu.be/2jOzQWnKc-o?si=46OR0fDfaeMK8iD9
Once you have it make sure do not share it with anyone else.
Make sure you have turned on the same settings shown in the video and save.
Once you have it, click on a NODE that has discord on it and paste the key and give it a name and make sure the rest of the discord NODES has them.
You don't need to nake a new profile everytime, once you have have already pasted the token, gave a name and save it, it saves it as a profile.

## Set up the Minecraft server
Open the compose Server.yml file, but don't copy and paste it to the .yml in the docker container yet.


## Usage

## Configuration

## Examples

## License

## Authors and Acknowledgments




