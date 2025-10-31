   # Proyecto Final - Docker & Kubernetes

   Alumno: Francisco Humberto Flores Huanca
   Fecha: 31/10/2025
   Curso: Docker & Kubernetes - i-Quattro

   ## Links de Docker Hub
   - Backend v2.1: https://hub.docker.com/repository/docker/francisco13/springboot-api/general
   - Frontend v2.2: https://hub.docker.com/repository/docker/francisco13/angular-frontend/general

   ## Parte 1: Setup del Ambiente

   **Ambiente utilizado:**
   - VirtualBox
   - Nombre de VM/Instancia: Francisco-Humberto-Flores-Huanca-k8s
   - Sistema operativo: Ubuntu 24.04 LTS
   - Recursos: 4GB RAM, 2 CPU cores
   - Red configurada: Bridged
   - Rango MetalLB: 10.241.2.240-10.241.2.250

   ### Screenshots
   ![microk8s status][def]

   ![Pods running][def2]

   ![Frontend][def3]

[def]: screenshots/parte1-microk8s-status.png
[def2]: screenshots/parte1-pods-running.png
[def3]: screenshots/parte1_frontend_browser.png

## Parte 2: Backend v2.1
Se adiciono el Endpoint en el controlador GreetingController
Se adiciono su import
Se aplicaron cambios a los deploments

### Código Agregado

import org.springframework.http.ResponseEntity;

@GetMapping("/api/infoA")
public ResponseEntity<Map<String, Object>> getInfo() {
    Map<String, Object> info = new HashMap<>();
    info.put("alumno", "Francisco Humberto Flores Huanca");
    info.put("version", "v2.1");
    info.put("curso", "Docker & Kubernetes - i-Quattro");
    info.put("timestamp", LocalDateTime.now().toString());
    info.put("hostname", System.getenv("HOSTNAME"));
    return ResponseEntity.ok(info);
}

### Screenshots
![Docker build](screenshots/parte2-docker-build.png)
![Rollout](screenshots/parte2-rollout.png)
![API Info](screenshots/parte2-api-info.png)
![docker images](screenshots/parte2-docker%20images.png)
![kubectl rollout status](screenshots/parte2-rollout.png)
![kubectl get pods](screenshots/parte2-kubectl-pods.png)
![kubectl get pods](screenshots/parte2-kubectl-pods.png)

## Parte 3: Frontend v2.2
 Se realizo cambios en el frontend
### Screenshots
![Frontend build](screenshots/parte3-frontend-build.png)
![html](screenshots/parte3-html.png)
![ts](screenshots/parte3-ts.png)
![kubectl get pods](screenshots/parte3-kubectl-get-pods.PNG)
![Info Sistema](screenshots/parte3-info-sistema.PNG)
![Sistema cargado](screenshots/parte3-sistema-cargado.PNG)
