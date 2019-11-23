# docker-gdal-openjdk

Alpine Based Docker image with GDAL and Java.
Designed to use as a base for a dockerized Geoserver including the OGR based WFS Output Format extension (https://docs.geoserver.org/stable/en/user/extensions/ogr.html)

## Supported tags

* `gdal_3.0.2_java_11.0.5`,  `latest`

## Build container

Build:

```bash
docker build -t dersteppen/docker-gdal-openjdk .
docker images dersteppen/docker-gdal-openjdk
docker tag xxxxx dersteppen/docker-gdal-openjdk:gdal_3.0.2_java_11.0.5
```

Push image to dockerhub:

    docker push dersteppen/docker-gdal-openjdk:gdal_3.0.2_java_11.0.5


## Usage example

Pull image:

    docker pull dersteppen/docker-gdal-openjdk

Show gdal version:

    docker run --rm dersteppen/docker-gdal-openjdk ogrinfo --version

Show java version:

    docker run --rm dersteppen/docker-gdal-openjdk java --version

List Supported vector formats: 
    
    docker run --rm dersteppen/docker-gdal-openjdk ogrinfo --formats | sort 

List Supported raster formats: 
    
    docker run --rm dersteppen/docker-gdal-openjdk gdalinfo --formats | sort 

Execute GDAL:

    docker run --rm -v /home:/home dersteppen/docker-gdal-openjdk gdalinfo $PWD/my.tif


## Contributing

You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull requests, and do our best to process them as fast as we can.

## License

This project is published under [MIT License](LICENSE).