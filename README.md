# LDS Stack

<b>Linux Download System Stack based on Docker for Raspberry Pi</b>

## About

Project goal is to simplyfy LDS deployment and maintanance on Raspbery Pi.
This repository will allow you to dynamicly choose needed containers and automate their deployment.

<b>What is currently a part of the LDS Stack:</b>

<ul>
  <li>Portainer - GUI Docker Manager :9000</li>
  <li> Sonarr :8989</li>
  <li> Radarr :7878</li>
  <li> Lidarr :8686</li>
  <li> Bazarr :6767</li>
  <li> Jackett :9117</li>
  <li> Deluge - Torrent Client :8112</li>
  <li> qBittorrent - Torrent Client :15080</li>
  <li> Transmission - Torrent Client :9091</li>
  <li> Emby - Media manager like Plex :8096</li>
  <li> EmbyStat - Statistics for Emby :6555</li>
  <li> Ngnix - Web Server with links to all servises deployed :80</li>
  <li> Pi-Hole - Private DNS sinkhole :8089</li>
  </ul>
<br>
<i>Numbers after ":" identify a port that particular container will respond on, i.e. Portainer default port is :9000, point your browser it to your server IP adding :9000 at the end i.e. http://192.168.100.100:9000 you will see Portainer login page.</i>

## How to Use it?

- install git using a command:
<pre><code>sudo apt-get install git</code></pre>

- Clone the repository with:
<pre><code>git clone https://github.com/maniuch/LDS.git ~/LDS</code></pre>

<i>Do not change name of the folder on your local system it should stay as is for the script to work properly</i>

- Enter the directory and run:

<pre><code>cd ~/LDS</code></pre>
<pre><code>./deploy.sh</code></pre>

## Menu

### Install docker
<p>Firts "Install docker" this might take a while. Process will install latest Docker and Docker-compose for ARM. When installation is completed you will be prompted to reboot, please do so before continuing.<p>

### Build LDS Stack
<p>Next "Build LDS Stack", select docker containers that you would like to pull and deploy. You do not have to select them all, use only the one you will need. Selecting only the one you need will reduce RAM consumption on your Pi what might be a problem on RPi 3, not so much on PPi 4 I guess. I do not have RPi 4 so I was only able to test it on my old RPi 3B</p>

<p>You might like to install Portainer among all the other containers - Portainer is a graphical interface that lets you manage Docker engine - very useful tool if you don’t want to use Docker CLI.</p>

### Docker Commands

<p>This small section contains few useful commands in case your Portainer is not running and you would like to get something done without GUI.</p>


### Miscellaneous commands.

<p>There are three scripts that can be used in case you would like to disable swapping to your SD card. You might want to do it in order to extend life of your SD card. SD cards were not designed to be used as IO intensive storage, therefore using them like a HDDs is not ideal. Swap file is used to offload your RAM in case of OS need to dump it somewhere. Swap will be quite often modify, what might wear out your SD card in a long run. In other hand if your OS is swapping a lot of data it means his RAM size is generally to small - this might be a case on RPi3 where we have only 1GB of RAM.</p>        

### Update LDS stack

<p>Each time you run <```./deploy.sh```> script it will check GitHub repository for any updates. There might be a small update but then you will be presented to upgrade, if this is the case, execute this option to pull recent updates in. Updates will not modify your configuration or any private files except the ones that are part of LDS logic. Some new functions might be added, new containers etc.</p>
