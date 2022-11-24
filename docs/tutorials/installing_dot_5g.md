# Installing Dot 5G

Install the necessary 5G components:

```bash
juju deploy tls-certificates-operator
juju deploy dot5g-amf --trust
juju deploy dot5g-smf --trust
juju deploy dot5g-upf --trust
juju deploy dot5g-ui --trust
```

Add the following relations:

```bash
juju relate dot5g-amf tls-certificates-operator
juju relate dot5g-smf tls-certificates-operator
juju relate dot5g-upf tls-certificates-operator
juju relate dot5g-smf dot5g-upf
```

Validate the deployment is successfull:

```bash
juju status
```

All services should be in `Active-Idle` state.

!!! success
    The 5G network is now deployed. You can access the UI at `https://<ip-address>:3000`.
