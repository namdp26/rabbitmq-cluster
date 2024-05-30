# RabbitMQ Cluster Installation & Configuration MGMT

## How to deploy new RMQ cluster

Create `inventories\non-prod\<cluster_name>.yml` vault inventory file

Change or Create new vault env property in `group_vars\<cluster_name>.yml`

### Deploy new cluster from scratch:

```
ansible-playbook -i inventories/production/production site.yml --limit '<group-name>' -t install-config,cluster-setup,mgmt
```

### Add or update user permission:

Add user list into `group_vars\<cluster_name>.yml`

```
ansible-playbook -i inventories/production/production site.yml --limit '<group-name>' -t mgmt
```