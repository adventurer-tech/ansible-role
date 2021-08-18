# adventurer-role

adventurer-tech 1.0 的 ansible role，用于部署

### 重要

- finance 第一次启动，如果连接不上数据库需要 force delete pod 重启一下服务

### 其他

- ~~kanban 的 url 只接受/v0，而 traefik 无法像 nginx 定义正则匹配，因此把 api 的 ingress 放到 pod 的配置文件中~~
- 使用`helm install pgadmin runix/pgadmin4 --namespace adv-uat -f ./files/pgadmin.yml`安装 pgadmin4，访问地址为`pgadmin.adv-uat.36node.com`，登录账号`chart@example.local`，登录 pwd`SuperSecret`，参考地址`https://github.com/rowanruseler/helm-charts/tree/master/charts/pgadmin4`

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

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
