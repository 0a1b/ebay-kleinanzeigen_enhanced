# Ebay-Kleinanzeigen notifier

Update:
- several ebay links can be put into the bot.
- /restart command empties the link queue

This is very simple Telegram bot checking new ads on [Ebay-Kleinanzeigen.de](https://www.ebay-kleinanzeigen.de/stadt/muenchen/).

It accepts just a link to a page with the search results (i.e. `https://www.ebay-kleinanzeigen.de/s-pc-zubehoer-software/grafikkarten/81825/anzeige:angebote/preis:100:500/c225l16390r150+pc_zubehoer_software.art_s:grafikkarten`) and then starts monitoring this page (by default every 15 minutes).

It doesn't work with the mobile version.

When some new ad appears, you'll be notified. 
 
 # Documentation
 
 ### Requirements
Python 3.6+ and Docker (preferrably)

### Setup for dummies

sudo apt update
sudo apt upgrade
sudo git clone https://github.com/0a1b/ebay-kleinanzeigen_enhanced.git
cd /home/a/ebay-kleinanzeigen_enhanced (where it was unpacked)
sudo apt install docker-compose (i am using raspberry pi os)
sudo nano .env (update the environmental file by putting the botfather key plainly into it and writing sth number in debug)
docker-compose build
sudo docker-compose up -d
systemctl start docker (if it doesn't work @.@)
sudo docker ps -a (see your docker)

sudo docker stop 30e7072151df (id can be found in the list of the command above, in case you want to remove an instance, you have to stop it frst if it was running in the first place)
sudo docker rm 30e7072151df (in case you want to remove an instance)
    
### Public availability and terms of usage

NOTE: I do not plan to host this bot publicly available (in contrast with [Munich Termin Notifier bot](https://github.com/okainov/munich-scripts)) because
it seems to have much more personalized queries and there is no point in analyzing the data in a single place. 

WARNING: Use this script on your own risk since usage may violate eBay Classified terms of usage. 

# Future improvements and contributions

Contributions welcome! Feel free to create Pull Request and/or propose ideas in [Issues](https://github.com/okainov/ebay-kleinanzeigen/issues)
