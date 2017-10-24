# Progress:

Front end has started and can be viewed at
[https://voyager.philgore.net](https://voyager.philgore.net)

The front end repo can also be found 
[here](https://github.com/Erog38/Voyager)

## Backend development has begun!

[Voyager Electronic Radio](http://streaming.shoutcast.com/VoyagerElectronicRadio)

<audio controls>
  <source src="http://streaming.shoutcast.com/VoyagerElectronicRadio" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

## Internet Radio Streaming in Golang

This will be a streaming server using ffmpeg to target the general public, 
and those who appreciate the genre which will be played, and which hasn't
been decided yet. I'll be pulling music from legal sources which have been
licensed for public use.

The idea behind this is to build a full stack service using React, golang,
and C bindings to the FFmpeg library

## Backend

The Backend has evolved somewhat to rely on shoutcast with goicy as the 
interface, the stream can be accessed via VLC at 

[Voyager Electronic Radio](http://streaming.shoutcast.com/VoyagerElectronicRadio)

The music is currently provided by NCS, and the entire station is in it's first 
baby steps.

The Free Music Archive (FMA) provides a REST API to gather song information
and download them from their servers. 

The Go backend will have two major functions:

* Gather track data from FMA  and serve it to the front end via a local sqlite
  database.
* Stream audio via FFmpeg bindings.
  https://github.com/giorgisio/goav 

The stream should also be available from an industry standard player, such as
VLC, iTunes, Winamp, etc.

__The backend will have a seperate git repository for simplicity to be linked
here soon__

## Frontend

The frontend for this project should consist of a featured website, including
song request out of a preselected library, and a webclient which can play
music from the server. 

This will be built using React, with simple REST API calls to pull information
from the backend.

When a user selects a song, the frontend adds that track to a table in the 
database for the backend to add it to the queue.

__The fontend repo can be found [here](https://github.com/Erog38/Voyager)__

### Specifics:

* Website using React
* HTML web player
* Basic Authentication for admin and management pages.
* REST API for backend communication.
* Certs provided by LetsEncrypt and auto renewed through by certbot. 

## Stretch Goals:

* Impliment OAuth through Google instead of basic HTTP authentication
* Allow file upload through the management interface
* Chat (possibly IRC) client
* Forum
* Song library for logged in users to petition songs to be added to the queue.
* Dockerfile to wrap all this up into a nice container for use in Gitlab CI
with an nginx reverse proxy.
