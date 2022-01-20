## to list kubernetes contexts 

[harishadmarunadm@wzv-az-rsp-client1 ~]$ kubectl config get-contexts
CURRENT   NAME                           CLUSTER                        AUTHINFO                                                                 NAMESPACE
          Prod-SmK8sCluster              Prod-SmK8sCluster              clusterUser_Prod-SmResourceGroupTerraform_Prod-SmK8sCluster
*         Prod-WorkzProdFRSmK8sCluster   Prod-WorkzProdFRSmK8sCluster   clusterUser_Prod-SmResourceGroupTerraform_Prod-WorkzProdFRSmK8sCluster
          Prod-WorkzProdUsSmK8sCluster   Prod-WorkzProdUsSmK8sCluster   clusterUser_Prod-SmResourceGroupTerraform_Prod-WorkzProdUsSmK8sCluster
          Prod-WorkzUSSmK8sCluster       Prod-WorkzUSSmK8sCluster       clusterUser_Prod-SmResourceGroupTerraform_Prod-WorkzUSSmK8sCluster       sm-m2m
[harishadmarunadm@wzv-az-rsp-client1 ~]$

[harishadmarunadm@wzv-az-rsp-client1 ~]$ kubectl config use-context Prod-WorkzUSSmK8sCluster
Switched to context "Prod-WorkzUSSmK8sCluster".
[harishadmarunadm@wzv-az-rsp-client1 ~]$
[harishadmarunadm@wzv-az-rsp-client1 ~]$ kubectl config get-contexts
CURRENT   NAME                           CLUSTER                        AUTHINFO                                                                 NAMESPACE
          Prod-SmK8sCluster              Prod-SmK8sCluster              clusterUser_Prod-SmResourceGroupTerraform_Prod-SmK8sCluster
          Prod-WorkzProdFRSmK8sCluster   Prod-WorkzProdFRSmK8sCluster   clusterUser_Prod-SmResourceGroupTerraform_Prod-WorkzProdFRSmK8sCluster
          Prod-WorkzProdUsSmK8sCluster   Prod-WorkzProdUsSmK8sCluster   clusterUser_Prod-SmResourceGroupTerraform_Prod-WorkzProdUsSmK8sCluster
*         Prod-WorkzUSSmK8sCluster       Prod-WorkzUSSmK8sCluster       clusterUser_Prod-SmResourceGroupTerraform_Prod-WorkzUSSmK8sCluster       sm-m2m
[harishadmarunadm@wzv-az-rsp-client1 ~]$

[harishadmarunadm@wzv-az-rsp-client1 ~]$ kubectl get pods -n sm-consumer

[harishadmarunadm@wzv-az-rsp-client1 ~]$ kubectl describe pods dpplus-deployment-1.7.7-7866f86c5-klzr4 -n sm-consumer

[harishadmarunadm@wzv-az-rsp-client1 ~]$ kubectl exec --stdin --tty dpplus-deployment-1.7.7-7866f86c5-klzr4 -n sm-consumer -- bash
Defaulted container "dpplus" out of: dpplus, dpplus-start-check (init)

root@dpplus-deployment-1:/# exit

[harishadmarunadm@wzv-az-rsp-client1 ~]$ kubectl exec --stdin --tty dpplus-deployment-1.7.7-7866f86c5-klzr4 -c dpplus -n sm-consumer -- bash
root@dpplus-deployment-1:/#


