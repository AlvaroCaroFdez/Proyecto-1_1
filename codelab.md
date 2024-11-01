author: Álvaro Caro Fernández
summary: Guía para bastionar BIOS/UEFI
id: Proyecto 1.1
categories: codelab,markdown
environments: Web
status: Publicado

# Guía para bastionar BIOS/UEFI

## ÍNDICE
- [Introducción](#introducción)
- [Acceso a la BIOS/UEFI](#acceso-a-la-biosuefi)
- [Configuraciones de Seguridad](#configuraciones-de-seguridad)
- [Configuraciones de Arranque](#configuraciones-de-arranque)
- [Actualización de la BIOS/UEFI](#actualización-de-la-biosuefi)
- [Opciones Avanzadas de Seguridad (Opcional)](#opciones-avanzadas-de-seguridad-opcional)
- [Guardar y Salir](#guardar-y-salir)
- [Verificación de Cambios](#verificación-de-cambios)
- [Conclusión](#conclusión)

## Introducción

La BIOS (Basic Input/Output System) y su sucesora, la UEFI (Unified Extensible Firmware Interface), son componentes fundamentales en la arquitectura de cualquier ordenador. Su función principal es inicializar el hardware durante el proceso de arranque y proporcionar un entorno para que el sistema operativo cargue. A través de la BIOS/UEFI, se puede acceder a diversas configuraciones relacionadas con el hardware, como la secuencia de arranque, las configuraciones de dispositivos y las opciones de seguridad.

Bastionar la BIOS/UEFI implica fortalecer su configuración para proteger el sistema contra ataques y accesos no autorizados. Este proceso es esencial para proteger el ordenador de amenazas potenciales, como malware que intenta ejecutarse antes de que el sistema operativo esté operativo. El bastionado puede incluir acciones como establecer contraseñas para la configuración de la BIOS, habilitar el arranque seguro, y deshabilitar opciones de arranque que no sean necesarias, así como actualizar el firmware a la última versión disponible.

El objetivo de bastionar la BIOS/UEFI es crear una capa adicional de seguridad que dificulte los intentos de manipulación del sistema y asegure que solo se ejecuten software y procesos autorizados. En un entorno donde las amenazas cibernéticas son cada vez más sofisticadas, garantizar que la BIOS/UEFI esté adecuadamente protegida se convierte en una parte crucial de la estrategia de seguridad general de un ordenador.

Esta guía tiene como objetivo proporcionar un conjunto de pasos prácticos para bastionar la BIOS/UEFI de mi portátil personal, en concreto un HP laptop 15-dw0xxx, asegurando así un entorno más seguro y resistente a ataques.

## Acceso a la BIOS/UEFI

Para comenzar el proceso de bastionización, es necesario acceder a la configuración de la BIOS/UEFI del portátil. Primero, se debe reiniciar el ordenador. Durante el arranque, es muy importante estar atento para presionar repetidamente la tecla Esc o F10. Esto abrirá un menú de inicio. En este menú, al seleccionar F10, se ingresará directamente a la configuración de la BIOS/UEFI. Este es el punto de partida para realizar las configuraciones necesarias que mejorarán la seguridad del sistema.

## Configuraciones de Seguridad

Una vez que se ha accedido a la BIOS/UEFI, el siguiente paso crucial es ajustar las configuraciones de seguridad para proteger el sistema.

Primero, se debe localizar la sección Security. Dentro de esta sección, la opción más significativa es Set Supervisor Password. Configurar una contraseña de supervisor es un paso fundamental, ya que esta contraseña impide que personas no autorizadas realicen cambios en la configuración de la BIOS. Al seleccionar esta opción, se debe introducir una contraseña que combine letras mayúsculas y minúsculas, números y símbolos, lo que fortalece su seguridad. Es importante que la contraseña sea lo suficientemente compleja como para resistir ataques de fuerza bruta, pero también fácil de recordar para el propietario del dispositivo. De no configurarse una contraseña, cualquier persona que tenga acceso físico al ordenador podría modificar la configuración de la BIOS, poniendo en riesgo la seguridad del sistema.

Tras establecer la contraseña, es recomendable habilitar la opción de arranque seguro (Secure Boot). Esta característica se encuentra generalmente en la sección Boot de la BIOS/UEFI. Al activar el arranque seguro, se permite que el firmware del sistema valide que el software que se intenta cargar durante el proceso de arranque es auténtico y no ha sido alterado. Esto se realiza mediante el uso de certificados digitales que deben estar firmados por entidades de confianza. Con el arranque seguro habilitado, se previene que malware, rootkits o cualquier otro software no autorizado se inicie antes de que el sistema operativo cargue, lo que agrega una capa adicional de protección al dispositivo. Además, se recomienda revisar la lista de certificados y asegurarse de que solo se permitan aquellos que son necesarios para el funcionamiento del sistema.

Otro ajuste crítico a considerar es la función de arranque rápido (Fast Boot). Esta opción, que se puede encontrar en la sección de Boot Options, permite que el ordenador se inicie más rápidamente al omitir ciertas pruebas de hardware y el chequeo de dispositivos durante el arranque. Si bien esto puede ser conveniente para el usuario, desactivar el arranque rápido permite que el proceso de arranque sea más completo y, por lo tanto, facilita el acceso a la BIOS si se necesitan realizar ajustes adicionales en el futuro. Con el arranque rápido desactivado, el sistema ejecuta todos los diagnósticos necesarios, lo que asegura que todo el hardware funcione correctamente antes de cargar el sistema operativo.

## Configuraciones de Arranque

La siguiente etapa es asegurar que la configuración del arranque sea la adecuada. En la misma sección de Boot, se debe establecer el disco duro como la primera opción de arranque. Este cambio garantiza que el sistema operativo se cargue desde el disco duro, minimizando el riesgo de que se inicie desde dispositivos externos no autorizados, que podrían contener software malicioso.

Además, es importante desactivar dispositivos que no se utilicen con frecuencia, como puertos USB o Ethernet. Esto se puede hacer en la sección de configuración de arranque. Al desactivar estos dispositivos, se reduce la posibilidad de que un atacante pueda utilizar un dispositivo externo para comprometer el sistema.

## Actualización de la BIOS/UEFI

Mantener la BIOS/UEFI actualizada es una parte crucial del proceso de seguridad. Para verificar si hay actualizaciones disponibles, se debe visitar el sitio web de HP y buscar el modelo específico del portátil. En la página de soporte, se puede encontrar la última versión del firmware de la BIOS.

Una vez que se ha localizado la actualización, es fundamental seguir las instrucciones proporcionadas por HP para realizar la actualización de manera segura. Esto generalmente implica descargar el archivo de actualización y ejecutarlo desde Windows o directamente desde la BIOS. Asegurarse de que la BIOS esté actualizada ayuda a proteger el sistema contra vulnerabilidades y ataques recientes.

## Opciones Avanzadas de Seguridad (Opcional)

Para aquellos que deseen fortalecer aún más la seguridad, existen opciones avanzadas que se pueden considerar. Una de ellas es la configuración del TPM (Trusted Platform Module). En la sección de security, se debe buscar la opción TPM Device y asegurarse de que esté habilitada. Esta característica proporciona un nivel adicional de seguridad, especialmente en lo que respecta a la encriptación de datos sensibles.

Además, es recomendable limitar el acceso a la BIOS. Esto se puede hacer restringiendo el acceso a la configuración de la BIOS a solo usuarios autorizados. Esto podría incluir la creación de cuentas de usuario específicas o el uso de contraseñas adicionales para proteger el acceso.

## Guardar y Salir

Una vez que se han realizado todos los cambios necesarios, es esencial guardar la configuración. Para ello, se debe seleccionar la opción de Exit y luego elegir Save Changes and Exit. Este paso asegura que todos los ajustes realizados se guarden correctamente y se apliquen en el próximo arranque del sistema.

## Verificación de Cambios

Después de reiniciar el ordenador, es útil verificar que los cambios realizados en la BIOS/UEFI se hayan aplicado correctamente. Para ello, se puede volver a ingresar a la BIOS y confirmar que ajustes como la contraseña, el arranque seguro y el orden de arranque están activados y configurados según lo configurado anteriormente.

## Conclusión

Bastionar la BIOS/UEFI es un aspecto esencial para asegurar la integridad y seguridad del sistema. La BIOS/UEFI, al ser el primer software que se ejecuta al encender el dispositivo, establece las bases para el funcionamiento seguro de todo el sistema operativo y las aplicaciones. Configurar adecuadamente las opciones de seguridad, como establecer una contraseña de supervisor, habilitar el arranque seguro y desactivar funciones como el arranque rápido, contribuye significativamente a proteger el dispositivo de accesos no autorizados y ataques de malware.

Al implementar estas medidas de seguridad, se minimiza el riesgo de que software no autorizado se ejecute durante el arranque, lo que puede comprometer no solo el hardware, sino también los datos y la privacidad del usuario. La seguridad en la BIOS/UEFI no debe ser un proceso aislado; es fundamental mantenerla actualizada y revisarla periódicamente para adaptarse a nuevas amenazas y vulnerabilidades.

En resumen, bastionar la BIOS/UEFI es una inversión crucial en la protección del portátil y de la información personal del usuario. Al tomar estas precauciones, se promueve un entorno más seguro y confiable para el uso diario de la tecnología, contribuyendo a la defensa frente a los constantes desafíos de seguridad en el mundo digital.