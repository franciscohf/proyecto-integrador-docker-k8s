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


## Parte 4: Gestión de Versiones

### Objetivo
Aprender a gestionar versiones de deployments usando comandos de rollout (rollback, rollforward, historial).

### ¿Qué hace kubectl rollout undo?

Con el comando podemos volver a una version anterior en caso de falla de la version actual
o  volver de la anterior a la actual.
#### 4.1 Ver Historial de Rollouts


  ### Screenshots
- ![kubectl rollout history backend](screenshots/parte4-kubectl-rollout-history-backend.png)
- ![kubectl rollout history frontend](screenshots/parte4-kubectl-rollout-history-frontend.png)
- ![rollback](screenshots/parte4-proceso-rollback.png)
- ![api info](screenshots/parte4-api-info-404.png)
- ![rollback reversion](screenshots/parte4-rollback-reversion.png)
- ![api info funcinal](screenshots/parte4-api-info-funcional.png)

## Parte 5: Ingress + MetalLB

   **IP del Ingress:** 10.241.2.240-10.241.2.250

   ### Screenshots
   ![Ingress config](screenshots/parte5-ingress.png)
   ![Acceso externo](screenshots/parte5-external-access.png)

   ## Conclusiones

   ### Aprendizajes principales
   - Manajeo de docker
   - Conocer un poco mas de la publicacion de imagenes
   - Ver el proceso y uso de comandos de kubernete
   - Conocer como se implemente el deploymet
   - Manejo de errores

   ### Dificultades encontradas
   - El ingress no tenia una ip externa 
   - No se actualizaba los cambios de la imagen, habia que crear una imagne con otro tag
   
   ### Reflexión
   El manejo de imagenes para la implementacion de microservicios