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
├── playbook-install-terraform-bare-metal.yaml
├── playbook-config.yaml
├── argocd.yaml
├── service-account.yaml
├── clusterrole.yaml
├── role-binding.yaml
```


### Tools

- **Wsl** : v0.2.1
- **Terraform** : v1.15.8
- **OS Laptop 1** : Windows 11 Pro
- **OS WSL2 Subsystem** : Ubuntu 24.04 LTS
- **OS Ubuntu VM (K8s Nodes)** : 24.04 LTS
- **OS Ubuntu Jenkins Node (Bare Metal)** : 25.04
- **Kubernetes** : 1.28
- **Containerd** : 2.2.4
- **Java** : 21
- **Docker** : v29.1.3
- **Ansible** : v2.16+
- **Jenkins** : 2.56
- **Network** : Flannel
- **ArgoCD** : v3.5.x
- **GitLab** : SaaS
- **Ngrok** 

### Reasoning

Kenapa saya memutuskan untuk membuat pull based infrastructure?karena saya ingin sekali bereksperimen dan memiliki rasa penasaran karena ingin tahu cara kerja dari infrastructure pull 
based yang tadinya push based,dan di sisi lain saya bosan karena terus menerus membuat push based infrastructure,yang terakhir saya ingin mengasah skill saya juga dengan menantang diri 
saya mengenal hal baru atau teknologi baru

