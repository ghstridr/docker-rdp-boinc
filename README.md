### BOINC Client and Manager

BOINC lets you contribute computing power on your home PC to projects doing research in many scientific areas. You can contribute to a single project, or to any combination of them. RDP-Boinc is a docker for the BOINC manager and client that can be accessed through a web based ui.

#### Install On unRaid:

On unRaid, install from the Community Applications and enter the app folder location and the port for the webUI.


#### Install On Other Platforms (like Ubuntu or Synology 5.2 DSM, etc.):

On other platforms, you can run this docker with the following command:

`docker run -d --name="RDP-Boinc" -e HEIGHT="720" -e WIDTH="1280" -v /path/to/config:/config:rw -v /etc/localtime:/etc/localtime:ro -p XXXX:8080 aptalca/docker-rdp-boinc`

#### Setup Instructions:

- Replace "/path/to/config" with your choice of folder location. That is where all of your configuration and library files will reside, so you won't lose data when you update, reinstall, etc.
- Replace "XXXX" with your choice of port.
- You can change the screen resolution by modifying the WIDTH and HEIGHT variables.
- Ctrl-Alt-Shft will bring up the menu that allows changing input options

To access the GUI, point your web browser to http://SERVERIP:PORT/#/client/c/Boinc (Replace SERVERIP and PORT with your values)


##### Note:
Some platforms like Debian are having issues with setting timezones. If you get the following error:
`mv: cannot move '/etc/localtime.dpkg-new' to '/etc/localtime': Device or resource busy
*** /etc/my_init.d/00_config.sh failed with status 1` and the container stops, remove the following from your run command: `-v /etc/localtime:/etc/localtime:ro` and replace it with the following: `-e TZ="America/New_York"`

You can change the timezone to yours according to the list here: https://en.wikipedia.org/wiki/List_of_tz_database_time_zones
=======
1. Install the plugin in the following linked thread http://lime-technology.com/forum/index.php?topic=39106.0 <br />
2. Scroll down and click on the logo <br />
3. Put in your library location and port <br />
4. Open the WebUI <br />
5. Profit
