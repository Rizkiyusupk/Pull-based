jika sebelumnya saya hanya membangun infrastructure push based sekarang saya akan membangun pull based menggunakan argo cd,karena rasa penasaran saya yang selalu bergejolak dan muncul saya
akhirnya memutuskan untuk belajar untuk membangun pull based dan memutuskan untuk menggunakan argo cd sebagai toolsnya,oke langsung saja masuk ke pembahaasanya

![vusbbra](/asset/as.png)



| Node        | CPU     | RAM  | Storage | Network                                             |
|-------------|---------|------|---------|---------------------------------------------------- |
| **Master-cluster-Jakarta**  | 2 cores | 2GB  | 10GB    | 1 Adapters   ( Static Ip )          |
| **Worker 1-cluster-Jakarta**| 2 cores | 2GB  | 10GB    | 1 Adapters   ( Static Ip )          |
| **Worker 2-cluster-Jakarta**| 2 cores | 2GB  | 10GB    | 1 Adapters   ( Static Ip )          |
| **Master-cluster-Bandung**  | 2 cores | 2GB  | 10GB    | 1 Adapters   ( Static Ip )          |
| **Worker 1-cluster-Bandung**| 2 cores | 2GB  | 10GB    | 1 Adapters   ( Static Ip )          |
| **Worker 2-Cluster-Bandung**| 2 cores | 2GB  | 10GB    | 1 Adapters   ( Static Ip )          |
| **Jenkins**                 | 7 cores | 7GB  | 240GB   |                Wlan                 |

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

