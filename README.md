# Contains the policies for demo and the polices are applied to kyverno-test namespace

This repository contains a set of Kyverno policies for POV and Demo.

For more information, visit our website at [https://nirmata.com/](https://nirmata.com/).

Sign-up for a free trial today at [https://try.nirmata.io/](https://try.nirmata.io/)


## Installing Policies

**Clone Repository:**

Clone the kyverno-policies repository.

```console
git clone https://github.com/anuddeeph1/POV-policies.git
```

# Pod Security Standards
To install Pod Security Standard policies, 

These are collections of policies which implement the various levels of Kubernetes [Pod Security Standards](https://kubernetes.io/docs/concepts/security/pod-security-standards/).

The `Baseline/Default` profile is minimally restrictive and denies the most common vulnerabilities while the `Restricted` profile is more heavily restrictive but follows many more of the common security best practices for Pods.

NOTE: the `proc-mount` pod may execute as non-default values for `securityContext.procMount` require the `ProcMountType` feature flag to be enabled.

## Installing the Pod Security Standard policies


```console
cd POV/Pod-Secutity-Standards/Audit
kubectl apply -f baseline
kubectl apply -f restricted
```


Install baseline policies

```sh
kubectl apply -f baseline/
```

Install restricted profile in enforce mode
```sh
kubectl apply -f Enforce/restricted
```
Once policies are installed, you can check if they are ready using the command:

```console
kubectl get cpol
```
