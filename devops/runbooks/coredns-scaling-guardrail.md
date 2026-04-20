# CoreDNS scaling guardrail in local kube-system

In the `local` Kubernetes cluster, the `coredns` deployment in the `kube-system` namespace cannot be scaled below **2 replicas**.

## Observed behavior

Attempting to scale `coredns` to `1` replica is blocked by a safety check:

```text
Cannot scale HA-critical deployment 'coredns' below 2 replica
```

## Implication

`coredns` is treated as an HA-critical deployment in this environment, and scaling it below 2 replicas is prevented.

## Scope

- Cluster: `local`
- Namespace: `kube-system`
- Deployment: `coredns`

## Notes

- Scaling `coredns` to 3 replicas in the same environment is permitted and has succeeded previously.
- This guardrail should be considered when planning maintenance or troubleshooting DNS-related issues in the local cluster.