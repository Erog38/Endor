# Plan

In this project, I have a timeline built around the needs for the Free Music 
Archive. With their annual fundraiser happening, I am awaiting an API token
from them, provided after October 15th, 2017.

With this in mind, the project will be built in four parts:

### Oct 04:
    
    By this date, I will have a thin front end using React which will provide
    information about the stream, myself, and the audio provider, 
    Free Music Archive. This time will be used mainly for design, planning, 
    and foundational setup for a webserver, repositories, and integration tools
    through gitlab.

### Oct 23:

    By this date, I will have an API token from the Free Music Archive, 
    and will have a working REST API to request tracks be added to  the
    queue, as well as to get information on the current song, and upcoming 
    songs in the playlist. If possible, I will also add a section for 
    an admin call to delete songs if provided the correct credentials via 
    basic auth.

    Songs will be downloaded in such a way that there are always two songs
    downloaded in the upcoming queue. 

    Groundwork will also be in place for songs to be dequeued and played 
    via FFMpeg.

### Nov 08:

    By this date, I will have a hold on the FFMpeg bindings for Golang, and 
    will have a thin working version of the streaming server, connected into
    the API built in the previous sprint. A user should be able to listen to 
    the stream via streaming clients such as VLC, which will also be the main
    client I will user for testing.

    I should also have a small html/js client for the browser to listen in to 
    the stream. 

### Nov 27:

    This time will be dedicated to the Front End, with design and user 
    experience in mind, I will also be using this time to test the internet
    radio stream through users and family members. 

    The main piece of this sprint is to ensure the user can have a simple, 
    usable, and well designed interface to access the Radio Stream.
