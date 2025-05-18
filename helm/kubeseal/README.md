# Notes

It needs the --controller-namespace and --controller-name (service name) to be specified

```shell
kubeseal --controller-namespace kubeseal --controller-name kubeseal-helm-sealed-secrets -f mysecret.json -w my-secret.sealed.yaml
```

Alternatively, you can create aliases :

```
alias kubeseal-prod="kubeseal --controller-namespace prod --controller-name kubeseal-helm-sealed-secrets-prod"
alias kubeseal-dev="kubeseal --controller-namespace dev --controller-name kubeseal-helm-sealed-secrets-dev"
```

# Concerns

Does key renewal when secrets are stored in gitops need manual recreation of the sealed secrets in the git repository ? Does it requires rewrite of the git history (sealed secrets are stored there after all)
