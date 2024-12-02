---
name: Blockstream Green - Escritorio
description: Uso del software Green Wallet en una computadora
---
![cover](assets/cover.webp)

En este tutorial, exploraremos cómo usar el software Blockstream Green en una computadora para gestionar una billetera segura en un monedero hardware. Al usar un monedero hardware, es esencial utilizar software en tu computadora para gestionar esta billetera. Este software de gestión no tiene acceso a las claves privadas; se utiliza solo para verificar el saldo de tu billetera, generar direcciones de recepción y construir y transmitir transacciones que serán firmadas por el monedero hardware. Green representa una de las muchas soluciones disponibles para gestionar tu Bitcoin hardware wallet.

En 2024, Blockstream Green solo es compatible con Ledger Nano S (versión anterior), Ledger Nano X, Trezor One, Trezor T y dispositivos Blockstream Jade.

## Introducción a Blockstream Green

Blockstream Green es un software disponible tanto para móviles como para escritorio. Anteriormente conocido como Green Address, este monedero se convirtió en un proyecto de Blockstream tras su adquisición en 2016.

Green es una aplicación muy amigable para el usuario, lo que la hace particularmente adecuada para principiantes. Ofrece varias características, como la gestión de monederos calientes, monederos hardware, así como monederos en la sidechain Liquid. También puedes usarlo para configurar un monedero solo para ver.

![GREEN-DESKTOP](assets/fr/01.webp)

En este tutorial, nos centraremos únicamente en el uso del software en una computadora. Para explorar otros usos de Green, te invito a consultar nuestros otros tutoriales dedicados:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Instalando y Configurando el Software Blockstream Green

