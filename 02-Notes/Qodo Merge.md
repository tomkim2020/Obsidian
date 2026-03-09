```posershell
ssh ops@coconut

ops@coconut:~$ cd /srv

ops@coconut:/srv$ cd qodo-merge/

ops@coconut:/srv/qodo-merge$ cd config

ops@coconut:/srv/qodo-merge/config$ nano configuration.toml

#restart
ops@coconut:/srv/qodo-merge/config$ cd ..
ops@coconut:/srv/qodo-merge$ podman-compose down
ops@coconut:/srv/qodo-merge$ podman-compose up -d
ops@coconut:/srv/qodo-merge$ podman-compose ps
```


## Search
https://qodo-merge-docs.qodo.ai/tools/review/?h=num_max_findings#configuration-options

## GitLab
http://10.10.50.52:8929/