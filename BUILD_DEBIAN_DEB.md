
# make debian deb-packages

## Install Docker

   * apt install docker.io git

## Build base image for package building

   * git clone this repository
   * cd to the root of this repository
   * choose wanted Debian release

```
  $ docker build -t apache-gelf-debian7  dist/debian7/
  $ docker build -t apache-gelf-debian8  dist/debian8/
  $ docker build -t apache-gelf-debian9  dist/debian9/
  $ docker build -t apache-gelf-debian10 dist/debian10/
```

## Build deb -binary package using above built image

   * clean build environment from previous runs (if any)
```
  $ rm -r dist/cache dist/tmp-*
```

   * run one of the below depending on the chosen Debian release

```
  $ docker run --rm=true -v `pwd`:/apache-gelf -t -i apache-gelf-debian7  fpm-cook package /apache-gelf/dist/recipe.rb
  $ docker run --rm=true -v `pwd`:/apache-gelf -t -i apache-gelf-debian8  fpm-cook package /apache-gelf/dist/recipe.rb
  $ docker run --rm=true -v `pwd`:/apache-gelf -t -i apache-gelf-debian9  fpm-cook package /apache-gelf/dist/recipe.rb
  $ docker run --rm=true -v `pwd`:/apache-gelf -t -i apache-gelf-debian10 fpm-cook package /apache-gelf/dist/recipe.rb
```

# License

Copyright (C) 2015 Graylog, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
