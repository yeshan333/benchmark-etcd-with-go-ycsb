
# using go-ycsb to benchmark etcd.

## Requirements

- [go-ycsb](https://github.com/pingcap/go-ycsb)
- etcd
- [Docker-Compose](https://docs.docker.com/compose/)

## Quick Start

```shell
git clone git@github.com:yeshan333/benchmark-etcd-with-go-ycsb.git

cd benchmark-etcd-with-go-ycsb

# download go-ycsb (linux)
cd bin
wget -c https://github.com/pingcap/go-ycsb/releases/latest/download/go-ycsb-linux-amd64.tar.gz -O - | tar -xz
cd ..

# start up etcd
docker-compose up -d

# load test data
./bin/go-ycsb load etcd -P workloads/etcd_offcial_workload

# running test
./bin/go-ycsb run etcd -P workloads/etcd_offcial_workload
```