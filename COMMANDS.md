docker build -t pqhdistributedcomputelab .
docker run -it --name pqh_distlab_01 pqhdistributedcomputelab /bin/bash
docker run -v ./:/mnt/datalake/instructor -it --name pqh_distlab_01 pqhdistributedcomputelab /bin/bash
