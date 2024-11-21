# argocd

用於部屬 ArgoCD 本身的安裝及資源設定，Application目標就是自己本身，除了初始化，後續皆可透過Git變動變更資源

初始化避免沒有部屬資源設定，直接部屬預設所需的資源
```shell
# 切到Init目錄
cd /argocd/init

# 執行 kustomization
kubectl apply -k .
```

# cluster-infra-install

用於部屬不同 K8S 集群的基礎元件，像是 Operator/CRD 等等

後續由個別集群自行部屬後續應用，僅管理基礎建設

由於上一部已添加設定資源，可以直接部屬 `all-cluster-infra-install-sync-application.yaml` 即可

```shell
kubectl apply -f /cluster-infra-install/application/all-cluster-infra-install-sync-application.yaml
```

