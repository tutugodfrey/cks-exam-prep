#  Commands

```bash
    1  kube-bench run | grep /var/lib/kubelet/config.yaml -A3 -B2
    2  chmod 600 /var/lib/kubelet/config.yaml
    3  kube-bench run | grep client-ca-file -A3 -B2
    4  ls /etc/kubernetes/manifests/
    5  kube-bench run --check 1.2.25
    6  exit
    7  history
    8  history > commands.txt
    1  kubectl get nodes
    2  kubectl config view
    3  kubectl config get-contexts
    4  kubectl config get-contexts | awk -F" " "{ print $2 }"
    5  kubectl config get-contexts | awk -F" " '{ print $2 }'
    6  kubectl config get-contexts | awk -F" " '{ if NR!=1 print $2 }'
    7  kubectl config get-contexts | awk -F" " '{ if (NR!=1) print $2 }'
    8  kubectl config get-contexts | awk -F" " '{ if (NR!=1) print $2 }' > /opt/course/1/contexts
    9  cat /opt/course/1/contexts
   10  kubectl config view
   11  kubectl config view --raw
   12  kubectl config view
   13  kubectl config view --raw -jsonpath '{ .users[?(@.name == "restricted@infra-prod")].user.client-certificate-data }'
   14  kubectl config view --raw -ojsonpath '{ .users[?(@.name == "restricted@infra-prod")].user.client-certificate-data }'
   15  kubectl config view --raw -ojsonpath "{ .users[?(.name == 'restricted@infra-prod')].user.client-certificate-data }"
   16  kubectl config view --raw -ojsonpath "{ .users[(.name == 'restricted@infra-prod')].user.client-certificate-data }"
   17  kubectl config view --raw -ojsonpath="{ .users[(.name == 'restricted@infra-prod')].user.client-certificate-data }"
   18  kubectl config view --raw -ojsonpath="{ .users[?(@.name == 'restricted@infra-prod')].user.client-certificate-data }"
   19  kubectl config view --raw -ojsonpath="{ .users[?(.name == 'restricted@infra-prod')].user.client-certificate-data }"
   20  kubectl config view --raw -ojsonpath="{ .users[?(.name == 'restricted@infra-prod')].user.client-certificate-data }" | base64 -d
   21  kubectl config view --raw -ojsonpath="{ .users[?(.name == 'restricted@infra-prod')].user.client-certificate-data }" | base64 -d > /opt/course/1/cert
   22  cat /opt/course/1/cert
   23  exit
   24  kube-bench run --target master | grep kube-controller-manager -A3 -B2
   25  kube-bench run  | grep kube-controller-manager -A3 -B2
   26  sudo -i
   27  exit
   28  cp ~/.kube/config restricted-config
   29  export KUBECONFIG=restricted-config 
   30  kubectl -n restricted get namespaces
   31  kubectl -n restricted get secrets -n restricted
   32  k config use-context restricted@infra-prod
   33  kubectl -n restricted get secrets -n restricted
   34  kubectl -n restricted get namespaces
   35  kubectl get pods
   36  kubectl get pods -n restricted
   37  kubectl config set-context --current --namespace restricted
   38  kubectl get pods 
   39  kubectl edit pod pod1-5f5cfd795c-q4f4f 
   40  kubectl exec pod1-5f5cfd795c-q4f4f -- cat /etc/secret-volume 
   41  kubectl exec pod1-5f5cfd795c-q4f4f -- cat /etc/secret-volumes 
   42  kubectl exec pod1-5f5cfd795c-q4f4f -- sh
   43  kubectl edit pod pod1-5f5cfd795c-q4f4f 
   44  kubectl exec pod1-5f5cfd795c-q4f4f -- ls /etc/secret-volume 
   45  kubectl exec pod1-5f5cfd795c-q4f4f -- ls /etc/secret-volume/password
   46  kubectl exec pod1-5f5cfd795c-q4f4f -- cat /etc/secret-volume/password
   47  kubectl exec pod1-5f5cfd795c-q4f4f -- cat /etc/secret-volume/password > /opt/course/12/secret1
   48  kubectl edit pod pod2-7dbfcbc8d4-q8lt9 
   49  kubectl exec pod2-7dbfcbc8d4-q8lt9 -- echo $PAASWORD
   50  kubectl exec pod2-7dbfcbc8d4-q8lt9 -- echo $PASSWORD
   51  kubectl exec pod2-7dbfcbc8d4-q8lt9 -- env | grep PASSWORD
   52  kubectl exec pod2-7dbfcbc8d4-q8lt9 -- env | grep PASSWORD > /opt/course/12/secret2
   53  vi /opt/course/12/secret2
   54  kubectl edit pod pod3-66d87cf45d-p4mx6 
   55  kubectl exec -it pod3-66d87cf45d-p4mx6  -- sh
   56  unset KUBECONFIG
   57  kubectl get pods
   58  kubectl get pods -n restricted
   59  vi 13-np.yaml
   60  kubectl apply -f 13-np.yaml 
   61  vi 13-np.yaml
   62  kubectl apply -f 13-np.yaml 
   63  exit
   64  kubectl get svc
   65  echo cEVuRXRSYVRpT24tdEVzVGVSCg== | base64 -d
   66  echo cEVuRXRSYVRpT24tdEVzVGVSCg== | base64 -d > /opt/course/12/secret3
   67  cat /opt/course/12/secret3
   68  exit
   69  vi /etc/kubernetes/audit/policy.yaml 
   70  sudo vi /etc/kubernetes/audit/policy.yaml 
   71  vi /etc/kubernetes/manifests/kube-apiserver.yaml 
   72  sudo vi /etc/kubernetes/manifests/kube-apiserver.yaml 
   73  sudo watch crictl ps
   74  sudo  crictl ps -a
   75  sudo crictl logs 8088164f5cd4d
   76  sudo vi /etc/kubernetes/audit/policy.yaml 
   77  sudo watch crictl ps
   78  sudo  crictl ps -a
   79  sudo watch crictl ps
   80  sudo  crictl ps -a
   81  sudo mv /etc/kubernetes/manifests/kube-apiserver.yaml .
   82  sudo cp kube-apiserver.yaml /etc/kubernetes/manifests/
   83  sudo watch crictl ps
   84  sudo  crictl ps -a
   85  crictl rm de9ceca8bec95
   86  sudo crictl rm de9ceca8bec95
   87  sudo  crictl ps -a
   88  sudo watch crictl ps
   89  sudo  crictl ps -a
   90  sudo crictl logs b6a5551b5349e
   91  sudo vi /etc/kubernetes/audit/policy.yaml 
   92  sudo  crictl ps -a
   93  sudo crictl rm e92a34a391285
   94  sudo watch crictl ps
   95  sudo  crictl ps -a
   96  sudo crictl logs e076acaca6a92
   97  sudo vi /etc/kubernetes/audit/policy.yaml 
   98  sudo  crictl ps -a
   99  sudo crictl rm e076acaca6a92
  100  sudo  crictl ps -a
  101  sudo ls /etc/kubernetes/audit/logs/audit.log 
  102  sudo cat /etc/kubernetes/audit/logs/audit.log | yq -p json -o json
  103  exit
  104  truncate 0 /etc/kubernetes/audit/logs/audit.log 
  105  truncate 0 > /etc/kubernetes/audit/logs/audit.log 
  106  sudo truncate 0 > /etc/kubernetes/audit/logs/audit.log 
  107  echo > /etc/kubernetes/audit/logs/audit.log 
  108  sudo echo > /etc/kubernetes/audit/logs/audit.log 
  109  sudo vi /etc/kubernetes/audit/logs/audit.log 
  110  sudo rm /etc/kubernetes/audit/logs/audit.log
  111  exit
  112  kubectl auth can-i get secret 
  113  kubectl auth can-i get secret  --as gianna
  114  kubectl auth can-i get secret  --as gianna -n kube-system
  115  kubectl create clusterrole gianna --verb create --resource pods,deployments
  116  kubectl create clusterrole manager --verb create --resource pods,deployments
  117  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna --namespace security
  118  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna --namespace restricted
  119  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna --namespace internal
  120  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna --namespace internal2
  121  kubectl auth can-i create pod  --as gianna -n security
  122  kubectl auth can-i create deployment  --as gianna -n security
  123  kubectl auth can-i create deployment  --as gianna -n kube-system
  124  kubectl config view
  125  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna@infra-prod --namespace internal
  126  kubectl delete rolebinding manager-gianna  -n security
  127  kubectl delete rolebinding manager-gianna  -n internal
  128  kubectl delete rolebinding manager-gianna  -n restricted
  129  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna@infra-prod --namespace internal
  130  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna@infra-prod --namespace security
  131  kubectl create rolebinding manager-gianna --clusterrole manager --user gianna@infra-prod --namespace restricted
  132  vi /opt/course/p2/audit.log 
  133  cat /opt/course/p2/audit.log | yp -p json json 
  134  cat /opt/course/p2/audit.log | yq -p json json 
  135  cat /opt/course/p2/audit.log | yq -o json json 
  136  cat /opt/course/p2/audit.log | yq -o json -p json 
  137  cat /opt/course/p2/audit.log | yq -o json -p json | grep p.auster
  138  kubectl -n security get sa
  139  kubectl get sa
  140  kubectl get namespaces
  141  kubectl get sa kube-system
  142  kubectl get sa -n kube-system
  143  kubectl get secret -n security 
  144  cat /opt/course/p2/audit.log | yq -o json -p json | grep p.auster -A2 -B3
  145  kubectl get secret -n security
  146  kubectl -n security get secret mysql-admin -o yaml
  147  echo -n newmysqlpassword | base64 
  148  kubectl edit secret -n security mysql-admin 
  149  exit
  150  kubectl -n security get secrets
  151  cat /opt/course/p2/audit.log | grep p.auster | wc
  152  cat /opt/course/p2/audit.log | grep p.auster | grep Secret | wc
  153  cat /opt/course/p2/audit.log | grep p.auster | grep Secret 
  154  cat /opt/course/p2/audit.log | grep p.auster | grep Secret | jq
  155  cat /opt/course/p2/audit.log | grep p.auster | grep Secret| grep get | jq
  156  jq
  157  yq
  158  cat /opt/course/p2/audit.log | grep p.auster | grep Secret| grep get | yq
  159  cat /opt/course/p2/audit.log | grep p.auster | grep Secret| grep get | yq -o json -p json
  160  ls
  161  exit
  162  ls
  163  ssh cks3477-node1 
  164  ls /opt/course/
  165  mkdir /opt/course/13
  166  cp 13-np.yaml /opt/course/13
  167  vi kube-apiserver.yaml 
  168  sudo vi kube-apiserver.yaml 
  169  sudo cp kube-apiserver.yaml /opt/course/17/
  170  exit
  171  ssh cks3477-node1 
  172  scp cks3477-node1:/home/candidate/commands.txt .
  173  history
  174  history >> commands.txt 

```
