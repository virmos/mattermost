# HOW TO INSTALL
vim ~/.bashrc
```
export PATH=$PATH:/usr/local/go/bin
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$PATH
```
source ~/.bashrc

sudo apt-get install gcc-multilib

# DEBUGGING
```
dlv dap --listen 0.0.0.0:2345 debug "./cmd/mattermost" --build-flags="-ldflags -buildvcs=false '\
        -X github.com/mattermost/mattermost/server/public/model.BuildNumber=dev\
        -X \"github.com/mattermost/mattermost/server/public/model.BuildDate=n/a\"\
        -X github.com/mattermost/mattermost/server/public/model.BuildHash=f34445a6f4946ad19c24064d23ebe196f76bc7cf\
        -X github.com/mattermost/mattermost/server/public/model.BuildHashEnterprise=none\
        -X github.com/mattermost/mattermost/server/public/model.BuildEnterpriseReady=false'\
        -tags 'sourceavailable'"
```

# GENERATE DIAGRAM
https://github.com/jfeliu007/goplantuml

```
go get github.com/jfeliu007/goplantuml/parser
go install github.com/jfeliu007/goplantuml/cmd/goplantuml@latest
goplantuml -recursive -hide-methods -hide-private-members channels > diagram.puml
```