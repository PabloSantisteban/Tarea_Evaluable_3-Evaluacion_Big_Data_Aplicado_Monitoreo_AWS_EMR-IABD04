# Monitoreo de Clúster AWS EMR con Prometheus y Grafana

Este repositorio contiene los archivos de configuración y documentación correspondientes a una práctica de monitoreo en un clúster **AWS EMR**, utilizando herramientas como **JMX Exporter**, **Prometheus** y **Grafana**.

## Objetivo de la tarea

El objetivo principal de esta práctica es desplegar un sistema de monitoreo que permita observar el estado y rendimiento de un clúster **EMR**. Para ello, se exponen métricas clave desde el NameNode mediante **JMX Exporter**, se recolectan desde una instancia EC2 con **Prometheus** y se visualizan mediante un dashboard en **Grafana**.


## Estructura del repositorio

- `config_files/`
  - `config.yml` – Configuración de JMX Exporter
  - `hadoop-env.sh` – Modificado para lanzar el agente JMX
  - `jmx_prometheus_javaagent-0.16.1.jar` – Agente JMX para exponer las métricas del NameNode
  - `prometheus.yml` – Configuración de Prometheus en EC2

- `Tarea_Evaluable_3ªEvaluación_Big_Data_Aplicado_Monitoreo_AWS_EMR - IABD04.pdf` – Informe paso a paso con el desarrollo completo de la práctica
- `LICENSE` - Archivo de licencia que indica los términos bajo los cuales se distribuyen los archivos de este repositorio


## Herramientas utilizadas

- **AWS EMR** – Clúster con Hadoop, Spark y Hive
- **Instancia EC2** – Instancia de AWS para alojar Prometheus y Grafana
- **JMX Exporter** – Herramienta para exponer métricas del NameNode
- **Prometheus** – Sistema de recolección de métricas
- **Grafana** – Herramienta de visualización y monitoreo en tiempo real de métricas


## Despliegue y configuración

1. Se creó un clúster **EMR** con un nodo maestro y dos nodos core.
2. En el NameNode, se configuró **JMX Exporter** para exponer métricas en el puerto `12345`.
3. Se desplegó una instancia **EC2** (Ubuntu) donde se instalaron **Prometheus** y **Grafana**.
4. Se configuró `prometheus.yml` para apuntar al NameNode.
5. Se creó un **dashboard en Grafana** con visualizaciones personalizadas de las métricas clave del clúster.


## Métricas visualizadas

A través del panel de Grafana, se visualizaron las siguientes métricas clave:

- **Uso de CPU**: `process_cpu_seconds_total`
- **Uso de memoria RAM (heap)**: `jvm_memory_bytes_used{area="heap"}`
- **Espacio en HDFS**: `hadoop_namenode_capacityusedgb`
- **Estado del NameNode**: `hadoop_namenode_safemodecount{name="StartupProgress"}`


## Informe

Para una explicación completa del proceso, puedes consultar el informe en PDF incluido en este repositorio.


*Autor: Pablo Santisteban Fernández – IABD04*
