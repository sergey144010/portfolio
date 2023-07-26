# Develop
## Run

Use docker image for compile stylus files
https://hub.docker.com/r/gruen/stylus

Presettings
```
chmod a+rw  styles/stylus/main.styl
chmod a+rw  styles/css/styles.css
chmod o+w styles/css
chmod o+w styles/stylus
```

Run without output
```
docker run -d --rm \
    -v ${PWD}/styles/stylus:/inputfiles \
    -v ${PWD}/styles/css:/outputfiles \
    --name stylus"$(date +%N)" \
    gruen/stylus \
    -w /inputfiles/main.styl \
    -o /outputfiles/styles.css
```

Run with output
```
docker run --rm \
    -v ${PWD}/styles/stylus:/inputfiles \
    -v ${PWD}/styles/css:/outputfiles \
    --name stylus"$(date +%N)" \
    gruen/stylus \
    -w /inputfiles/main.styl \
    -o /outputfiles/styles.css
```
