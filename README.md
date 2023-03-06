This repository contains manifests to deploy MariaDB, PHPMyAdmin, and Wordpress into a namespace in Kubernetes.

## Usage

1. Create a namespace:

    ```
    kubectl create ns wordpress-example
    ```

1. Edit the credentials in `mariadb/mariadb-credentials.env` with your favorite editor.

1. Deploy the manifests:

    ```
    kubectl -n wordpress-example apply -k .
    ```

1. Wait for all the pods to become Ready.

---

This example intentionally does expose any services publicly. You can access wordpress (or phpmyadmin) using the `kubectl port-forward` command:

```
kubectl -n wordpress-example port-forward service/wordpress 8080:80
```

After running the above command, you can access Wordpress at <http://localhost:8080>.
