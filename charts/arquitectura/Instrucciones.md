# Instrucciones para levantar la arquitectura

## 1. Despliegue completo con Helm

Ubicado en la carpeta raíz del proyecto (`2025-02-2021579438-IC7602`):

```sh
helm install arquitectura ./charts/arquitectura
```

## 2. Verificar namespaces

```sh
kubectl get ns
```

## 3. Manejo de componentes y versiones

Colocar los componentes adicionales en la carpeta `_templates_`. Tener cuidado con el manejo de versiones.

---

## Comandos Helm

- **Instalar todo:**
  ```sh
  helm install arquitectura ./charts/arquitectura
  ```
- **Actualizar/reiniciar:**
  ```sh
  helm upgrade arquitectura ./charts/arquitectura
  ```
- **Desinstalar todo:**
  ```sh
  helm uninstall arquitectura
  ```

---

## Comandos Kubernetes

- **Montar un pod (ubicado en la carpeta del YAML):**
  ```sh
  kubectl apply -f nombre_archivo.yaml
  ```
- **Borrar un pod:**
  ```sh
  kubectl delete pod nombre_pod
  ```
- **Acceder a bash de un pod (ejemplo para router):**
  ```sh
  kubectl exec -it router-deployment-6c56d4c6db-vpzmn -- bash
  ```
- **Acceder a pod en un namespace específico:**
  ```sh
  kubectl exec -it test-client -n publico -- sh
  ```

---

## Contenedores Docker

- **Construir imagen:**
  ```sh
  docker build -t centos-nftables:1.1 .
  ```
- **Etiquetar imagen:**
  ```sh
  docker tag centos-nftables:1.0 gerardo67/centos-nftables:1.0
  ```
- **Login en Docker Hub:**
  ```sh
  docker login
  ```
- **Subir imagen:**
  ```sh
  docker push gerardo67/centos-nftables:1.0
  ```
