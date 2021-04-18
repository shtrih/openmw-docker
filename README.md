# OpenMW-docker

Build and run OpenMW inside a Docker container on Windows 10.

This is definitely a hack. The idea is to be able to build and debug OpenMW
without having to install its build dependencies, it has only been tested on
Windows 10 (v. 20H2) WSL 2 (Ubuntu 20.04 Focal) and is not expected to function anywhere else.

You need to [install Docker under WSL](https://docs.docker.com/engine/install/ubuntu/) (not on windows host).
Also it is required [X410](https://www.microsoft.com/en-us/p/x410/9nlp712zmn9q?rtc=1&activetab=pivot:overviewtab). I believe that it can be replaced by `VcXsrv` but it's not tested.
More info: [using-x410-with-wsl2](https://x410.dev/cookbook/wsl/using-x410-with-wsl2/)

This repo builds OpenMW [Lua](https://gitlab.com/OpenMW/openmw/-/merge_requests/430) branch to work with scripts.

---
UPDATE: This solution has the same camera issues (pure WSL2 too!): https://forum.openmw.org/viewtopic.php?t=6869&p=67354

No luck ¯\\(°_o)/¯

## Build
```shell
$ git submodule update --init
$ docker build . -t openmw
## Run X410 in «windowed apps» mode with «allow public access» on Windows.
## Create and edit .env then export environmnet variables:
$ source .env
$ ./test-display
$ ./build
## To configure, it will fail to run the game when you click play.
$ ./launcher 
$ ./run
```
