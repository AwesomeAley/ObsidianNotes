## Installation

### Install from Kali/OpenVAS repositories
https://agix.com.au/installing-openvas-on-kali-in-2020/

### Install on Docker 
Using mikesplain
https://github.com/mikesplain/openvas-docker

`apt install docker.io`

`docker run -d -p 443:443 --name openvas mikesplain/openvas`

navigate to `https://127.0.0.1` in a browser

credentials: 
admin
admin

go to *Scans > Tasks*, click on purple magic wand to start the basic configuration wizard. Run the scan on local machine {127.0.0.1}

