# Commands

```bash
   1  falco -U | grep httpd
    2  crictl ps --id 838b66166c99
    3  crictl pods --id 89a03560694f0
    4  kubectl get pods -n team-purple
    5  kubectl -n team-purple scale deployment rating-service --replicas=0
    6  kubectl get pods -n team-purple
    7  falco -U | grep "Package management process"
    8  vi /etc/falco/rules.d/falco_custom.yaml
    9  falco -U | grep "Package management process"
   10  falco -U | grep "Package management process" > /opt/course/2/falco.log
   11  vi /opt/course/2/falco.log
   12  falco -U | grep "Package management process"
   13  falco -U | grep "Package management process" >> /opt/course/2/falco.log
   14  cat /opt/course/2/falco.log
   15  vi /opt/course/2/falco.log
   16  falco -U | grep "Package management process" >> falco.log
   17  vi falco.log 
   18  cat falco.log 
   19  falco -U | grep "Package management process"
   20  crictl ps --id 44c286e466d9
   21  kubectl -n team-blue get pods
   22  kubectl -n team-blue scale deployment webapi --replicas=0
   23  exit
   24  crictl ps
   25  crictl ps | grep team-yellow
   26  crictl ps --id a92e532919efc
   27  crictl inspect a92e532919efc | grep args -A3
   28  ps aux | grep collector3-process
   29  strace -p 14311
   30  ps aux | grep collector2-process
   31  strace -p 115836
   32  strace -p 14091
   33  ps aux | grep collector1-process
   34  strace -p 14047
   35  strace -p 14023
   36  kubectl -n team-yellow get deployment
   37  kubectl -n team-yellow scale deployment collector1 --replicas=0
   38  kubectl -n team-pink get pods
   39  kubectl -n team-pink get svc
   40  kubectl -n team-pink get ingress
   41  exit
   42  falco -U | grep 'Package management process launched'
   43  kubectl -n team-blue scale deployment webapi --replicas=1
   44  kubectl -n team-blue get pod
   45  falco -U | grep 'Package management process launched'
   46  vi /etc/falco/rules.d/falco_custom.yaml 
   47  falco -U | grep 'Package management process launched'
   48  kubectl -n team-blue scale deployment webapi --replicas=0
   49  ls

1  kubectl get nodes
    2  scp cks7262-node1:/etc/falco/rules.d/falco_custom.yaml .
    3  ls
    4  ssh cks7262-node1
    5  vi /opt/course/2/falco.log
    6  exit
    7  kubectl get svc
    8  sudo -i
    9  exit
   10  scp /opt/course/9/profile cks7262-node1
   11  scp /opt/course/9/profile cks7262-node1:/
   12  sudo scp /opt/course/9/profile cks7262-node1:/
   13  sudo sshcks7262-node1:/profile
   14  sudo sshcks7262-node1: apparmor_parser /profile
   15  sudo ssh cks7262-node1:
   16  sudo ssh cks7262-node1 apparmor_parser /profile
   17  vi /opt/course/9/profile 
   18  kubectl label node cks7262-node1 security=apparmor
   19  kubectl -n default create deployment apparmor --image=nginx:1.27.1 --dry-run=client -o yaml > 9-pod.yaml
   20  vi 9-pod.yaml 
   21  kubectl apply -f 9-pod.yaml 
   22  kubectl get pod -w
   23  kubectl logs -f apparmor-7884f478d9-h78m2 > /opt/course/9/logs
   24  vi /opt/course/9/logs
   25  kubectl get nodes
   26  vi runtime-class.yaml
   27  kubectl apply -f runtime-class.yaml 
   28  kubectl get runtimeclass
   29  cat runtime-class.yaml 
   30  kubectl get nodes
   31  kubectl label node cks7262-node2 userruntime=gvisor
   32  kubectl -n team-purple run gvisor-test --image=nginx:1.27.1 --dry-run=client -o yaml > gvisor-test.yaml
   33  vi gvisor-test.yaml 
   34  kubectl apply -f gvisor-test.yaml 
   35  kubectl -n team-purple get pod -w
   36  kubectl -n team-purple logs -f gvisor-test 
   37  kubectl -n team-purple exec gvisor-test -- dmesg
   38  kubectl -n team-purple exec gvisor-test -- dmesg > /opt/course/10/gvisor-test-dmesg
   39  vi /opt/course/10/gvisor-test-dmesg
   40  kubectl -n team-purple get pod -o wide
   41  ETCDCTL_API=3 etcdctl --cert /etc/kubernetes/pki/apiserver-etcd-client.crt --key /etc/kubernetes/pki/apiserver-etcd-client.key --cacert /etc/kubernetes/pki/etcd/ca.crt get /registry/secrets/team-green/database-access
   42  sudo -i
   43  exit
   44  kubectl -n team-yellow get pod -o wide
   45  ssh cks7262-node1 
   46  kubectl -n team-pink create secret tls --cert /opt/course/15/tls.crt --key /opt/course/15/tls.key 
   47  kubectl -n team-pink create secret tls secure --cert /opt/course/15/tls.crt --key /opt/course/15/tls.key 
   48  kubectl -n team-pink edit ingress secure 
   49  curl -kv https://secure-ingress.test:31443/app
   50  curl -kv https://secure-ingress.test:31443/api
   51  kubectl -n team-blue get deployment
   52  kubectl -n team-blue get deployment pod
   53  kubectl -n team-blue get pods
   54  vi /opt/course/16/image/Dockerfile 
   55  docker build -t registry.killer.sh:5000/image-verify:v1 -f  /opt/course/16/image/Dockerfile .
   56  podman build -t registry.killer.sh:5000/image-verify:v2 -f  /opt/course/16/image/Dockerfile .
   57  podman push registry.killer.sh:5000/image-verify:v2
   58  podman images
   59  cd /opt/course/16/image/
   60  ls
   61  podman build -t registry.killer.sh:5000/image-verify:v2 -F  /opt/course/16/image/Dockerfile .
   62  podman build -t registry.killer.sh:5000/image-verify:v2 
   63  podman build -t registry.killer.sh:5000/image-verify:v2 .
   64  podman push registry.killer.sh:5000/image-verify:v2
   65  kubectl -n team-blue get pod -w
   66  exit
   67  cp /opt/course/16/image/Dockerfile .
   68  ls
   69  kubectl -n team-blue edit deployment image-verify 
   70  exit
   71  cp /opt/course/19/immutable-deployment.yaml /opt/course/19/immutable-deployment-new.yaml 
   72  vi /opt/course/19/immutable-deployment-new.yaml
   73  kubectl get pods
   74  vi /opt/course/19/immutable-deployment-new.yaml
   75  kubectl -n team-purple get pods
   76  kubectl apply -f /opt/course/19/immutable-deployment-new.yaml 
   77  exit
   78  cat > /opt/course/2/falco.log 
   79  exit
   80  kubectl -n team-orange get pods
   81  kubectl -n team-orange get svc
   82  kubectl -n team-orange get pods --show-labels
   83  vi 8-p1.yaml
   84  kubectl apply -f 8-p1.yaml 
   85  vi 8-p1.yaml
   86  kubectl apply -f 8-p1.yaml 
   87  vi 8-p2.yaml
   88  kubectl apply -f 8-p2.yaml 
   89  vi 8-p2.yaml
   90  kubectl apply -f 8-p2.yaml 
   91  vi 8-p3.yaml
   92  kubectl explain ciliumnetworkpolicy.spec.egressdeny
   93  kubectl explain ciliumnetworkpolicy.spec.egressDeny
   94  kubectl explain ciliumnetworkpolicy.spec
   95  kubectl explain ciliumnetworkpolicy.spec.egress
   96  kubectl explain ciliumnetworkpolicy.spec.egress.authentication
   97  vi 8-p3.yaml 
   98  kubectl apply -f 8-p3.yaml 
   99  vi 8-p3.yaml 
  100  kubectl apply -f 8-p3.yaml

``` 