Comienza instalando el software Blockstream Green en tu computadora. Ve al [sitio web oficial](https://blockstream.com/green/) y haz clic en el botón "*Descargar Ahora*". Luego sigue el proceso de instalación según tu sistema operativo.

![GREEN-DESKTOP](assets/fr/02.webp)

Inicia la aplicación, luego marca la casilla "*Acepto los términos...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Cuando abras Green por primera vez, aparecerá la pantalla de inicio sin ninguna billetera configurada. Más tarde, si creas o importas billeteras, aparecerán en esta interfaz. Antes de pasar a crear una billetera, te aconsejo ajustar la configuración de la aplicación según tus expectativas. Haz clic en el icono de configuración en la parte inferior izquierda.

![GREEN-DESKTOP](assets/fr/04.webp)

En el menú "*General*", puedes cambiar el idioma del software y habilitar características experimentales si lo deseas.

![GREEN-DESKTOP](assets/fr/05.webp)
En el menú "*Red*", puedes habilitar la conexión a través de Tor, una red que encripta todas tus conexiones y hace que tus actividades sean difíciles de rastrear. Aunque esta opción puede ralentizar ligeramente el rendimiento de la aplicación, se recomienda encarecidamente para proteger tu privacidad, especialmente si no estás utilizando tu propio nodo completo.
![GREEN-DESKTOP](assets/fr/06.webp)

Para los usuarios que tienen su propio nodo completo, Green ofrece la posibilidad de conectarse a él a través de un servidor Electrum, asegurando el control total sobre la información de la red Bitcoin y la transmisión de transacciones. Para hacer esto, haz clic en el menú "*Servidores personalizados y validación*", luego ingresa la información de tu servidor Electrum.

![GREEN-DESKTOP](assets/fr/07.webp)
Otra característica alternativa es la opción de "*Verificación SPV*" (SPV Verification), que permite la verificación directa de ciertos datos de la blockchain, reduciendo así la necesidad de confiar en el nodo predeterminado de Blockstream, aunque este método no proporciona todas las garantías de un nodo completo. Esta opción también se encuentra en el menú "*Servidores personalizados y validación*" (Custom servers and validation).
![GREEN-DESKTOP](assets/fr/08.webp)

Una vez que estos ajustes se hayan modificado según tus necesidades, puedes salir de esta interfaz.

## Importando una Cartera de Bitcoin en Blockstream Green

Ahora estás listo para importar tu cartera de Bitcoin. Haz clic en el botón "**Comenzar**" (Get Started).

![GREEN-DESKTOP](assets/fr/09.webp)

Tienes la opción de crear una cartera de software local o gestionar una cartera fría a través de una cartera de hardware. Para este tutorial, nos centraremos en la gestión de una cartera de hardware, por lo que necesitarás seleccionar la opción "*En Cartera de Hardware*" (On Hardware Wallet).

La opción "*Solo visualización*" (Watch-only), por otro lado, te permite importar una clave pública extendida (`xpub`) para ver las transacciones de una cartera sin poder gastar los fondos asociados.

![GREEN-DESKTOP](assets/fr/10.webp)

Si estás usando un Jade, haz clic en el botón correspondiente. De lo contrario, selecciona "*Conectar un Dispositivo de Hardware diferente*" (Connect a different Hardware Device). En mi caso, estoy usando un Ledger Nano S. Para los usuarios de Ledger, asegúrate de instalar la aplicación "*Bitcoin Legacy*" en tu cartera de hardware, ya que Green solo admite esta versión.

![GREEN-DESKTOP](assets/fr/11.webp)

Conecta tu cartera de hardware al ordenador y selecciónala en Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Espera mientras Green importa la información de tu cartera, después de lo cual podrás acceder a ella.

![GREEN-DESKTOP](assets/fr/13.webp)

En este punto, dos escenarios son posibles. Si ya habías usado tu cartera de hardware antes, deberías ver tu cuenta aparecer en el software. Pero si, como yo, acabas de inicializar tu cartera de hardware generando una frase mnemotécnica sin haberla usado aún, necesitarás crear una cuenta. Haz clic en "*Crear Cuenta*" (Create Account).
![GREEN-DESKTOP](assets/fr/14.webp)
Elige "*Estándar*" (Standard) si deseas usar una cartera clásica.

![GREEN-DESKTOP](assets/fr/15.webp)

Ahora tienes acceso a tu cuenta.

![GREEN-DESKTOP](assets/fr/16.webp)

## Usando una cartera de hardware con Blockstream Green

Ahora que tu cartera de Bitcoin está configurada, ¡estás listo para recibir tus primeros sats! Para hacerlo, simplemente haz clic en el botón "*Recibir*" (Receive).

![GREEN-DESKTOP](assets/fr/17.webp)

Haz clic en el botón "*Copiar dirección*" (Copy address) para copiar la dirección, o escanea su código QR.

![GREEN-DESKTOP](assets/fr/18.webp)

Una vez que la transacción se haya transmitido en la red, aparecerá en tu cartera. Espera a obtener suficientes confirmaciones para considerar la transacción como inmutable.

![GREEN-DESKTOP](assets/fr/19.webp)

Con bitcoins en tu cartera, ahora eres capaz de enviarlos. Haz clic en el botón "*Enviar*" (Send).

![GREEN-DESKTOP](assets/fr/20.webp)

En la página siguiente, ingresa la dirección del destinatario. Puedes ingresarla manualmente o escanear un código QR con tu webcam.

![GREEN-DESKTOP](assets/fr/21.webp)

Elige la cantidad de pago.

![GREEN-DESKTOP](assets/fr/22.webp)
En la parte inferior de la pantalla, puedes seleccionar la tarifa para esta transacción. Tienes la opción de seguir las recomendaciones de la aplicación o personalizar tus tarifas. Cuanto más altas sean las tarifas en comparación con otras transacciones pendientes, más rápido se procesará tu transacción. Para conocer el mercado de tarifas, puedes visitar [Mempool.space](https://mempool.space/) en la sección de "*Tarifas de Transacción*".
![GREEN-DESKTOP](assets/fr/23.webp)

Si deseas seleccionar específicamente qué UTXOs usar en tu transacción, haz clic en el botón de "*Selección manual de monedas*".

![GREEN-DESKTOP](assets/fr/24.webp)

Revisa la configuración de tu transacción y, si todo es como esperas, haz clic en "*Siguiente*".

![GREEN-DESKTOP](assets/fr/25.webp)

Verifica una vez más que la dirección, cantidad y tarifas sean correctas, luego haz clic en "*Confirmar transacción*".

![GREEN-DESKTOP](assets/fr/26.webp)

Asegúrate de que todos los parámetros de la transacción sean correctos en la pantalla de tu monedero hardware, luego firma la transacción usándolo.

![GREEN-DESKTOP](assets/fr/27.webp)

Una vez que la transacción esté firmada desde el monedero hardware, Green la transmite automáticamente en la red de Bitcoin. Tu transacción aparecerá entonces en el tablero de tu monedero de Bitcoin, pendiente de confirmación.

![GREEN-DESKTOP](assets/fr/28.webp)

Y ahí lo tienes, ahora sabes cómo configurar fácilmente el software Blockstream Green para gestionar tu monedero de Bitcoin en un monedero hardware.
Si encontraste útil este tutorial, te agradecería mucho si pudieras dejar un pulgar arriba abajo. Siéntete libre de compartir este artículo en tus redes sociales. ¡Muchas gracias!
También recomiendo revisar este tutorial completo sobre la aplicación móvil Blockstream Green para configurar un monedero caliente:

https://planb.network/tutorials/wallet/blockstream-green