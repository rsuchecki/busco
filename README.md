# busco

busco license: MIT

## Useful Links

 * [package web-site](http://busco.ezlab.org/)
 * [container github-site](https://github.com/c-omics/samtools)
 * [Docker Hub](https://hub.docker.com/u/comics/)

## Example Usage
See the [container github-site](https://github.com/c-omics/) for further usage documentation.

To start a container:

```
docker run -it comics/busco bash
```

To process data sitting in your current working directory:

```
docker run -it -v $PWD:$PWD comics/busco bash -c "cd $PWD ; run_BUSCO.py [busco options]"
```

Or as an example:

```
docker run -it -v $PWD:$PWD comics/busco bash -c "cd $PWD ; run_BUSCO.py -i target.fa -o SAMPLE -l example -m genome -c 1 -sp fly"
```



