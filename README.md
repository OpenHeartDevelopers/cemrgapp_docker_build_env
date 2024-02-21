# README
This is a docker container, which allows to virtualise Ubuntu (18.04 or 20.04) to build CemrgApp.

### Normal Usage 
Assume you have the following in your computers: 
+ A folder with a pre-build version of CemrgApp in `$CEMRG_BUILD` 
+ Source code for CemrgApp in `$CEMRG_SRC`
+ You need to choose a `$TAG`, which can be `18.04` or `20.04`

> Note that 18.04 builds CemrgApp 2 and 20.04 builds CemrgApp 3
> CemrgApp 3 is not yet functional !!! 

Pull the docker image that you want (so far only supported: `cemrg/app:18.04`)

```
docker pull cemrg/app:18.04
```

You would call the docker container as follows 
```sh
docker run -ti --rm --volume=$CEMRG_SRC:/CemrgApp --volume=$CEMRG_BUILD:/Build cemrg/app:$TAG
```

then, inside the container you would run 
```sh
cmake .
make -j 
```
The first time it takes a long time. Subsequent times are quicker. 
