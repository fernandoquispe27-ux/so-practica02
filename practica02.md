# Práctica 02 - xv6-riscv

## 1. Interfaz, tabla de despacho e implementación de dos llamadas al sistema nuevas

![Captura grep getpid](imgs/getpid.png)
### 1.1. Llamada al sistema: getpid
Para la llamada al sistema getpid, la secuencia inicia en el archivo kernel/syscall.h, donde se define la constante #define SYS_getpid 11 como su número de interfaz. Este número es utilizado en kernel/syscall.c para mapear la llamada en el arreglo de la tabla de despacho mediante el elemento [SYS_getpid] sys_getpid. Finalmente, cuando se efectúa la llamada, la tabla redirige la ejecución hacia la función sys_getpid() localizada en kernel/sysproc.c, la cual obtiene y devuelve el identificador de proceso actual (myproc()->pid).

![Captura grep read](imgs/read.png)
### 1.2. Llamada al sistema: read
En el caso de la llamada al sistema read, la secuencia se define mediante la constante #define SYS_read 5 en kernel/syscall.h, estableciendo así su número de interfaz. En kernel/syscall.c, esta posición se registra dentro del arreglo de la tabla de despacho como [SYS_read] sys_read. Al invocarse la llamada, el despacho redirige la instrucción hacia la función sys_read(), que se encuentra implementada en kernel/sysfile.c para realizar las operaciones de lectura directamente sobre el archivo o descriptor solicitado.
