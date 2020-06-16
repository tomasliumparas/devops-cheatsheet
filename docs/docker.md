## Custom formatting

``` tab="Command"
docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Size}}\t{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
```

```bash tab="Output"
[root@docker03 tl]# docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Size}}\t{{.RunningFor}}\t{{.Status}}\t{{.Names}}"
CONTAINER ID        IMAGE                              SIZE                      CREATED             STATUS                    NAMES
760868f422e7        hc-docs                            22kB (virtual 349MB)      34 hours ago        Up 13 minutes             hc-docs
ed6472d97f53        mkdocs-example                     22kB (virtual 520MB)      34 hours ago        Up 13 minutes             mkdocs-example
b9916d2c07a2        syncthing/syncthing:latest         0B (virtual 27.4MB)       2 days ago          Up 13 minutes (healthy)   syncthing
7b8063ed5fc1        drone/drone-runner-docker:latest   0B (virtual 20.6MB)       2 weeks ago         Up 13 minutes             drone-runner
cfa7878e62d7        drone/drone:latest                 0B (virtual 67.6MB)       2 weeks ago         Up 13 minutes             drone
f8ce88dd8100        jordan/hubot-slack                 9.66MB (virtual 1.01GB)   4 months ago        Up 13 minutes             hubot
```
