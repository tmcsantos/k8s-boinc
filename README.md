# Science United on k8s
Donate extra cpu cycles to charity with Kubernetes, Docker and boinc.

## Installation
edit `scienceunited/account.env` with your account information.

```bash
kubectl apply -k scienceunited
```

List lods.

```bash
kubectl get po -l app=boinc -A
```

Then join a project or use a manager.

```bash
kubectl -n united exec -it boinc-d85b899c4-dlnk9 bash
boinccmd --acct_mgr attach "$URL" "$NAME" "$PASS"
```
