# vicar-api

Download the main VICAR source code tarball from NASA repo here: https://github.com/nasa/VICAR/ 

You need to add the vicset1 and vicset2 scripts to vos's .cshrc folder so all the environment variables are setup correctly. 

### vos .cshrc file ###
`setenv V2TOP /vos/vicar_open_3.0`

`source $V2TOP/vicset1.csh`

`source $V2TOP/vicset2.csh`

`setenv PATH $PATH\:$R2LIB`


### X11 forwarding, and mount folder to read/write files from container to local filesystem ###

docker run -td -w /mnt/vicar -u vos --env="DISPLAY" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" -v *local-filesystem-folder*:/mnt/vicar <container id> "/bin/bash"
  

Then run `docker exec -it *container-id* /bin/bash` or `/bin/csh`
