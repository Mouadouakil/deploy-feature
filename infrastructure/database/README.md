## Database customization

1. Change `my-namespace` in kustomization.yaml with your project namespace name
   <br/>
   <br/>
2. Change your database password but don't commit it to git, you can use `kubeseal` as described below
   <br/>
   <br/>

# Sealing secrets

```
cat secrets.yaml | kubeseal --controller-namespace sealed-secrets --controller-name sealed-secrets --format yaml > ss-postgres.yaml
```