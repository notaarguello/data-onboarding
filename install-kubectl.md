# Instalar kubectl y herramientas de Kubernetes

kubectl es el cliente de línea de comandos para interactuar con clusters de Kubernetes. Esta guía también incluye herramientas complementarias: k9s, kustomize y minikube.

## kubectl

Cliente oficial para gestionar clusters de Kubernetes.

**Sitio oficial:** https://kubernetes.io/docs/tasks/tools/

### Linux

```bash
# Descargar kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

# Verificar
kubectl version --client
```

### Mac

```bash
brew install kubectl
kubectl version --client
```

### Cheatsheet kubectl

```bash
kubectl get pods              # Listar pods
kubectl get services          # Listar servicios
kubectl logs POD              # Ver logs de un pod
kubectl exec -it POD -- bash  # Shell en un pod
kubectl apply -f file.yaml    # Aplicar configuración
kubectl delete pod POD        # Eliminar pod
```

---

## k9s

Interfaz de terminal para Kubernetes. Permite navegar y gestionar recursos de forma interactiva.

**Sitio oficial:** https://k9scli.io

### Linux

```bash
# Descargar última versión
curl -sS https://webinstall.dev/k9s | bash

# O con snap
sudo snap install k9s
```

### Mac

```bash
brew install derailed/k9s/k9s
```

### Cheatsheet k9s

```bash
k9s                           # Abrir UI de k9s
k9s -n NAMESPACE              # Abrir en namespace específico
# Dentro de k9s:
# :pods, :svc, :deploy        # Navegar recursos
# /texto                      # Filtrar
# l                           # Ver logs
# s                           # Shell en pod
```

---

## kustomize

Herramienta para personalizar configuraciones de Kubernetes sin templates.

**Sitio oficial:** https://kustomize.io

### Linux

```bash
curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh" | bash
sudo mv kustomize /usr/local/bin/
```

### Mac

```bash
brew install kustomize
```

### Cheatsheet kustomize

```bash
kustomize build .             # Generar YAML desde directorio actual
kustomize build . | kubectl apply -f -  # Aplicar directamente
kubectl apply -k .            # Shortcut (kubectl nativo)
```

---

## minikube

Cluster local de Kubernetes para desarrollo y pruebas.

**Sitio oficial:** https://minikube.sigs.k8s.io

### Linux

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Verificar
minikube version
```

### Mac

```bash
brew install minikube
minikube version
```

### Cheatsheet minikube

```bash
minikube start            # Iniciar cluster local
minikube stop             # Detener cluster
minikube delete           # Eliminar cluster
minikube dashboard        # Abrir dashboard web
minikube status           # Ver estado del cluster
```
