# chisel - linux_amd64
# Otras versiones -> https://github.com/jpillora/chisel/releases
Con este binario de chisel para  linux x64 podemos realizar un port forwarding desde una maquina a la que tengamos acceso, redireccionando los puertos y pudiendo acceder a su intranet desde nuestra maquina local
El binario no necesita compilacion ni instalacion, es Plug&Play. 

Lo primero es extraer el binario.

    gunzip chisel_1.8.1_linux_amd64.gz

Para establecer un port forwarding seguiremos los siguientes comandos.

Maquina local(host):

    ./chisel server -p [PUERTO] --reverse
  
Maquina remota(victim)>

    .chisel client [IP_HOST]:[PUERTO_HOST] R:[PUERTO_LOCAL_REDIRECCION]:[IP_VICTIMA_INTRANET]:[PUERTO_INTRANET]
  
  
Tanto la ip como el puerto de la victima dependeran de la maquina, pero al tratarse de puertos locales y que no son visibles desde fuera,
se encontraran en localhost/127.0.0.1 y el puerto dependera de cada maquina. 

Se pueden ver los puertos con:

    netstat -tlnp 
