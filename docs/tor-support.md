<h1 align="center">Ai</h1>
<h4 align="center">Tor support</h4>

## Description
To spice things up I implemented a Tor support for Ai so you can hide your real IP/identity while scanning for vulnerabilities.

## Setup
1. Visit [torproject](https://www.torproject.org/download/tor/) and download the **Windows Expert Bundle**.
2. Decompress the file go to **Tor** folder and run **tor.exe**.
3. Find **Opened Socks listener connection (ready) on 127.0.0.1:9050** in the logs and get the IP and port and use it in the Tor flag.

## Usage example
```
node index.js -u http://124.83.125.190:9998 -t templates/iwoca.yaml -tr 127.0.0.1:9050
```
