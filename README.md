# CentOS 7 upstream repositories

When you're provisioning software onto a machine that will run in Production, you don't want to be running software from _anywhere_. You need to know that you can _trust_ the source of the software before you ship it into Production.

In our case, we run CentOS. These are our criteria for determining whether or not to trust a package.

1. Packages are maintained by CentOS/RedHat directly.
2. Packages are maintained by the vendor of the software directly.
3. Packages are maintained by a reputable third-party source (as few of these as possible).
4. Packages are maintained by us. That is, [we compile them from source ourselves](https://github.com/lru-packages).

Your criteria may look different. If you don't have criteria, and generally just install software from anywhere, I have two pieces of advice.

1. Stop it.
2. Our criteria has been very good to us. Feel free to borrow ours.

## CentOS/RedHat-owned repos

* [CentOS Plus](http://mirror.centos.org/centos-7/7/centosplus/x86_64/)
* [Continuous Release](http://mirror.centos.org/centos-7/7/cr/x86_64/)
* [EPEL](http://dl.fedoraproject.org/pub/epel/7/x86_64/)
* [Extras](http://mirror.centos.org/centos-7/7/extras/x86_64/)
* [Fast Track Fixes](http://mirror.centos.org/centos-7/7/fasttrack/x86_64/)
* [Gluster](http://mirror.centos.org/centos-7/7/storage/x86_64/gluster-3.7/)
* [OpenStack](http://mirror.centos.org/centos-7/7/cloud/x86_64/openstack-liberty/)
* [OS Packages](http://mirror.centos.org/centos-7/7/os/x86_64/)
* [Updates](http://mirror.centos.org/centos-7/7/updates/x86_64/)
* [Virtualization](http://mirror.centos.org/centos-7/7/virt/x86_64/xen/)

## Vendor-approved first/second-party repos

* [Couchbase](http://packages.couchbase.com/releases/couchbase-server/community/rpm/7/x86_64)
* [Docker](http://yum.dockerproject.org/repo/main/centos/7/)
* [Duo Security](http://pkg.duosecurity.com/CentOS/7/x86_64/)
* [Elastic Beats](https://packages.elastic.co/beats/yum/el/x86_64/)
* [Elastic Curator](https://packages.elastic.co/curator/3/centos/7/)
* [Elastic Logstash](https://packages.elastic.co/logstash/2.1/centos/)
* [Elastic Search](https://packages.elastic.co/elasticsearch/2.x/centos/)
* [Erlang](http://packages.erlang-solutions.com/rpm/centos/7/x86_64/)
* [Facebook OSQuery](https://s3.amazonaws.com/osquery-packages/centos7/x86_64/)
* [Git-LFS](https://packagecloud.io/github/git-lfs/el/7/x86_64)
* [Google Stackdriver](http://repo.stackdriver.com/repo/el7/x86_64/)
* [Grafana](https://packagecloud.io/grafana/stable/el/7/x86_64)
* [Mongo DB](https://repo.mongodb.org/yum/redhat/7/mongodb-org/3.3/x86_64/)
* [MySQL 5.5](https://repo.mysql.com/yum/mysql-5.5-community/el/7/x86_64/)
* [MySQL 5.6](https://repo.mysql.com/yum/mysql-5.6-community/el/7/x86_64/)
* [MySQL 5.7](https://repo.mysql.com/yum/mysql-5.7-community/el/7/x86_64/)
* [MySQL Connectors](https://repo.mysql.com/yum/mysql-connectors-community/el/7/x86_64/)
* [MySQL Tools](https://repo.mysql.com/yum/mysql-tools-community/el/7/x86_64/)
* [New Relic](https://yum.newrelic.com/pub/newrelic/el5/x86_64/)
* [Nginx](http://nginx.org/packages/centos/7/x86_64/)
* [PostgreSQL 9.6](https://download.postgresql.org/pub/repos/yum/9.6/redhat/rhel-7-x86_64)
* [Rsyslog](http://rpms.adiscon.com/v8-stable/epel-7/x86_64/)
* [Sensu monitoring](http://repositories.sensuapp.org/yum/7/x86_64/)
* [VirtualBox](http://download.virtualbox.org/virtualbox/rpm/rhel/7/x86_64/)
* [Yarn](https://dl.yarnpkg.com/rpm/)

## Trusted third-party repos

* [Cityfan](http://www.city-fan.org/ftp/contrib/yum-repo/rhel7/x86_64/) — The least trusted of the bunch. Provides modern cURL packages. (cURL didn't receive support for TLS 1.1/1.2 until version 7.34.0. CentOS 6 ships with 7.19.0. CentOS 7 ships with 7.29.0.)
* [Remi](http://mirrors.mediatemple.net/remi/enterprise/7/remi/x86_64/) — _Remi_ is a member of the RedHat SCL group. He packages modern PHP builds for RedHat/CentOS.
* [Nodesource 0.12](https://rpm.nodesource.com/pub_0.12/el/7/x86_64/), [4.x](https://rpm.nodesource.com/pub_4.x/el/7/x86_64/), [5.x](https://rpm.nodesource.com/pub_5.x/el/7/x86_64/), [6.x](https://rpm.nodesource.com/pub_6.x/el/7/x86_64/), [7.x](https://rpm.nodesource.com/pub_7.x/el/7/x86_64/) — Nodesource is a trusted member of the Node.js community.

## Custom-built package repos

* [Custom-built packages: el7](https://github.com/lru-packages)
* [Custom-built packages: nodist](https://github.com/lru-packages)

### Which Packages?

[Build scripts for these packages](https://github.com/lru-packages) are available for inspection. In the meantime, these are the packages you'll find in the Lucky Rocketship Underpants repos. I generally try to stay on top of updates, and will keep old versions around for some time as to not break your provisioning scripts which grab specific versions.

**All** packages are built against CentOS 7 x86_64.

```bash
yum list | grep -i direct-centos7-custom
```

* [Autoconf](http://www.gnu.org/software/autoconf/autoconf.html) 2.69
* [Automake](https://www.gnu.org/software/automake/) 1.15
* [Chag](https://github.com/mtdowling/chag) 1.1.4
* [CMake](https://github.com/Kitware/CMake) 3.7.2
* [cmark](https://github.com/jgm/cmark) 0.27.1
* [Docker Compose](https://www.docker.com/products/docker-compose) 1.10.0
* [GCC](http://gcc.gnu.org) 6.3.0
* [Git](https://git-scm.com) 2.11.0
* [GitHub Hub](https://hub.github.com) 2.2.9
* [Golang](https://golang.org) 1.7.5
* [Hashicorp Consul](https://www.consul.io) 0.7.3
* [Hashicorp Terraform](https://www.terraform.io) 0.8.5
* [Hashicorp Vault](https://www.vaultproject.io) 0.6.4
* [HHVM](http://hhvm.com) 3.15.4
* [hiredis](https://github.com/redis/hiredis) 0.13.3
* [httpstat](https://github.com/davecheney/httpstat) 1.0.0
* [jq](https://stedolan.github.io/jq/) 1.5
* [LLVM, Clang, LLDB, LLD](http://www.llvm.org) 3.9.1
* [Ninja Build](https://ninja-build.org) 1.7.2
* [Oracle Java](http://www.oracle.com/technetwork/java/javase/downloads/) 8u121 + the unlimited crypto package
* [Pandoc](http://pandoc.org) 1.19.1
* [Packer](https://packer.io) 0.12.2
* [pfff](https://github.com/facebook/pfff/wiki/Main) 0.29
* [PlantUML](http://plantuml.com) 8054
* [Python](https://www.python.org) 2.7.13 and 3.6.0
* [Ruby](https://www.ruby-lang.org/) 2.4.0
* [server-info](https://github.com/skyzyx/server-metadata) 1.0.0
* [Siege](https://github.com/JoeDog/siege) 4.0.0
* [sift](https://sift-tool.org) 0.9.0
* [Square Certstrap](https://github.com/square/certstrap) 1.0.1
* [Statsite](http://armon.github.io/statsite/) 0.7.1
