---
title: Untitled Page
description: 
published: true
date: 2024-01-05T11:02:01.169Z
tags: 
editor: markdown
dateCreated: 2024-01-04T11:27:48.095Z
---

# Resize de un volumen en windows 2008 dwh


> Con el timepo ha sido necesario agregar mas espacio de almacenamiento al equipo windows dwh2008r2. Se probaron varias alternativas, y la que resultó mas apropiada fue la de incorporar volumenes nuevos desde cinder.
{.is-warning}


No es posible agregar discos en caliente por lo que se hace necesario apagar el equipo windows, borrar el stack de heat, agregar disco y luego crear o ampliar volumenes desde windows.

Entonces, los pasos serían:

- Crear en volumen en cinder del tamaño requerido

- Agregar el id del volumen en la plantilla de heat /etc/openstack-osep/heat_templates/dwh_2008r2.yml

- Apagar la vm dwh2008 desde windows

- Luego eliminar el stack:

**heat stack-delete dwh2008r2**

- Crear el stack de nuevo con heat stack-create

heat stack-create -f /etc/openstack-osep/heat_templates/dwh_2008r2.yml -P host_name=dwh2008r2 -P flavor=m1.large.3 -P root_disk=49670912-793a-4082-8cc8-8e85a0d45e9a dwh2008r2

 * verificar los datos anteriores en backup/rdiff-backup/openstack_stacks/dwh2008r2/ultimo/input_params

- Una vez encendida la vm, vamos a herrmientas administrativas del panel control de windows > administrar discos 

*Aqui ya deberíamos ver el disco nuevo y nos va a pedir que lo Inicialicemos*

- Una vez hecho esto, es posible crear un filesystem nuevo o usarlo para ampliar otro volumen existente (el volumen existente debe ser dinamico)

Para ampliar volumen:

>         click con el boton derecho en el volumen existente
>         selecionar Extender volumen...
>         seguimos los pasos del asistente
> 
