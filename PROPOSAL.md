## Internet Radio Streaming in Golang

This will be a streaming server using ffmpeg to target the general public, 
and those who appreciate the genre which will be played, and which hasn't
been decided yet. I'll be pulling music from legal sources which have been
licensed for public use.

The idea behind this is to build a full stack service using only Golang and 
C bindings, including the streaming service, data management, and web 
fronend.

## Backend

Using flat files, and a network connected file share, this server will hold
a queue of file handlers with one song being played, and one being loaded into
a buffer.

Specifics:

* Built in golang libraries for file management
* FFmepg bindings for streaming
https://github.com/giorgisio/goav 

## Frontend

The frontend for this project should consist of a featured website, including
song request out of a preselected library, and a webclient which can play
music from the server. 

The stream should also be available from an industry standard player, such as
VLC, iTunes, Winamp, etc.

Specifics:

* Website using Echo, a Golang web framework
* HTML web player
* Basic Authentication for admin and management pages.
* Certs provided by LetsEncrypt and auto renewed through by certbot. 

##Stretch Goals:

* Impliment OAuth through Google instead of basic HTTP authentication
* Allow file upload through the management interface
* Chat (possibly IRC) client
* Forum
* Song library for logged in users to petition songs to be added to the queue.
* Dockerfile to wrap all this up into a nice container for use in Gitlab CI
with an nginx reverse proxy.
