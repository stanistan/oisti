# oisti

> reversing-istio

While this tool does not yet exist, the idea is to have something that can look
at the state of a running kubernetes cluster's _running_ istio resources (sidecars, gateways, etc)
and output all contributing API state (in cluster) that contributed to that proxy being
configured as such.

For example:

A sidecar proxy could be configured by:
- `istio-system`
- the `Sidecar`
- the existence of Services
- `ServiceEntries`
- etc

The way I was thinking about building this is starting out with a model for an empty cluster. 
See what happens when you have a default istio configuration. See what happens when you add kubernetes services.
See what happens when you change sidecar configurations add service entries, virtual services, etc.

By See what happens: Do some structural diffing of the istio proxy by dumping out the proxy-config.
