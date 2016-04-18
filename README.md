A very simple NginX/RTMP setup loosely based on jasonrivers/nginx-rtmp.

Simply spin up the image like so:

```
docker volume create --name recordings
docker run -d --name rtmpsrv -v recordings:/recordings -p 80:80 -p 1935:1935 madsen/nginx-rtmp:latest
```

Then point your streaming software at: rtmp://localhost/live[/helloworld] and
your video player at the same. Recordings will be stored in 5-hour chunks in
the 'recordings' volume.
