# ROS Explorer
A visual, web-based interface for examining the ROS graph.
- See all the nodes, topics, services, and parameters.
- Click on one to see what other nodes, topics, or services they are connected to.
- See topic and service types.
- Add/edit/delete parameters.

![ROS Explorer Dashboard screenshot](https://cloud.githubusercontent.com/assets/1175286/20996188/9da3cb16-bcb0-11e6-899b-4d46d0c2b01e.png)

## Running
ROS Explorer is a simple webpage, which you can serve from the `www` directory however you like, such as with `python -m SimpleHTTPServer 8595 .`
You must be running a websocket server beforehand: `roslaunch rosbridge_server rosbridge_websocket.launch`.

We also provide two launch files for convenience.
- `roslaunch ros_explorer ros_explorer.launch`: Runs a Python server from the `www` directory and opens ROS Explorer in a web browser.
  To use this, you need `xdg-open` and `python -m SimpleHTTPServer`. The website will be served on http://localhost:8595.
- `roslaunch ros_explorer ros_explorer_websocket.launch`: Same as above but also runs a websocket server.

## User notes
- By default, the websocket URL is determined from the host the webpage is being served from (e.g., `localhost`, `robot.university.edu`).
- You can scroll horizontally to view names that have been cut off but holding Shift while scrolling.
- Press Ctrl+F to search for a name.

## Developing
ROS Explorer is built with [Polymer](https://www.polymer-project.org/).

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
- Visit http://localhost:8081 in a web browser.

## Robot web server
ROS Explorer works with [RWS](https://github.com/hcrlab/rws).
