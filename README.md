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

<p>Firts "Install docker" this might take a while. Process will install latest Docker and Docker-compose for ARM. When installation is completed you will be prompted to reboot, please do so before continuing.<p>

<p>Next "Build LDS Stack", select docker containers that you would like to pull and deploy. You do not have to select them all, use only the one you will need. Selecting only the one you need will reduce RAM consumption on your Pi what might be a problem on RPi 3, not so much on PPi 4 I guess. I do not have RPi 4 so I was only able to test it on my old RPi 3B</p>

<p>You might like to install Portainer - that will be available on port :9000, Portainer is a graphical interface to manage Docker engine. If you not sure what Portainer is check it on YouTube</p>
