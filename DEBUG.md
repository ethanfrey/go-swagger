# DEBUGGING TIPS

1) rename all imports in the cmd directory, or you use the official version, not the fork

2) to get godebug to run...

```
DOC=/home/localadmin/work/src/panono/api-server/docs/swagger

cd /home/localadmin/work/src/github.com/ethanfrey/go-swagger/cmd/swagger

godebug run -instrument github.com/ethanfrey/go-swagger/generator swagger.go generate model -f=${DOC}/params.yaml -t=${DOC}/out --name=Location --template-dir=/home/localadmin/work/src/github.com/ethanfrey/go-swagger/generator/templates

```

Compiling templates...

```
# (with ...?)
go get -u github.com/jteeuwen/go-bindata/
go-bindata -pkg generator -nocompress templates/...

```

Run for real:
```
go run swagger.go generate model -f=${DOC}/params.yaml -t=${DOC}/out --name=Location
```