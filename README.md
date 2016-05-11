# docker-stress
Lighweight docker image for stress tool


## stress

The related informations are [here](http://people.seas.harvard.edu/~apw/stress/)

## Build

```
$ docker build -t stress .
```

## Run

Display usages :

```
$ docker run -it stress
`stress' imposes certain types of compute stress on your system

Usage: stress [OPTION [ARG]] ...
 -?, --help         show this help statement
     --version      show version statement
 -v, --verbose      be verbose
 -q, --quiet        be quiet
 -n, --dry-run      show what would have been done
 -t, --timeout N    timeout after N seconds
     --backoff N    wait factor of N microseconds before work starts
 -c, --cpu N        spawn N workers spinning on sqrt()
 -i, --io N         spawn N workers spinning on sync()
 -m, --vm N         spawn N workers spinning on malloc()/free()
     --vm-bytes B   malloc B bytes per vm worker (default is 256MB)
     --vm-stride B  touch a byte every B bytes (default is 4096)
     --vm-hang N    sleep N secs before free (default none, 0 is inf)
     --vm-keep      redirty memory instead of freeing and reallocating
 -d, --hdd N        spawn N workers spinning on write()/unlink()
     --hdd-bytes B  write B bytes per hdd worker (default is 1GB)

Example: stress --cpu 8 --io 4 --vm 2 --vm-bytes 128M --timeout 10s

Note: Numbers may be suffixed with s,m,h,d,y (time) or B,K,M,G (size).
```

Run stress workers :

```
$ docker run stress --cpu 2 --io 1 --vm 1 --vm-bytes 128M --timeout 10s
stress: info: [1] dispatching hogs: 2 cpu, 1 io, 1 vm, 0 hdd
stress: info: [1] successful run completed in 10s
```

## Docker hub

[Repository](https://hub.docker.com/r/lorel/docker-stress/)

## License

[GPLv2](http://www.fsf.org/licenses/info/GPLv2.html)
