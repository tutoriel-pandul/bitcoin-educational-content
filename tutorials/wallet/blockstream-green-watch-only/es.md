---
name: Blockstream Green - Solo Lectura
description: Configurando una cartera solo lectura
---
![cover](assets/cover.webp)

En este tutorial, aprenderás cómo configurar fácilmente una cartera solo lectura en móvil usando la aplicación Blockstream Green.

## ¿Qué es una Cartera Solo Lectura?

Una cartera solo lectura, o "watch-only wallet," es un tipo de software diseñado para permitir al usuario observar transacciones asociadas con una o más claves públicas de Bitcoin específicas, sin tener acceso a las claves privadas correspondientes.

Este tipo de aplicación solo retiene los datos necesarios para monitorear una cartera de Bitcoin, incluyendo ver su saldo e historial de transacciones, pero no tiene acceso a las claves privadas. Por lo tanto, es imposible gastar los bitcoins mantenidos en la cartera en la aplicación solo lectura.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Generalmente, se usa solo lectura en adición a una cartera de hardware. Esta última permite el almacenamiento seguro de las claves privadas de la cartera en un dispositivo no conectado a internet, que tiene una superficie de ataque mínima, aislando así las claves privadas de entornos potencialmente vulnerables. La aplicación solo lectura, por otro lado, almacena exclusivamente la clave pública extendida (`xpub`, `zpub`, etc.) de la cartera de Bitcoin. Esta clave padre no permite el descubrimiento de las claves privadas asociadas y, consecuentemente, no permite el gasto de bitcoins. Sin embargo, permite la derivación de claves públicas hijas y direcciones de recepción. Con el conocimiento de las direcciones de la cartera asegurada por la cartera de hardware, la aplicación solo lectura puede rastrear estas transacciones en la red de Bitcoin, ofreciendo al usuario la capacidad de monitorear su saldo y generar nuevas direcciones de recepción, sin tener que conectar su cartera de hardware cada vez.

En este tutorial, propongo descubrir una de las soluciones de cartera solo lectura más populares en móvil: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Introducción a Blockstream Green

Blockstream Green es un software disponible en móvil y computadora. Anteriormente conocida como Green Address, esta cartera se convirtió en un proyecto de Blockstream tras su adquisición en 2016.

Green es una aplicación muy fácil de usar, lo que la hace particularmente adecuada para principiantes. Ofrece varias características, como la gestión de carteras calientes, carteras de hardware, así como carteras en la sidechain Liquid.

En este tutorial, nos centraremos únicamente en crear una cartera solo lectura. Para explorar otros usos de Green, te invito a consultar nuestros otros tutoriales dedicados:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Instalando y Configurando la Aplicación Blockstream Green
El primer paso es naturalmente descargar la aplicación Green. Ve a tu tienda de aplicaciones:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Para usuarios de Android, también tienes la opción de instalar la aplicación a través del archivo `.apk` [disponible en GitHub de Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Inicia la aplicación, luego marca la casilla "*Acepto los términos...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Cuando abres Green por primera vez, la pantalla de inicio aparece sin una cartera configurada. Más tarde, si creas o importas carteras, aparecerán en esta interfaz. Antes de pasar a crear una cartera, te aconsejo que ajustes la configuración de la aplicación según tus expectativas. Haz clic en "*Configuración de la Aplicación*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

La opción "*Privacidad Mejorada*", disponible solo en Android, mejora la privacidad al deshabilitar las capturas de pantalla y ocultar las vistas previas de la aplicación. También bloquea automáticamente el acceso a la aplicación en cuanto tu teléfono se bloquea, haciendo que tus datos sean más difíciles de exponer.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Para aquellos que deseen mejorar su privacidad, la aplicación ofrece enrutamiento de tu tráfico a través de Tor, una red que encripta todas tus conexiones y hace que tus actividades sean difíciles de rastrear. Aunque esta opción puede ralentizar ligeramente el rendimiento de la aplicación, se recomienda encarecidamente para proteger tu privacidad, especialmente si no estás utilizando tu propio nodo completo.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Para los usuarios que tienen su propio nodo completo, Green Wallet ofrece la posibilidad de conectarse a él a través de un servidor Electrum, asegurando el control total sobre la información de la red Bitcoin y la transmisión de transacciones.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Otra característica alternativa es la opción de "*Verificación SPV*", que permite la verificación directa de ciertos datos de la blockchain, reduciendo así la necesidad de confiar en el nodo predeterminado de Blockstream, aunque este método no proporciona todas las garantías de un nodo completo.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Una vez que estos ajustes estén configurados según tus necesidades, haz clic en el botón "*Guardar*" y reinicia la aplicación.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Creando una cartera solo de observación en Blockstream Green
Ahora estás listo para crear una cartera solo de observación. Haz clic en el botón "*Comenzar*".
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Tendrás la opción de elegir entre varios tipos de carteras. Para este tutorial, queremos crear una cartera solo de observación, así que haz clic en el botón correspondiente.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Elige la opción "*Firma Única*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Luego selecciona "*Bitcoin*". Por mi parte, estoy realizando este tutorial en una cartera de testnet, pero el procedimiento sigue siendo el mismo en la mainnet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Se te pedirá que proporciones un clave pública extendida (`xpub`, `zpub`, etc.), o un descriptor de script de salida.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Necesitarás recuperar esta información de la cartera que deseas seguir a través de tu cartera solo de observación. La clave pública extendida no es sensible en términos de seguridad, ya que no permite el acceso a las claves privadas, pero es sensible para tu privacidad, ya que revela todas tus claves públicas y por lo tanto todas tus transacciones de Bitcoin.

Imagina que estás usando Sparrow Wallet para gestionar tu cartera en un monedero hardware, encontrarás esta información en la sección de "*Configuración*". Encontrar esta información dependerá del software de gestión de carteras que estés utilizando, pero generalmente se encuentra en la configuración.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Copia tu clave pública extendida e ingrésala en la aplicación Green, luego haz clic en "*Conectar*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Entonces podrás ver el saldo asociado con esta clave, así como el historial de transacciones.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Al hacer clic en "*Recibir*", puedes generar una dirección de recepción para recibir bitcoins en tu monedero hardware. Sin embargo, te aconsejo no usar esta opción sin antes verificar en la pantalla del monedero hardware que posee la clave privada asociada con la dirección generada, antes de usarla para bloquear bitcoins. Esta es una buena práctica a seguir.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

La opción "*Barrer*" te permite ingresar manualmente una clave privada para gastar fondos directamente desde tu aplicación Green. Excepto en casos muy específicos, recomiendo no usar esta función, ya que requiere revelar tu clave privada en un teléfono, lo cual es mucho más vulnerable a ataques cibernéticos que tu monedero hardware.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
¡Y ahí lo tienes, ahora sabes cómo configurar fácilmente un monedero de solo visualización en tu smartphone! Es una herramienta muy útil para monitorear un monedero en un monedero hardware sin tener que conectarlo y desbloquearlo cada vez.

Si encontraste útil este tutorial, te agradecería si pudieras dejar un pulgar hacia arriba abajo. Siéntete libre de compartir este artículo en tus redes sociales. ¡Muchas gracias!

También recomiendo revisar este tutorial completo sobre la aplicación Blockstream Green para configurar un monedero caliente:

https://planb.network/tutorials/wallet/blockstream-green