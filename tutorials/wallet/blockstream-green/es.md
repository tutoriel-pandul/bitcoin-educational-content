---
name: Blockstream Green - Móvil
description: Configuración de una cartera de software móvil
---
![cover](assets/cover.webp)

Una cartera de software es una aplicación instalada en una computadora, smartphone u otro dispositivo conectado a Internet, que permite la gestión y seguridad de las claves de una cartera de Bitcoin. A diferencia de las carteras de hardware, que aíslan las claves privadas, las carteras "calientes" operan en un entorno potencialmente expuesto a ciberataques, aumentando los riesgos de hackeo y robo.

Las carteras de software se deben usar para gestionar cantidades razonables de bitcoins, especialmente para transacciones diarias. Esto también puede ser una opción interesante para personas con un portafolio limitado de Bitcoin, para quienes invertir en una cartera de hardware puede parecer desproporcionado. Sin embargo, su constante exposición a Internet las hace menos seguras para almacenar tus ahorros a largo plazo o fondos significativos. Para estos, es preferible optar por soluciones más seguras, como las carteras de hardware.

En este tutorial, te presentaré una de las mejores soluciones de cartera de software móvil: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Si estás interesado en aprender cómo usar Blockstream Green en una computadora, por favor consulta este otro tutorial:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Introducción a Blockstream Green

Blockstream Green es una cartera de software disponible tanto en móvil como en computadora. Anteriormente conocida como *Green Address*, esta cartera se convirtió en un proyecto de Blockstream tras su adquisición en 2016.

Green es una aplicación que es particularmente fácil de usar, lo que la hace interesante para principiantes. Ofrece todas las características esenciales de una buena cartera de Bitcoin, incluyendo RBF (*Replace-by-Fee*), una opción para conectarse a través de Tor, la capacidad de conectar tu propio nodo, la opción SPV (*Simple Payment Verification*), etiquetado y control de monedas.

Blockstream Green también admite la red Liquid, una sidechain de Bitcoin desarrollada por Blockstream para realizar transacciones rápidas y confidenciales fuera de la blockchain principal. Este tutorial se enfoca exclusivamente en Bitcoin, pero uno futuro abordará el uso de Liquid.

## Instalando y Configurando la App Blockstream Green

