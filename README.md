## Debian works

``` bash
$ docker run -t debian:bullseye-slim bash -c 'echo $PATH'
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
$ act -P ubuntu-latest=debian:bullseye-slim
[CI/build]   🐳  docker exec cmd=[bash --noprofile --norc -e -o pipefail /var/run/act/workflow/0] user= workdir=
| PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

## Ubuntu doesn't

``` bash
$ docker run -t ubuntu:jammy bash -c 'echo $PATH'
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
$ act -P ubuntu-latest=ubuntu:jammy
[CI/build]   🐳  docker exec cmd=[bash --noprofile --norc -e -o pipefail /var/run/act/workflow/0] user= workdir=
| PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin":/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

