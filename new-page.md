---
title: NEW PRUEBA
description: 
published: true
date: 2024-01-05T11:20:09.326Z
tags: 
editor: markdown
dateCreated: 2024-01-05T11:12:01.389Z
---

## GDE por wan de Fleming debido a problemas de Telecom en Dir Gral.

---

# Redirigir GDE por FLEMING

### host: srvvpn.intranet

Archivo /etc/openvpn/vpn\_fleming.conf, como menciona el comentario descomente las lineas como se muestra :

```plaintext
#----------------------------------------------------------------------
#GDE para OSEP, usando vinc. wan de fleming:
#----------------------------------------------------------------------
#Esta config. esta acompaniada de cambios en /etc/openvpn/scripts/on_connect_fleming.sh
#Para Activar descomente:
 route 10.160.2.131 255.255.255.255
 route 10.160.2.132 255.255.255.255
 route 10.160.2.128 255.255.255.255
 route 10.160.1.3   255.255.255.255
```

Archivo /etc/openvpn/scripts/on\_connect\_fleming.sh, como menciona el comentario descomente las lineas como se muestra :

```plaintext
#----------------------------------------------------------------------
#GDE para OSEP, usando vinc. wan de fleming:
|#----------------------------------------------------------------------
#Esta config. esta acompaniada de cambios en /etc/openvpn/scripts/on_connect_fleming.sh
#Para Activar descomente:
echo iroute 10.160.2.131 255.255.255.255 >> $1
echo iroute 10.160.2.132 255.255.255.255 >> $1
echo iroute 10.160.2.128 255.255.255.255 >> $1
echo iroute 10.160.1.3   255.255.255.255 >> $1
```

**Para activar cambio:** kill a proceso openvpn para que sea relanzado.

### host: proxy.fleming.intranet (loguearse a ip de la wan: 192.168.126.18)

Archivo /etc/rc.local.d/rc.route2, como menciona el comentario descomente las lineas como se muestra :

        #----------------------------------------------------------------------

        #GDE para OSEP, usando vinc. wan de fleming:

        #----------------------------------------------------------------------

        #Esta config. esta acompaniada de cambios en /etc/rc.local.d/rc.firewall, function \_start\_wan

        #Para Activar descomente:

        ip route $CMD 10.160.2.131/32 via 10.101.56.1

        ip route $CMD 10.160.2.132/32 via 10.101.56.1

        ip route $CMD 10.160.2.128/32 via 10.101.56.1

        ip route $CMD 10.160.1.3/32   via 10.101.56.1

**Para activar cambio:**

        # /etc/rc.local.d/rc.route2 restart

# Retornar a situación default : GDE por OSEP

### host: srvvpn.intranet

Archivo /etc/openvpn/vpn\_fleming.conf, como menciona el comentario, **debe volver a comentar las lineas como se muestra** : 

#----------------------------------------------------------------------

#GDE para OSEP, usando vinc. wan de fleming:

#----------------------------------------------------------------------

#Esta config. esta acompaniada de cambios en /etc/openvpn/scripts/on\_connect\_fleming.sh

#Para Activar descomente:

#route 10.160.2.131 255.255.255.255

#route 10.160.2.132 255.255.255.255

#route 10.160.2.128 255.255.255.255

#route 10.160.1.3   255.255.255.255

Archivo /etc/openvpn/scripts/on\_connect\_fleming.sh , **debe volver a comentar las lineas como se muestra** :

#----------------------------------------------------------------------

#GDE para OSEP, usando vinc. wan de fleming:

#----------------------------------------------------------------------

#Esta config. esta acompaniada de cambios en /etc/openvpn/scripts/on\_connect\_fleming.sh

#Para Activar descomente:

#echo iroute 10.160.2.131 255.255.255.255 >> $1

#echo iroute 10.160.2.132 255.255.255.255 >> $1

#echo iroute 10.160.2.128 255.255.255.255 >> $1

#echo iroute 10.160.1.3   255.255.255.255 >> $1

**Para activar cambio:** kill a proceso openvpn para que sea relanzado.

### host: proxy.fleming.intranet

Archivo /etc/rc.local.d/rc.route2, como menciona en comentario, **debe volver a comentar las lineas como se muestra** :

        #----------------------------------------------------------------------

        #GDE para OSEP, usando vinc. wan de fleming:

        #----------------------------------------------------------------------

        #Esta config. esta acompaniada de cambios en /etc/rc.local.d/rc.firewall, function \_start\_wan

        #Para Activar descomente:

        #ip route $CMD 10.160.2.131/32 via 10.101.56.1

        #ip route $CMD 10.160.2.132/32 via 10.101.56.1

        #ip route $CMD 10.160.2.128/32 via 10.101.56.1

        #ip route $CMD 10.160.1.3/32   via 10.101.56.1

**Para activar cambio:**

        # /etc/rc.local.d/rc.route2 restart 

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Mi Aplicación</title>
</head>
<body>

   <h1>Hola, Mundo!</h1>

   <script>
       // Tu código JavaScript va aquí

       // Ejemplo de código:
       let nombre = prompt("Ingrese su nombre:");
       alert("Hola, " + nombre + "! Bienvenido a mi aplicación.");
   </script>

</body>
</html>
```