El primer paso es, naturalmente, descargar la app Green. Ve a tu tienda de aplicaciones:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Para usuarios de Android, también tienes la opción de instalar la aplicación a través del archivo `.apk` [disponible en el GitHub de Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Inicia la aplicación, luego marca la casilla "*Acepto las condiciones...*".
![GREEN](assets/fr/04.webp)

Cuando abres Green por primera vez, la pantalla de inicio aparece sin ninguna cartera configurada. Más tarde, si creas o importas carteras, aparecerán en esta interfaz. Antes de pasar a crear una cartera, te aconsejo ajustar la configuración de la aplicación según tus expectativas. Haz clic en "*Configuración de la Aplicación*".

![GREEN](assets/fr/05.webp)

La opción "*Privacidad Mejorada*", disponible solo en Android, mejora la privacidad al deshabilitar capturas de pantalla y ocultar vistas previas de la aplicación. También bloquea automáticamente el acceso a la aplicación tan pronto como tu teléfono se bloquea, haciendo que tus datos sean más difíciles de exponer.

![GREEN](assets/fr/06.webp)
Para aquellos que deseen mejorar su privacidad, la aplicación ofrece la opción de enrutar su tráfico a través de Tor, una red que encripta todas sus conexiones y hace que sus actividades sean difíciles de rastrear. Aunque esta opción puede ralentizar ligeramente el rendimiento de la aplicación, se recomienda encarecidamente para proteger su privacidad, especialmente si no está utilizando su propio nodo completo.
![GREEN](assets/fr/07.webp)

Para los usuarios que tienen su propio nodo completo, Green Wallet ofrece la posibilidad de conectarse a él a través de un servidor Electrum, asegurando el control total sobre la información de la red Bitcoin y la transmisión de transacciones.

![GREEN](assets/fr/08.webp)

Otra característica alternativa es la opción de "*Verificación SPV*", que permite la verificación directa de ciertos datos de la blockchain, reduciendo la necesidad de confiar en el nodo predeterminado de Blockstream, aunque este método no proporciona todas las garantías de un nodo completo.

![GREEN](assets/fr/09.webp)

Una vez que estos ajustes estén configurados según sus necesidades, haga clic en el botón "*Guardar*" y reinicie la aplicación.

![GREEN](assets/fr/10.webp)

## Creando una Cartera de Bitcoin en Blockstream Green

Ahora estás listo para crear una cartera de Bitcoin. Haz clic en el botón "*Comenzar*".

![GREEN](assets/fr/11.webp)

Tienes la opción de crear una cartera de software localmente o gestionar una cartera fría a través de una cartera de hardware. Para este tutorial, nos centraremos en crear una cartera caliente, por lo que necesitarás seleccionar la opción "*En este dispositivo*". En un futuro tutorial, te mostraré cómo usar la otra opción.

La opción "*Solo visualización*", por otro lado, te permite importar una clave pública extendida (`xpub`) para ver las transacciones de una cartera sin poder gastar los fondos asociados, lo cual es conveniente para monitorear una cartera en una cartera de hardware, por ejemplo.

![GREEN](assets/fr/12.webp)
Luego puedes elegir restaurar una cartera de Bitcoin existente o crear una nueva. Para los propósitos de este tutorial, crearemos una nueva cartera. Sin embargo, si necesitas regenerar una cartera de Bitcoin ya existente a partir de su frase mnemotécnica, por ejemplo, debido a la pérdida de tu cartera de hardware, necesitarás elegir la segunda opción.
![GREEN](assets/fr/13.webp)

Luego tienes la opción entre una frase mnemotécnica de 12 palabras o 24 palabras. Esta frase te permitirá recuperar el acceso a tu cartera desde cualquier software compatible en caso de problemas con tu teléfono. Actualmente, optar por una frase de 24 palabras no ofrece más seguridad que una frase de 12 palabras. Por lo tanto, recomiendo elegir una frase mnemotécnica de **12 palabras**.

Green te proporcionará entonces tu frase mnemotécnica. Antes de continuar, asegúrate de no estar siendo observado. Haz clic en "*Mostrar frase de recuperación*" para mostrarla en la pantalla.

![GREEN](assets/fr/14.webp)

**Esta frase mnemotécnica otorga acceso completo y sin restricciones a todos tus bitcoins.** Cualquiera en posesión de esta frase puede robar tus fondos, incluso sin acceso físico a tu teléfono.

Te permite restaurar el acceso a tus bitcoins en caso de pérdida, robo o daño a tu teléfono. Por lo tanto, es muy importante guardarla cuidadosamente **en un medio físico (no digital)** y almacenarla en un lugar seguro. Puedes escribirla en un pedazo de papel, o para más seguridad, si esta cartera es importante, recomiendo grabarla en un medio de acero inoxidable para proteger contra los riesgos de incendios, inundaciones o derrumbes (para una cartera caliente destinada a asegurar una pequeña cantidad de bitcoins, una copia de seguridad en papel simple probablemente sea suficiente).
*Obviamente, nunca deberías compartir estas palabras en internet, contrario a lo que estoy haciendo en este tutorial. Esta cartera de ejemplo se usará solo en Testnet y será eliminada al final del tutorial.*
![GREEN](assets/fr/15.webp)

Después de anotar correctamente tu frase mnemotécnica en un medio físico, haz clic en "*Continuar*". Green Wallet te pedirá entonces que confirmes ciertas palabras de tu frase para verificar que las has registrado correctamente. Rellena los espacios en blanco con las palabras que faltan.

![GREEN](assets/fr/16.webp)

Elige el código PIN para tu dispositivo, que se utilizará para desbloquear tu cartera Green. Esto es, por lo tanto, una protección contra el acceso físico no autorizado. Este código PIN no juega un papel en la derivación de las claves criptográficas de tu cartera. Así, incluso sin acceso a este código PIN, la posesión de tu frase mnemotécnica de 12 o 24 palabras te permitirá recuperar el acceso a tus bitcoins.
Se recomienda elegir un PIN de 6 dígitos que sea lo más aleatorio posible. Además, asegúrate de respaldar este código para no olvidarlo, de lo contrario, te verás obligado a recuperar tu cartera usando la frase mnemotécnica. Posteriormente, puedes añadir una opción de bloqueo biométrico para evitar introducir el PIN con cada uso. En términos generales, la biometría es mucho menos segura que el propio PIN. Por lo tanto, por defecto, aconsejo no configurar esta opción de desbloqueo.
![GREEN](assets/fr/17.webp)

Introduce tu PIN una segunda vez para confirmarlo.

![GREEN](assets/fr/18.webp)

Espera a que tu cartera sea creada, luego haz clic en el botón "*Crear una cuenta*".

![GREEN](assets/fr/19.webp)

Luego tienes la opción entre una cartera de firma única estándar, que usaremos en este tutorial, o una cartera protegida por autenticación de dos factores (2FA).

![GREEN](assets/fr/20.webp)

La opción 2FA en Green crea una cartera multisignatura 2/2, una de cuyas claves es mantenida por Blockstream. Esto significa que para realizar una transacción, se requieren ambas claves: una clave local protegida por tu PIN en tu teléfono, y una clave remota asegurada por 2FA en los servidores de Blockstream. En caso de pérdida de acceso a 2FA o indisponibilidad de los servicios de Blockstream, los mecanismos de recuperación basados en scripts de time-lock aseguran la posibilidad de recuperar independientemente tus fondos. Aunque esta configuración reduce significativamente el riesgo de que tus bitcoins sean robados, es más compleja de manejar y depende parcialmente de Blockstream. Para este tutorial, optaremos por una cartera de firma única clásica, con claves almacenadas localmente en el teléfono.

¡Y ahí lo tienes, tu cartera de Bitcoin ha sido creada exitosamente usando la app Green!

![GREEN](assets/fr/21.webp)

Antes de recibir tus primeros bitcoins en tu cartera, **te aconsejo encarecidamente realizar una prueba de recuperación en seco**. Anota una información de referencia, como tu xpub o la primera dirección de recepción, luego elimina tu cartera en la app Green mientras aún está vacía. A continuación, intenta restaurar tu cartera en Green usando tus respaldos de papel. Comprueba que la información testigo generada después de la restauración coincide con la que inicialmente anotaste. Si este es el caso, puedes estar seguro de que tus respaldos de papel son fiables. Para aprender más sobre cómo realizar una prueba de recuperación, te aconsejo consultar este otro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Configurando tu cartera en Blockstream Green
Si quieres personalizar tu cartera, haz clic en los tres puntitos en la parte superior derecha.
![GREEN](assets/fr/22.webp)
La opción "*Rename*" te permite personalizar el nombre de tu cartera, lo cual es particularmente útil si gestionas múltiples carteras en la misma aplicación.
![VERDE](assets/fr/23.webp)

El menú "*Unit*" te da la opción de cambiar la unidad base de tu cartera. Por ejemplo, puedes elegir mostrarla en satoshis en lugar de en bitcoins.

![VERDE](assets/fr/24.webp)

El menú "*Settings*" proporciona acceso a las diferentes opciones de tu cartera de Bitcoin.

![VERDE](assets/fr/25.webp)

Aquí, por ejemplo, encontrarás tu clave pública extendida y su *descriptor*, útil si planeas configurar una cartera de solo visualización a partir de esta cartera.

![VERDE](assets/fr/26.webp)

También puedes cambiar el código PIN de tu cartera y habilitar el inicio de sesión biométrico.

![VERDE](assets/fr/27.webp)

## Usando Blockstream Green

Ahora que tu cartera de Bitcoin está configurada, ¡estás listo para recibir tus primeros sats! Para hacerlo, simplemente haz clic en el botón "*Receive*".

![VERDE](assets/fr/28.webp)

Green mostrará entonces la primera dirección de recepción en blanco de tu cartera. Puedes escanear el código QR asociado o copiar la dirección directamente para enviar bitcoins a ella. Este tipo de dirección no especifica la cantidad a ser enviada por el pagador. Sin embargo, puedes generar una dirección que solicite una cantidad específica, haciendo clic en los tres pequeños puntos en la parte superior derecha, luego en "*Request Amount*", e ingresando la cantidad deseada.

Dado que estás utilizando una cuenta Segwit v0 (BIP84), tu dirección comenzará con `bc1q...`. En mi ejemplo, estoy usando una cartera de Testnet, por lo que el prefijo es ligeramente diferente.

![VERDE](assets/fr/29.webp)

Cuando la transacción se difunda en la red, aparecerá en tu cartera.

![VERDE](assets/fr/30.webp)

Espera a obtener suficientes confirmaciones para considerar la transacción como final.

![VERDE](assets/fr/31.webp)

Con bitcoins en tu cartera, ahora también puedes enviarlos. Haz clic en "*Send*".

![VERDE](assets/fr/32.webp)

En la siguiente página, ingresa la dirección del destinatario. Puedes ingresarla manualmente o escanear un código QR.

![VERDE](assets/fr/33.webp)

Elige la cantidad de pago.

![VERDE](assets/fr/34.webp)
En la parte inferior de la pantalla, puedes seleccionar la tasa de comisión para esta transacción. Tienes la opción de seguir las recomendaciones de la aplicación o personalizar tus comisiones. Cuanto más altas sean las comisiones en comparación con otras transacciones pendientes, más rápido se procesará tu transacción. Para entender el mercado de comisiones, puedes visitar [Mempool.space](https://mempool.space/) en la sección "*Transaction Fees*".
![VERDE](assets/fr/35.webp)

Haz clic en "*Next*" para acceder a una pantalla resumen de tu transacción. Verifica que la dirección, cantidad y comisiones sean correctas.

![VERDE](assets/fr/36.webp)

Si todo es de tu satisfacción, desliza el botón verde en la parte inferior de la pantalla hacia la derecha para firmar y difundir la transacción en la red Bitcoin.

![VERDE](assets/fr/37.webp)

Tu transacción ahora aparecerá en el tablero de tu cartera de Bitcoin esperando confirmación.

![VERDE](assets/fr/38.webp)
*Este tutorial se basa en [una versión original perteneciente a Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) escrita por Loïc Morel. Bitstack es una neo-banco francés de Bitcoin que ofrece la posibilidad de ahorrar en bitcoins, ya sea a través de DCA (Dollar Cost Averaging) o mediante un sistema automático de redondeo de gastos diarios.*