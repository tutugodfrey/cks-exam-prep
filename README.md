# CKS Exam environment

```bash
git clone https://github.com/tutugodfrey/cks-exam-prep

cd cks-exam-prep/

rm -rf /var/lib/etcd

ETCDCTL_API=3 etcdctl snapshot restore --endpoints https://127.0.0.1:2379 --data-dir /var/lib/etcd --cert /etc/kubernetes/pki/apiserver-etcd-client.crt --key /etc/kubernetes/pki/apiserver-etcd-client.key --cacert /etc/kubernetes/pki/etcd/ca.crt  etcd-backups/cks3477-snapshot.db

```
