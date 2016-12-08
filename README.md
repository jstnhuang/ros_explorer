# ROS Explorer
A visual, web-based interface for examining the ROS graph.
- See all the nodes, topics, services, and parameters.
- Click on one to see what other nodes, topics, or services they are connected to.
- See topic and service types.
- Add/edit/delete parameters.

![ROS Explorer Dashboard screenshot](https://cloud.githubusercontent.com/assets/1175286/20996188/9da3cb16-bcb0-11e6-899b-4d46d0c2b01e.png)

## Installation
Unzip the pre-built website from the latest release in the [Releases](https://github.com/jstnhuang/rose/releases) tab.
We recommend compiling the code as a catkin package just to get the ability to run the ROS Explorer using `roslaunch`.

```
cd ~/catkin_ws
git clone https://github.com/jstnhuang/rose.git
cd rose
wget https://github.com/jstnhuang/rose/releases/download/v1.1/www.zip
unzip www.zip
catkin build
```

## Running
ROS Explorer is a simple webpage, which you can serve from the `www` directory however you like, such as with `python -m SimpleHTTPServer 8595 .`
You must be running a websocket server beforehand: `roslaunch rosbridge_server rosbridge_websocket.launch`.

We also provide two launch files for convenience.
- `roslaunch rose rose.launch`: Runs a Python server from the `www` directory and opens ROS Explorer in a web browser.
- `roslaunch rose rose_websocket.launch`: Same as above but also runs a websocket server.

## User notes
- By default, the websocket URL is determined from the host the webpage is being served from (e.g., `localhost`, `robot.university.edu`).
- You can scroll horizontally to view names that have been cut off but holding Shift while scrolling.
- Press Ctrl+F to search for a name.

## Developing
ROS Explorer is built with [Polymer](https://www.polymer-project.org/1.0/).

Install Node.js using nvm if you don't already have it:
- Install [nvm](https://github.com/creationix/nvm)
- `nvm install node`

Install the Polymer CLI if you don't already have it:
- `npm install -g polymer-cli`

Download the frontend dependencies:
- `cd frontend`
- `bower update`

Run a local development server:
- `polymer serve`
- Visit `localhost:8080` in a web browser.

## Robot web server
ROS Explorer works with [RWS](https://github.com/hcrlab/rws).
