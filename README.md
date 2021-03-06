# docker-graphite-api

Builds a docker image for running graphite-api web application running in
gunicorn and the carbon-cache metrics listener in container.

## Requirements

A working Docker setup and a valid shell (e.g., bash).

## Getting Started
Build the container and run it.

## Example
### Running the Container
```
./build.sh
docker run -t -i -d -p 8000:8000 -p 2003:2003 vmware-opencloud/graphite-api
```
This command opens a listener for metrics from other hosts or containers on
port 2003 and starts up the graphite api webapp on port 8000. 

### Sample Queries:
Once the graphite-api is installed and collecting metrics from some source
(such as collectd) queries may be made. Some samples:

    http://graphite-api:8000/metrics/find?query=collectd.*

Would show all the servers feeding metrics through collectd.

    http://graphite-api:8000/metrics/search?query=collectd.cna-ubuntu-0.*

Would list all the metrics collected by collectd on the server cna-ubuntu-0.

    http://graphite-api:8000/render?target=collectd.cna-ubuntu-0.cpu-0.cpu-*

would graph all the cpu metrics for cna-ubuntu-0.

More information may be found at
[the graphiteapi docs site](http://graphite-api.readthedocs.org/en/latest/api.html).

# License and Copyright
 
Copyright 2015 VMware, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


## Author Information

This role was created in 2015 by [Anne Ebie / VMware](http://www.vmware.com/).
