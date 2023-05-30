Helm charts for TLS dev

These charts install cert-manager operator, OSP operators, then deploy OSP by fetching the relevant alm-examples and applying overrides where necessary


Install OCP prerequisites (just cert-manager now, previously had service-mesh etc...):
```
help install openshift ./openshift
```

Install OSP operators:
```
helm install openstack-k8s ./openstack-k8s
```

Install OSP:
```
helm install openstack ./openstack
```

Delete OSP:
```
helm delete openstack
```

Delete OSP operators:
```
helm delete openstack-k8s
```

Install individual charts:
```
helm install cert-manager-operator ./openshift/charts/cert-manager-operator
helm install mariadb-operator ./openstack-k8s/charts/mariadb-operator --set 'global.namespace="openstack"'
etc...
```


