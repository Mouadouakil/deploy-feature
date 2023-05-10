## Generating SSH key for Flux

The secret here is named gitops-myapp-auth, but it should be changed to your project name.

```
ssh-keygen -t ecdsa -b 521

flux create secret git gitops-myapp-auth --url=ssh://git@github.com/octocampus/sample-gitops-project.git --private-key-file=flux -n mfa
```
