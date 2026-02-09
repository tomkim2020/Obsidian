==ssh -p 22 kth@10.10.50.52== : ssh [사용자ID]@[서버IP] 
==su -== : (Switch User) - 는 root의 환경 변수까지 모두 가져오겠다는 의미

==lsblk== (List Block Devices) : 물리 디스크 확인
==df - h== (Disk Free) : -h는 사람이 읽기 편한 단위(GB, TB)로 보여달라는 옵션
==apt update== : 업데이트 확인
==cat /etc/os-release== version 확인
==hostnamectl== 커널 버전, 아키텍처, OS 정보를 요약
cd ~ 계정의 디렉토리로


```
ops@coconut:~$ cd /srv
ops@coconut:/srv$ ls
gitlab  oracle  samba
ops@coconut:/srv$ cd oracle
ops@coconut:/srv/oracle$ ls
podman-compose.yml  scripts
ops@coconut:/srv/oracle$ cat podman-compose.yml
services:
  oracledb:
    image: container-registry.oracle.com/database/free:latest
    container_name: oracledb
    restart: unless-stopped
    ports:
      - "1521:1521"
      - "5500:5500"
    environment:
      ORACLE_PWD: "${ORACLE_PWD}"
      ORACLE_CHARACTERSET: "AL32UTF8"
    volumes:
      - oracle_data:/opt/oracle/oradata
      - spectra_data:/dbfs/oradata/SPECTRA
      - /srv/oracle/scripts:/opt/oracle/scripts:ro
    shm_size: 2gb
    ulimits:
      nofile:
        soft: 65536
        hard: 65536

volumes:
  oracle_data:
    driver: local
  spectra_data:
ops@coconut:/srv/oracle$ cd /
ops@coconut:/$ ls
bin   data  etc   initrd.img      lib    lost+found  mnt  proc  run   srv  tmp  var      vmlinuz.old
boot  dev   home  initrd.img.old  lib64  media       opt  root  sbin  sys  usr  vmlinuz
ops@coconut:/$ cd data
ops@coconut:/data$ ls
archive
ops@coconut:/data$ cd archive/
ops@coconut:/data/archive$ l
-bash: l: command not found
ops@coconut:/data/archive$ ls
samba_data
ops@coconut:/data/archive$ cd samba_data/
ops@coconut:/data/archive/samba_data$ ls
djheo  ghkim   jdbae  kth       msham   nrlee         prj-server1  team-shared
dwnoh  hsshin  jykim  main-r-1  mskim2  prj-database  prj-server2  wyyoon
ops@coconut:/data/archive/samba_data$ ls -al
total 4
drwxr-xr-x 18 root   root   4096 Jan 21 23:55 .
drwxr-xr-x  3 root   root     24 Jan 10 02:19 ..
drwx------  2 232080 231171    6 Jan 11 23:10 djheo
drwx------  2 232078 231171    6 Jan 11 23:10 dwnoh
drwx------  2 232076 231171    6 Jan 11 23:10 ghkim
drwx------  7 232072 231171  104 Jan 21 20:28 hsshin
drwx------  2 232073 231171    6 Jan 11 23:09 jdbae
drwx------  2 232079 231171    6 Jan 11 23:10 jykim
drwx------  2 232071 231171    6 Jan 11 22:23 kth
drwxr-xr-x  3 232082 231171   22 Jan 22 01:21 main-r-1
drwx------  2 232081 231171    6 Jan 11 23:31 msham
drwx------  2 232075 231171    6 Jan 11 23:10 mskim2
drwx------  2 232074 231171    6 Jan 11 23:23 nrlee
drwxrwxrwx  2 ops    ops       6 Jan 11 23:40 prj-database
drwxrwxrwx  2 ops    ops       6 Jan 11 23:31 prj-server1
drwxrwxrwx  2 ops    ops       6 Jan 11 23:43 prj-server2
drwxrwxrwx  2 ops    ops      48 Jan 22 00:38 team-shared
drwx------  2 232077 231171    6 Jan 11 23:10 wyyoon
ops@coconut:/data/archive/samba_data$
```