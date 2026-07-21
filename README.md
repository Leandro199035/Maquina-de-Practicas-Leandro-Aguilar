### Descripción y Justificación Técnica

Las capturas muestran la instantánea (*snapshot*) **"Clean Install - Hardening applied"** en **VirtualBox** aplicada tanto a la máquina virtual de Linux ("Kali") como a la de Windows ("WindowsPrueba"). Su propósito en el trabajo práctico comprende:

* **Clean Install (Instalación Limpia):** Garantiza un entorno base sin *bloatware* ni configuraciones previas que alteren las pruebas en ambos sistemas.
* **Hardening (Bastionado):** Confirma la aplicación de políticas de seguridad (cierre de puertos, desactivación de servicios no esenciales y parches) para reducir la superficie de ataque.
* **Punto de Restauración (*Baseline*):** Funciona como línea base para revertir cualquier sistema a un estado seguro e inalterado en segundos si las máquinas se comprometen durante los ensayos de ciberseguridad.
<img width="1755" height="1076" alt="Sin título" src="https://github.com/user-attachments/assets/4ef328e1-50e5-43da-a162-85e40a4d9dde" />
<img width="1726" height="1077" alt="Sin título" src="https://github.com/user-attachments/assets/695b9e85-6d63-422a-a461-b5c849e07afe" />

### Análisis de Permisos de Archivos (`ls -l`)

La captura muestra la ejecución del comando `ls -l` en una terminal de Kali Linux, visualizando los permisos, propietarios y atributos de los archivos del directorio:

* **`laboratorio.exe`:** Muestra permisos `-rw-rw-r--` bajo el usuario `leandro`, indicando que tiene privilegios de lectura y escritura (`rw-`), permitiendo modificar su contenido.
* **`prueba.txt`:** Muestra permisos `-r--r--r--` bajo el usuario `root`, lo que indica que es un archivo de **solo lectura** (`r--`) para todos los usuarios, restringiendo cualquier intento de modificación o escritura.
<img width="1920" height="974" alt="VirtualBox_Kali_20_07_2026_22_45_40" src="https://github.com/user-attachments/assets/b1005182-dce6-4872-a5e3-922ace507db5" />

### Actualización Completa del Sistema Linux (`Kali`)

La captura demuestra que el sistema operativo Kali Linux se encuentra **completamente actualizado y al día** mediante los siguientes elementos:

* **Ejecución del Comando:** Se utilizó `sudo apt full-upgrade`, comando encargado de actualizar todos los paquetes e instalar las dependencias necesarias.
* **Resumen de Estado:** La línea final de la terminal confirma el estado con el mensaje: 
  `Actualizando: 0, Instalando 0, Eliminando: 0, no actualizando: 0`. Esto certifica que no hay ningún paquete pendiente de actualización.
* **Relevancia en Ciberseguridad:** Mantener el sistema completamente actualizado es fundamental dentro del proceso de *hardening* (bastionado), ya que elimina vulnerabilidades conocidas (CVEs) en el software y herramientas del sistema.
<img width="1920" height="974" alt="VirtualBox_Kali_20_07_2026_22_28_43" src="https://github.com/user-attachments/assets/df16d53f-0112-4ab0-878f-253711bd762d" />

### Configuración de Red: Adaptador Sólo Anfitrión (*Host-Only*)

La captura muestra la ventana de configuración de **VirtualBox** para la máquina virtual `Kali`, donde se ha seleccionado el modo de red **"Adaptador sólo anfitrión"** (*VirtualBox Host-Only Ethernet Adapter*):

* **Aislamiento del Entorno (*Sandboxing*):** Esta configuración desconecta la máquina virtual de la red local física e Internet, creando una red privada accesible únicamente entre la máquina anfitriona (*Host*) y las VMs del laboratorio.
* **Seguridad y Control:** Previene la fuga no deseada de tráfico de pruebas, evita ataques o escaneos hacia la red real y protege al sistema contra posibles amenazas externas procedentes de Internet durante las prácticas de ciberseguridad.
<img width="1894" height="1078" alt="620603126-51d56292-e39b-40a2-9a26-2a369cb26adf" src="https://github.com/user-attachments/assets/b453e500-30d1-4866-9c25-407b0ab2e7a3" />
<img width="1920" height="974" alt="VirtualBox_Kali_20_07_2026_21_27_47" src="https://github.com/user-attachments/assets/99175ba2-7244-44e1-af08-885f041fcd25" />
