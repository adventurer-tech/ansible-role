# adventurer-role

adventurer-tech 1.0 的 ansible role，用于部署

### 重要

- finance 第一次启动，如果连接不上数据库需要 force delete pod 重启一下服务

postgresql 检查是否有 transaction 卡主，并且删除之，[参考](https://medium.com/little-programming-joys/finding-and-killing-long-running-queries-on-postgres-7c4f0449e86d)


```
SELECT
  pid,
  now() - pg_stat_activity.query_start AS duration,
  query,
  state
FROM pg_stat_activity
WHERE (now() - pg_stat_activity.query_start) > interval '5 minutes';
```

删除卡主的

```
SELECT pg_terminate_backend(__pid__);
```

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

## Develop guide

Link to local installed role for convenience.

```
rm -rf /Users/zzs/.ansible/roles/36node.project.adventurer
ln -s $PWD /Users/zzs/.ansible/roles/36node.project.adventurer
```

## License

BSD

## Author Information

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
