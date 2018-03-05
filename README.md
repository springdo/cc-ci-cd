## companyxyz Cluster Bootsrap

## TODOs
- remove ref to build pod dockerfile as springdo/lab-ci-cd


## Replacing  the `companyxyz` to something meaningful where `COMPANY_NEWNAME` is the new name
```
for file in $(ll | grep companyxyz |awk {'print $9'});do  newname=$(echo $file |sed -e 's/companyxyz\-/COMPANY_NEWNAME\-/g'); mv $file $newname;done
```


### run instructions
1. Close casl-ansible
```
git clone git@github.com:redhat-cop/casl-ansible.git casl-ansible
```

1. Login to Open Shift Cluster. Where ${OCP_USER} and ${OCP_PASS} are your username and password for the cluster
```
oc login https://console.companyxyz.rht-labs.com -u ${OCP_USER} -p ${OCP_PASS}
```

1. Run the playbook to bootstrap your cluster
```
ansible-playbook --connection=local -i inventory casl-ansible/playbooks/openshift-cluster-seed.yml
```
