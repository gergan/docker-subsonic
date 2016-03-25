gergan/subsonic
=================

This Dockerfile is cloned from mbentley/docker-subsonic

Changes made:
- Change the alpine repo-url (the original one is somwhat flaky)
- add flac and lame
- add a special volume for the music (I need it readonly for example)
- fix the gid/uid not really nice but for now will do
- add ttf-dejavu and fontconfig in order to fix the stats-graphics
- execute all the commands in one line in order to minimize layers
docker image for subsonic; utilizes libre subsonic from https://github.com/EugeneKay/subsonic

To pull this image:
`docker pull gergan/alpine-subsonic`

Example usage:
`docker run -d -p 4040:4040 -p 4443:4443 -v /somemousic:/music:ro -v /data/subsonic:/data --name subsonic gergan/alpine-subsonic`
