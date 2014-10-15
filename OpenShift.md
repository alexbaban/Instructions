## OpenShift DevOps

### create a Ghost blog app on OpenShift
`rhc app create ghost nodejs-0.10 mysql-5.5 --env NODE_ENV=production --from-code https://github.com/openshift-quickstart/openshift-ghost-mysql-quickstart.git`
>`'ghost'` is the app name `'nodejs-0.10'` and `'mysql-5.5'` are cartridges

---

### port forward
`rhc port-forward -a nodejs`
> `'nodejs'` is the app name
