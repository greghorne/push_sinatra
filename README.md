# Shake-Shake
**Server-Sent Events (SSE in HTML5)**


*Overview:*

- This application is written in Ruby/JS and deployed as a Sinatra application.
- The purpose of this project is to demonstrate <i>Server-Sent Events</i> which is a server to client communication protocol (one-way).  	
- Note that Server-Sent Events are not supported by IE/Edge as of this writing.  
- Wikipedia: https://en.wikipedia.org/wiki/Server-sent_events

*What does this webpage do:*

- Display in client browser a map.
- Server polls USGS every 30 seconds for earthquakes that have occured within the last 15 minutes.
- Note that the USGS information is not necessarily instantaneous meaning for example an earthquake that occurred 10 minutes ago might only be reported by the USGS within the last few minutes.
- The intent of the webpage is to display the latest earthquake that has occurred within the past 15 minutes as reported by the USGS.
- When a new earthquake event is received by the server, such information is pushed to the client browser repositioning the map and displaying information about the event.
- If the initial map displayed is a view of the entire USA with no marker on the map signifying an earthquake, this means an earthquake has not been recorded in the last 15 minutes.  Thus just leave the webpage as is and wait.
- If the browser's developer's console is open, one can observe the messages being sent to the client from the server.

*Tech Stack:*

- ruby 2.4.0p0 (2016-12-24 revision 57164) [i686-linux] 
- sinatra (1.4.8), sinatra-contrib (1.4.7)
- Leaflet 1.0.3 (https://en.wikipedia.org/wiki/Leaflet_(software))
- OpenStreetMaps (https://en.wikipedia.org/wiki/OpenStreetMap)
- USGS REST API Server (https://earthquake.usgs.gov/fdsnws/event/1/)
- Deployment: Docker container on Raspberry Pi 3 B http://zotac1.ddns.net:3200

*Local Deployment/Execution (Ubuntu):*

- Clone this repository to a folder
- Confirm ruby, sinatra and sinatra-contrib is installed
- Execute "bundle install"
- Execute "ruby app.rb -o 0.0.0.0"
- Open a web browser and navigate to: "0.0.0.0:4567"

This webpage can be more fun than watching paint dry.

Deployment: http://zotac1.ddns.net:3200

