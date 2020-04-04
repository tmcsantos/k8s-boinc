# Science United on k8s
Donate extra cpu cycles to charity with Kubernetes, Docker and boinc.

## Installation
edit `scienceunited/account.env` with your account information.

```bash
kubectl apply -k scienceunited
```

List Pods.

```bash
kubectl get po -l app=boinc -A
```

Then join a project or use a manager.

```bash
kubectl -n united exec -it boinc-d85b899c4-dlnk9 bash
boinccmd --acct_mgr attach "$URL" "$NAME" "$PASS"
```

## Utility controller
There is simple script `controller` to issue commands directly in the running pods. It depends on [jq](https://stedolan.github.io/jq/).


```bash
# force account resync
./controller boinccmd --acct_mgr sync

# get currently assigned tasks
./controller boinccmd --get_tasks
```
