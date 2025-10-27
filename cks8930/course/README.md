# Commands

```bash
1  sudo apt-get install kubeadm=1.33.1 -y
    2  sudo apt-get install kubeadm=1.33.1-1.1 -y
    3  kubectl get nodes
    4  kubeadm upgrade node
    5  sudo kubeadm upgrade node
    6  sudo apt-get install kubelet=1.33.1-1.1 kubectl=1.33.1-1.1 -y
    7  sudo systemctl restart kubelet
    8  kubectl get nodes
    9  kubectl uncordon cks8930-node1 
   10  kubectl get pods
   11  kubectl get pods -w
   12  exit
   13  lsof -ti :6666
   14  sudo lsof -ti :6666
   15  ps aux | grep 6666
   16  cat /proc/7321/exe 
   17  sudo cat /proc/7321/exe 
   18  sudo ls /proc/7321/exe 
   19  sudo ls /proc/7321/cmdline 
   20  sudo cat /proc/7321/cmdline 
   21  sudo cat /proc/7321/comm 
   22  kill $(lsof -ti :6666)
   23  sudo kill $(lsof -ti :6666)
   24  sudo kill -9 $(lsof -ti :6666)
   25  sudo lsof -ti :6666
   26  sudo kill 7321
   27  sudo rm /bin/system-atm 


  1  kubectl get cm -n kube-system
    2  kubectl -n kube-system edit cm kubelet-config 
    3  vi /var/lib/kubelet/config.yaml 
    4  kubeadm upgrade node --kubelet
    5  kubeadm upgrade node phase kubelet-config
    6  sudo -i
    7  exit
    8  ssh cks8930-node1 
    9  trivy image k8s.gcr.io/kube-controller-manager:v1.18.0 | grep -e CVE-2020-10878 -e CVE-2020-1967
   10  exit
   11  bom --version
   12  bom version
   13  bom generate help
   14  bom generate --hep
   15  bom generate --help
   16  bom generate --image registry.k8s.io/kube-apiserver:v1.31.0
   17  bom generate --image registry.k8s.io/kube-apiserver:v1.31.0 --format json
   18  bom generate --image registry.k8s.io/kube-apiserver:v1.31.0 --format json --output /opt/course/18/sbom1.json
   19  trivy image --help
   20  trivy image registry.k8s.io/kube-controller-manager:v1.31.0 --format cyclonedx --output /opt/course/18/sbom2.json
   21  vi /opt/course/18/sbom2.json
   22  trivy --help
   23  trivy sbom --help
   24  kubectl get nodes
   25  sudo ETCDCTL_API=3 etcdctl --endpoint https://127.0.0.1:2379 --cert /etc/kubernetes/pki/apiserver-etcd-client.crt --key /etc/kubernetes/pki/apiserver-etcd-client.key --cacert /etc/kubernetes/pki/etcd/ca.crt snapshot save cks8930-snapshot.db
   26  sudo ETCDCTL_API=3 etcdctl --endpoints https://127.0.0.1:2379 --cert /etc/kubernetes/pki/apiserver-etcd-client.crt --key /etc/kubernetes/pki/apiserver-etcd-client.key --cacert /etc/kubernetes/pki/etcd/ca.crt snapshot save cks8930-snapshot.db
   27  ls
   28  kubectl get nodes
   29  sudo vi /etc/apt/sources.list.d/kubernetes.list 
   30  sudo apt-mark unhold kubeadm
   31  sudo apt-mark hold kubectl kubelet
   32  sudo apt-cache madison kubeadm
   33  sudo apt-get update kubeadm=1.33.1-1.1 -y
   34  sudo apt-get install kubeadm=1.33.1-1.1 -y
   35  sudo kubeadm upgrade plan
   36  sudo kubeadm upgrade apply 1.33.1 -y
   37  kubectl get nodes
   38  sudo apt-get install kubelet=1.33.1-1.1 kubectl=1.33.1-1.1 -y
   39  sudo apt-mark unhold kubelet kubectl
   40  sudo apt-get update
   41  sudo apt-get install kubelet=1.33.1-1.1 kubectl=1.33.1-1.1 -y
   42  sudo systemctl restart kubelet
   43  kubectl cordon cks8930-node1 
   44  kubectl drain cks8930-node1 --ignore-daemonsets
   45  trivy image nginx:1.16.1-alpine | grep -e CVE-2020-10878 -e CVE-2020-1967
   46  trivy image k8s.gcr.io/kube-apiserver:v1.18.0 | grep -e CVE-2020-10878 -e CVE-2020-1967
   47  trivy image docker.io/weaveworks/weave-kube:2.7.0 | grep -e CVE-2020-10878 -e CVE-2020-1967
   48  echo docker.io/weaveworks/weave-kube:2.7.0 > /opt/course/21/good-images
   49  cd /opt/course/22/files/
   50  ls
   51  vi Dockerfile-go 
   52  vi Dockerfile-mysql 
   53  echo Dockerfile-mysql  >> /opt/course/22/security-issues
   54  vi Dockerfile-py 
   55  vi deployment-nginx.yaml 
   56  vi deployment-redis.yaml 
   57  echo deployment-redis.yaml  >> /opt/course/22/security-issues
   58  vi pod-nginx.yaml 
   59  echo pod-nginx.yaml  >> /opt/course/22/security-issues
   60  vi pv-manual.yaml 
   61  vi pvc-manual.yaml 
   62  vi sc-local.yaml 
   63  vi statefulset-nginx.yaml 
   64  echo statefulset-nginx.yaml  >> /opt/course/22/security-issues
   65  cat /opt/course/22/security-issues
   66  cat /opt/course/21/good-images 
   67  exit 
   68  lsof -t :6666
   69  lsof -ti :6666
   70  lsof -ti 6666
   71  sudo lsof -it :6666
   72  sudo lsof -ti :6666
   73  ps aux | grep 6666
   74  kubectl get nodes
   75  ssh cks8930-node1 
   76  exit
   77  ls /opt/course/18/sbom_check.json
   78  trivy sbom /opt/course/18/sbom_check.json
   79  trivy sbom /opt/course/18/sbom_check.json --format json
   80  trivy sbom /opt/course/18/sbom_check.json --format json --output /opt/course/18/sbom_check_result.json
   81  vi /opt/course/18/sbom_check_result.json


```
