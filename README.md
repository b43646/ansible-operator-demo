# ansible-operator-demo

1. 获取资源

```
git clone https://github.com/b43646/ansible-operator-demo.git

cd ansible-operator-demo/demo-operator
```

2. 创建CRD

```
oc create -f deploy/crds/demo.example.com_demos_crd.yaml
```

3. 配置项目

```
oc new-project tutorial
oc adm policy add-scc-to-group anyuid system:serviceaccounts:tutorial
oc create -f deploy/service_account.yaml
oc create -f deploy/role.yaml
oc create -f deploy/role_binding.yaml
```

4. 部署Operator

```
oc create -f deploy/operator.yaml
```

5. 创建demo资源对象，以实现demo应用的部署

```
oc create -f deploy/crds/demo.example.com_v1alpha1_demo_cr.yaml
```

6. 查看部署就绪的demo应用地址

```
oc get route
```

