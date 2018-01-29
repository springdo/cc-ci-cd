## Elisa Cluster Bootsrap 

## TODOs
- remove ref to build pod dockerfile as springdo/lab-ci-cd


### run instructions
1. 
```
git clone git@github.com:redhat-cop/casl-ansible.git c8.core.rht-labs.com/casl-ansible
```
1. 
```
ansible-playbook --connection=local -i seed-hosts.yml casl-ansible/playbooks/openshift-cluster-seed.yml
 
```