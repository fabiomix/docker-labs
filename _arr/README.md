# The Arr Stack
Documentation on the popular media downloading tools collectively referred as
"*Arr" or "*Arrs", designed to automatically grab, sort, organize, and monitor
your Music, Movies, E-Book, and/or TV show collections.

This is just a proof of concept, you probably need a VPN if you want to use this
in a production environment.

## Contents
- sonarr: collection manager for TV shows
- radarr: collection manager for movies
- bazarr: manages and downloads subtitles
- lidarr: collection manager for music albums
- readarr: collection manager for eBooks
- prowlarr: indexer manager/proxy for torrent trackers
- transmission: a fast, easy, and free cross-platform bittorrent client

All the docker images are built by linuxserver.io, you can check their docs for
more details and options.

## Volumes
Single storage volume to allow hardlinks and instant/atomic moves.

    mkdir -p config/{bazarr,lidarr,prowlarr,radarr,readarr,sonarr,transmission}
    mkdir -p storage/{books,downloads,movies,music,tv,watch}

## Setup
When linking one service to another, remember to use the container name instead
of `localhost`.

Set the advanced settings of the -arr containers as soon as possible to the
following:
- Media management - Use hardlinks instead of Copy: true
- Media management - Root folder: /data/ and then tv, movies or music depending
  on service
- General - Send Anonymous Usage Data: false
