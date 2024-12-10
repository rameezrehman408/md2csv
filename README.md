# md2csv

Converts a Markdown document into a CSV file based on the document index, ignoring common sections such as the `Introduction`, `Definitions`, `Acknowledgements`, etc.

This application was written with the intention to create a quick compliance check list from requirements written in markdown such as the [CA/Browser Forum Documents](https://github.com/cabforum/documents) and the [Mozilla PKI Policy](https://github.com/mozilla/pkipolicy/).

## Install
```bash
go install github.com/digitorus/md2csv
```

## Usage
```bash
md2csv {url|filename}
md2csv {url|filename} {url|filename} {url|filename} ...

md2csv document.md
md2csv https://raw.githubusercontent.com/mozilla/pkipolicy/master/rootstore/policy.md
md2csv https://raw.githubusercontent.com/mozilla/pkipolicy/master/rootstore/policy.md document.md
md2csv https://raw.githubusercontent.com/cabforum/documents/master/docs/BR.md
md2csv https://raw.githubusercontent.com/cabforum/documents/master/docs/BR.md https://raw.githubusercontent.com/cabforum/documents/master/docs/EVG.md
```

Using [pdf2md](http://pdf2md.morethan.io/) you can convert a PDF document to Markdown so that you can use it with `md2csv`. 


## Using Docker

### Downloading the docker image
```bash
docker pull digitorus/md2csv
```

### Running the docker image
```bash
docker run -ti digitorus/md2csv sh
```

### Running the command
The above command will open a shell in the Docker container. To execute the command `md2csv`, use `./` before the command as following:
```bash
./md2csv {url|filename}
```

### Copying files to/from Docker image
The subject file from your local/host filesystem needs to be copied to the docker filesystem to execute the above command.For this purpose,  `docker cp` command can be used. `Docker cp --help` can be used to get more information about the command.

## Reconnect Docker image
```bash
docker ps -a
docker start {container id}
docker attach {container id}
```