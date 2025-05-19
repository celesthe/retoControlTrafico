# Reto Control de Tráfico

Este repositorio contiene los manifiestos de Kubernetes necesarios para implementar un sistema de control de tráfico utilizando Istio y herramientas de observabilidad como Prometheus, Grafana, Jaeger y Kiali.

## Estructura del Repositorio

- `api-frontend.yaml`: Manifiesto para el despliegue y servicio del frontend de la aplicación.
- `api-products.yaml`: Manifiesto para el despliegue y servicio del backend de productos, con anotaciones para Prometheus.
- `auth.yaml`: Manifiesto relacionado con la autenticación.
- `canary.yaml`: Configuración para implementar despliegues canary.
- `mtls.yaml`: Configuración para habilitar mTLS en el mesh de Istio.
- `product-backend-v1.yaml`: Manifiesto para la versión 1 del backend de productos.
- `product-backend-v2.yaml`: Manifiesto para la versión 2 del backend de productos.
- `virtual-service-destination-rule.yaml`: Configuración de Istio para servicios virtuales y reglas de destino.

## Herramientas de Observabilidad

### Prometheus
Prometheus se utiliza para recolectar métricas de las aplicaciones. Las anotaciones necesarias para habilitar el scraping de métricas están configuradas en `api-products.yaml`.

### Grafana
Grafana se utiliza para visualizar las métricas recolectadas por Prometheus. Asegúrate de que Grafana esté configurado para usar Prometheus como fuente de datos.

### Jaeger
Jaeger se utiliza para el tracing distribuido. Asegúrate de que las aplicaciones estén instrumentadas para enviar trazas a Jaeger.

### Kiali
Kiali proporciona una vista gráfica del mesh de servicios de Istio. Asegúrate de que Istio esté correctamente configurado.

## Cómo Acceder a las Herramientas

### Prometheus
1. Ejecuta el siguiente comando para acceder a Prometheus:
   ```bash
   kubectl port-forward svc/prometheus-service-name 9090:9090
   ```
2. Abre tu navegador y ve a `http://localhost:9090`.

### Grafana
1. Ejecuta el siguiente comando para acceder a Grafana:
   ```bash
   kubectl port-forward svc/grafana-service-name 3000:3000
   ```
2. Abre tu navegador y ve a `http://localhost:3000`.

### Jaeger
1. Ejecuta el siguiente comando para acceder a Jaeger:
   ```bash
   kubectl port-forward svc/jaeger-service-name 16686:16686
   ```
2. Abre tu navegador y ve a `http://localhost:16686`.

### Kiali
1. Ejecuta el siguiente comando para acceder a Kiali:
   ```bash
   kubectl port-forward svc/kiali 20001:20001 -n istio-system
   ```
2. Abre tu navegador y ve a `http://localhost:20001`.

## Configuración Adicional

- **Istio**: Asegúrate de que Istio esté desplegado en tu clúster y que las aplicaciones estén dentro del mesh.
- **Instrumentación**: Instrumenta tus aplicaciones para enviar métricas y trazas a Prometheus y Jaeger, respectivamente.

## Contribuciones

Si deseas contribuir a este proyecto, por favor abre un issue o envía un pull request.

