### STRUCTURE FOLDER 

Ada dua config folder yang pertama untuk provisioning node,yang kedua itu untuk provsioning k8s dan yang terakhir untuk cluster side  alertmanager yang pertama terlebih 
dahulu

```
terraform-setup/
├── .terraform/
├── compute.tf
├── main.tf
├── prep-vm.tf
├── compute-cluster-2.tf
├── prep-2.tf
```

lalu yang kedua

```
k8s/
├── ansible.cfg
├── inventory
├── playbook-allow-port.yaml
├── playbook-enable-service-baremetal.yaml
├── playbook-ip.yaml
├── playbook-install-java-baremetal.yaml
├── playbook-install-jenkins-baremetal.yaml
├── playbook-install-kubectl-baremetal.yaml
├── playbook-join.yaml
├── playbook-kubernetes.yaml
├── playbook-pkg.yaml
├── playbook-swap.yaml
├── observ.yaml
├── observ_2.yaml
├── argocd.yaml
```

dan yang ketiga

```
cluster-side/
├── alsertmanager-telegram.yaml
```
