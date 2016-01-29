# BIER Topology Manager
This is a web application developed to manage multipoint content over BIER networks. It implemented on top of OpenDaylight with means of [Angular](http://github.com/angular/angular.js), [Angular Material](https://github.com/angular/material) and [NeXt UI](http://github.com/CiscoDevNet/next-ui). Pure open-source product.

# Application Overview
## What is BIER?
Bit Indexed Explicit Replication (BIER) is a revolutionary new multipoint forwarding architecture. BIER allows for network replication without a tree building protocol or per-flow state by providing a mechanism to define endpoints within the packet header. BIER routers replicate and forward multicast packets along the unicast shortest paths to each of the defined endpoints for any given packet. This is a radical simplification over all previous multi-point solutions, reducing the cost of operation and providing deterministic network convergence performance for multicast services.

## Demo
App vizualizes BIER topology:
<div>
<img src="https://raw.githubusercontent.com/zverevalexei/bierman-gui/master/images/01-app-overview.png" alt="Network topology" style="display:block;">
</div>
<br><br>
Easy setup of channel in **Channel Manager**: 
<div>
<img src="https://raw.githubusercontent.com/zverevalexei/bierman-gui/master/images/02-channel-manager.png" alt="Channel manager" style="display:block;">
</div>
**Path Manager** features one-click computation and deployment of BIER tree:
<div>
<img src="https://raw.githubusercontent.com/zverevalexei/bierman-gui/master/images/06-path-computed.png" alt="Computed path" style="display:block;">
</div>
<div>
<img src="https://github.com/zverevalexei/bierman-gui/blob/master/images/07-path-deployed.png?raw=true" alt="Path deployed" style="display:block;">
</div>

# 3-step Setup
## REST Proxy Server
We use [ODL REST Proxy](https://github.com/zverevalexei/odl-rest-proxy) to avoid CORS restrictions. Proxy enhances possibilities of REST API, since we can make even 'unsafe' requests.

Open the file /web/app/bierman.controller.js and find the object '$scope.appConfig'.

Modify its properties 'proxyHost' and 'proxyPort' so that they are your actual data. You may want to leave the data as is if you don't locate proxy on a remote computer or you didn't change the port number.
- **proxyHost** points to proxy's IP address (or a host name)
- **proxyPort** points to proxy's port


## Controller Settings
Open the file rest_proxy.js and find the object 'appConfig'.

Modify its properties 'ctrlHost', 'ctrlPort', 'ctrlUsername' and 'ctrlPassword' so that they are your actual data.
- **ctrlHost** points to controller's IP address (or a host name)
- **ctrlPort** points to controller's port
- **ctrlUsername** and **ctrlPassword** are credentials to authorize on the server

## Running GUI (easy as pie)
1. Have [NodeJS](https://nodejs.org) installed on your computer
2.  Go to the application's root folder and run the command in terminal:

  ```
  node rest_proxy.js
  ```
3. Point your browser to (PATH-TO-BIERMAN)/web/app/index.html and enjoy

# Meet the Team
* Chris Metz (chmetz@cisc.com)
* Greg Shepherd (shep@cisco.com)
* IJsbrand Wijnands (ice@cisco.com)
* Gaofeng Tao (gatao@cisco.com)
* Alexei Zverev (alzverev@cisco.com)
