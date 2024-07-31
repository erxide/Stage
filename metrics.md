# Metrics Importantes pour un Dashboard Grafana de Prometheus pour une Infrastructure Kubernetes (K8S)

Pour surveiller une infrastructure Kubernetes (k8s) à l'aide de Prometheus et de Grafana, il est crucial de sélectionner des métriques pertinentes qui offrent une vue d'ensemble de la santé et des performances du cluster. Voici une liste des métriques les plus importantes à considérer :

## Métriques de Cluster

1. **État des nœuds (Nodes)**
   - `kube_node_status_condition`: pour surveiller l'état des nœuds (Ready, NotReady, etc.)
   - `kube_node_status_capacity`: capacité des nœuds en termes de CPU et de mémoire.

2. **Ressources des nœuds**
   - `node_cpu_usage_seconds_total`: utilisation de CPU par nœud.
   - `node_memory_MemAvailable_bytes`: mémoire disponible par nœud.
   - `node_disk_io_time_seconds_total`: utilisation des disques par nœud.

## Métriques de Namespace

1. **Ressources des namespaces**
   - `kube_namespace_status_phase`: état des namespaces.
   - `kube_resourcequota`: quotas de ressources par namespace.
   - `kube_limitrange`: limites de ressources par namespace.

## Métriques d'Application

1. **Performance des applications**
   - `http_requests_total`: nombre total de requêtes HTTP reçues.
   - `http_request_duration_seconds`: durée des requêtes HTTP.
   - `http_request_size_bytes`: taille des requêtes HTTP.

## Métriques de Réseau

1. **Ressources réseau**
   - `node_network_receive_bytes_total`: octets reçus par les interfaces réseau des nœuds.
   - `node_network_transmit_bytes_total`: octets transmis par les interfaces réseau des nœuds.
   - `node_network_receive_errs_total`: erreurs de réception réseau par nœud.
   - `node_network_transmit_errs_total`: erreurs de transmission réseau par nœud.

## Métriques de Stockage

1. **Utilisation du stockage**
   - `kube_persistentvolume_status_phase`: état des volumes persistants (Available, Bound, Released, Failed).
   - `kube_persistentvolumeclaim_status_phase`: état des revendications de volumes persistants.
   - `node_filesystem_avail_bytes`: espace disponible sur les systèmes de fichiers des nœuds.
   - `node_filesystem_usage_bytes`: espace utilisé sur les systèmes de fichiers des nœuds.

Ces métriques vous aideront à obtenir une vue d'ensemble de la santé et des performances de votre cluster Kubernetes, ainsi qu'à identifier et résoudre rapidement les problèmes potentiels.
