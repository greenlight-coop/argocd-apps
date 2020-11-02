# argocd-apps

## Initial install command

    argocd app create argocd-apps \
        --repo https://github.com/greenlight-coop/argocd-apps.git \
        --path apps \
        --dest-server https://kubernetes.default.svc \
        --dest-namespace argocd