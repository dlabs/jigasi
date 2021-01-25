# buildpkg-debian

This Dockerfile produces development images that include [gitlab-buildpkg-tools](https://gitlab.com/Orange-OpenSource/gitlab-buildpkg-tools) scripts for the automatic build of .deb packages by Gitlab-CI.

For more information, see the home page of the project [gitlab-buildpkg-tools](https://gitlab.com/Orange-OpenSource/gitlab-buildpkg-tools).


Building:
```
docker build --tag deb_builder:0.1 .
```

Running:
```
docker run -v <jigasi project folder>:/home/jigasi -it deb_builder:0.1 bash
```