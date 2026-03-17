```posershell
ssh ops@coconut

ops@coconut:~$ cd /srv

ops@coconut:/srv$ cd qodo-merge/

ops@coconut:/srv/qodo-merge$ cd config

ops@coconut:/srv/qodo-merge/config$ nano configuration.toml

#restart
podman stop qodo-merge
podman rm qodo-merge
podman run -d \
  --name qodo-merge \
  --network qodo-merge_default \
  -p 3000:3000 \
  --add-host coconut:10.10.50.52 \
  -v /srv/qodo-merge/config/configuration.toml:/app/pr_agent/settings/configuration.toml:ro \
  -v /srv/qodo-merge/config/.secrets.toml:/app/pr_agent/settings/.secrets.toml:ro \
  --entrypoint /bin/sh \
  docker.io/codiumai/pr-agent:latest \
  -c "python -m pr_agent.servers.gitlab_webhook"


podman logs -f qodo-merge



```


## Search
https://qodo-merge-docs.qodo.ai/tools/review/?h=num_max_findings#configuration-options

## GitLab
http://10.10.50.52:8929/





/add_docs 
주석을 달아줍니다.