## CC Cluster Bootsrap 

## TODOs
- remove ref to build pod dockerfile as springdo/lab-ci-cd


### run instructions
1. Close casl-ansible
```
git clone git@github.com:redhat-cop/casl-ansible.git casl-ansible
```

1. Run the playbook to bootstrap your cluster 
```
ansible-playbook --connection=local -i files/inventory casl-ansible/playbooks/openshift-cluster-seed.yml 
```