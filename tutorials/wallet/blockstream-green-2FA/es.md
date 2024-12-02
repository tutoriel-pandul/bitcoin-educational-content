---
name: Blockstream Green - 2FA
description: Configuración de un multisig 2/2 en Green Wallet
---
![cover](assets/cover.webp)

Una billetera de software es una aplicación instalada en una computadora, smartphone u otro dispositivo conectado a Internet, que permite la gestión y seguridad de las llaves de una billetera Bitcoin. A diferencia de las billeteras de hardware, que aíslan las llaves privadas, las billeteras "calientes" operan en un entorno potencialmente expuesto a ciberataques, aumentando los riesgos de hackeo y robo.

Las billeteras de software deben usarse para manejar cantidades razonables de bitcoins, especialmente para transacciones diarias. Esto también puede ser una opción interesante para personas con un portafolio limitado de Bitcoin, para quienes invertir en una billetera de hardware puede parecer desproporcionado. Sin embargo, su constante exposición a Internet las hace menos seguras para almacenar tus ahorros a largo plazo o fondos significativos. Para estos casos, es preferible optar por soluciones más seguras, como las billeteras de hardware.

En este tutorial, te mostraré cómo mejorar la seguridad de una billetera caliente utilizando la opción "2FA" en Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Introducción a Blockstream Green

Blockstream Green es una billetera de software disponible para móviles y escritorio. Anteriormente conocida como *Green Address*, esta billetera se convirtió en un proyecto de Blockstream tras su adquisición en 2016.

Green es una aplicación que es particularmente fácil de usar, lo que la hace interesante para principiantes. Ofrece todas las características esenciales de una buena billetera Bitcoin, incluyendo RBF (*Replace-by-Fee*), una opción para conectarse a través de Tor, la capacidad de conectar tu propio nodo, la opción SPV (*Simple Payment Verification*), etiquetado y control de monedas.

Blockstream Green también soporta la red Liquid, una sidechain de Bitcoin desarrollada por Blockstream para realizar transacciones rápidas y confidenciales fuera de la blockchain principal. En este tutorial, nos enfocamos exclusivamente en Bitcoin, pero también he hecho otro tutorial para aprender a usar Liquid en Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## La opción multisig 2/2 (2FA)

En Green, ciertamente puedes crear una billetera caliente "singlesig" clásica. Pero también tienes la opción "2FA multisig", que te permite mejorar la seguridad de tu billetera caliente sin complicar demasiado su gestión diaria.
Por lo tanto, configurarás una billetera multisig 2/2, lo que significa que cada transacción requerirá la firma de dos llaves. La primera llave, derivada de tu frase mnemónica de 12 o 24 palabras, está asegurada localmente con un código PIN en tu teléfono. Tienes control total sobre esta llave. La segunda llave la tienen los servidores de Blockstream, y su uso para firmar requiere autenticación, que se puede lograr a través de un código recibido por correo electrónico, SMS, llamada telefónica o, como veremos en este tutorial, a través de una aplicación de autenticación (Authy, Google Authenticator, etc.).

Para asegurar tu autonomía en caso de un fallo de Blockstream (por ejemplo, si la compañía quiebra o los servidores que sostienen la segunda llave se destruyen), se aplica un mecanismo de timelock a tu multisig. Este mecanismo transforma el multisig 2/2 en un multisig 1/2 después de aproximadamente un año (o precisamente 51,840 bloques, pero este valor puede cambiarse), después de lo cual tu billetera solo necesitará tu llave local para gastar los bitcoins. Así, si pierdes acceso a los servidores de Blockstream o a la autenticación 2FA, solo necesitas esperar hasta un año para poder usar libremente tus bitcoins con tu aplicación, sin depender de Blockstream.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Este método incrementa significativamente la seguridad de tu monedero caliente, mientras te deja en control de tus bitcoins y facilita su uso diario. Sin embargo, requiere refrescar regularmente el timelock para mantener la seguridad del 2FA. La cuenta regresiva de 360 días, durante la cual tus fondos están protegidos por el 2FA, comienza tan pronto como recibes bitcoins. Si, 360 días después de recibirlos, no has realizado una transacción gastando esos fondos, tus bitcoins solo estarán protegidos por tu llave local, sin el 2FA.

Esta restricción hace que la opción de 2FA sea más adecuada para un monedero de gastos, donde las transacciones regulares renuevan automáticamente los timelocks. Para un monedero de ahorros a largo plazo, esto puede ser problemático, ya que necesitarás pensar en realizar una transacción de barrido a ti mismo cada año antes de que el timelock expire.

Otro inconveniente de este método de seguridad es que necesitarás usar patrones de script minoritarios. Esto significa que, desde el punto de vista de la privacidad, las cosas se complican: muy pocas personas usan el mismo tipo de script que tú, permitiendo a un observador externo identificar más fácilmente la huella de tu monedero. Además, estos scripts resultarán en tarifas de transacción más altas debido a su mayor tamaño.
Si prefieres no usar la opción de 2FA y simplemente quieres configurar un monedero "singlesig" en Green, te invito a consultar este otro tutorial:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Instalando y Configurando el Software Blockstream Green

El primer paso es naturalmente descargar la aplicación Green. Ve a tu tienda de aplicaciones:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Para usuarios de Android, también tienen la opción de instalar la aplicación a través del archivo `.apk` [disponible en GitHub de Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Inicia la aplicación, luego marca la casilla "*Acepto los términos...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Cuando abres Green por primera vez, la pantalla de inicio aparece sin ningún monedero configurado. Más tarde, si creas o importas monederos, aparecerán en esta interfaz. Antes de pasar a crear un monedero, te aconsejo ajustar la configuración de la aplicación según tus expectativas. Haz clic en "*Configuración de la Aplicación*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

La opción "*Privacidad Mejorada*", disponible solo en Android, mejora la privacidad al deshabilitar capturas de pantalla y ocultar vistas previas de la aplicación. También bloquea automáticamente el acceso a la aplicación tan pronto como tu teléfono se bloquea, haciendo que tus datos sean más difíciles de exponer.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Para aquellos que deseen mejorar su privacidad, la aplicación ofrece enrutamiento de tu tráfico a través de Tor, una red que encripta todas tus conexiones y hace que tus actividades sean difíciles de rastrear. Aunque esta opción puede ralentizar ligeramente el rendimiento de la aplicación, se recomienda encarecidamente para proteger tu privacidad, especialmente si no estás usando tu propio nodo completo.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Para usuarios que tienen su propio nodo completo, Green Wallet ofrece la posibilidad de conectarse a él a través de un servidor Electrum, asegurando el control total sobre la información de la red Bitcoin y la transmisión de transacciones.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Otra característica alternativa es la opción de "*Verificación SPV*", que permite la verificación directa de ciertos datos de la blockchain, reduciendo así la necesidad de confiar en el nodo predeterminado de Blockstream, aunque este método no proporciona todas las garantías de un nodo completo.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Una vez que estos ajustes se hayan modificado según tus necesidades, haz clic en el botón "*Guardar*" y reinicia la aplicación.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Creando una Cartera de Bitcoin en Blockstream Green

Ahora estás listo para crear una cartera de Bitcoin. Haz clic en el botón "*Comenzar*".

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Tienes la opción de crear una cartera de software localmente o gestionar una cartera fría a través de una cartera de hardware. Para este tutorial, nos centraremos en crear una cartera caliente, por lo que necesitarás seleccionar la opción "*En este dispositivo*".

![GREEN 2FA MULTISIG](assets/fr/13.webp)

A continuación, puedes elegir restaurar una cartera de Bitcoin existente o crear una nueva. Para los propósitos de este tutorial, crearemos una nueva cartera. Sin embargo, si necesitas regenerar una cartera de Bitcoin existente a partir de su frase mnemotécnica, por ejemplo, debido a la pérdida de tu antiguo teléfono, necesitarás elegir la segunda opción.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Luego tienes la opción entre una frase mnemotécnica de 12 palabras o de 24 palabras. Esta frase te permitirá recuperar el acceso a tu cartera desde cualquier software compatible en caso de problemas con tu teléfono. Actualmente, optar por una frase de 24 palabras no ofrece más seguridad que una frase de 12 palabras. Por lo tanto, recomiendo elegir una frase mnemotécnica de **12 palabras**.

Green te proporcionará entonces tu frase mnemotécnica. Antes de continuar, asegúrate de no estar siendo observado. Haz clic en "*Mostrar frase de recuperación*" para mostrarla en la pantalla.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Esta frase mnemotécnica otorga acceso completo y sin restricciones a todos tus bitcoins**. Cualquiera en posesión de esta frase puede robar tus fondos, incluso sin acceso físico a tu teléfono (bajo condiciones de timelock expirado o 2FA en el caso de una cartera 2/2 en Green).

Te permite restaurar el acceso a tus claves locales en caso de pérdida, robo o daño a tu teléfono. Por lo tanto, es muy importante guardarla cuidadosamente **en un medio físico (no digital)** y almacenarla en un lugar seguro. Puedes anotarla en un pedazo de papel, o para más seguridad, si esta cartera es importante, recomiendo grabarla en un medio de acero inoxidable para proteger contra los riesgos de incendios, inundaciones o derrumbes (para una cartera caliente destinada a asegurar una pequeña cantidad de bitcoins, una simple copia de seguridad en papel probablemente sea suficiente).
*Obviamente, nunca debes compartir estas palabras en internet, a diferencia de lo que estoy haciendo en este tutorial. Esta cartera de ejemplo se utilizará solo en la Testnet y se eliminará al final del tutorial.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Después de anotar correctamente tu frase mnemotécnica en un medio físico, haz clic en "*Continuar*". Green Wallet te pedirá entonces que confirmes algunas palabras de tu frase para verificar que las has registrado correctamente. Rellena los espacios en blanco con las palabras faltantes.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Elige el código PIN para tu dispositivo, que se utilizará para desbloquear tu billetera Green. Por lo tanto, es una protección contra el acceso físico no autorizado. Este código PIN no juega un papel en la derivación de las claves criptográficas de tu billetera. Así, incluso sin acceso a este código PIN, la posesión de tu frase mnemotécnica de 12 o 24 palabras te permitirá recuperar el acceso a tus claves locales.
Se recomienda elegir un código PIN de 6 dígitos tan aleatorio como sea posible. Además, asegúrate de guardar este código para no olvidarlo, de lo contrario, te verás obligado a recuperar tu billetera desde la frase mnemotécnica. Más tarde puedes añadir una opción para el bloqueo biométrico para evitar ingresar el PIN cada vez. En términos generales, la biometría es mucho menos segura que el propio PIN. Por lo tanto, por defecto, aconsejo no configurar esta opción de desbloqueo.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Ingresa tu PIN una segunda vez para confirmarlo.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Espera mientras se crea tu billetera, luego haz clic en el botón "*Crear una cuenta*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Luego tienes la opción entre una billetera de firma única estándar o una billetera protegida por autenticación de dos factores (2FA). En este tutorial, elegiremos la segunda opción.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

¡Y ahí lo tienes, tu billetera multisig de Bitcoin ha sido creada exitosamente usando la aplicación Green!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Configuración de 2FA

Haz clic en tu cuenta.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Haz clic en el botón verde "*Aumenta la seguridad de tu cuenta añadiendo 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Luego tendrás la opción de elegir el método de autenticación para acceder a la segunda clave de tu multisig 2/2. Para este tutorial, usaremos una aplicación de autenticación. Si no estás familiarizado con este tipo de aplicación, recomiendo consultar nuestro tutorial sobre Authy:
https://planb.network/tutorials/others/authy

Selecciona "*Aplicación Autenticadora*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green mostrará entonces un código QR y una clave de recuperación. Esta clave te permite restaurar el acceso a tu 2FA en caso de que pierdas tu aplicación Authy. Se recomienda hacer una copia de seguridad segura de esta clave, aunque siempre puedes recuperar el acceso a tus bitcoins después de la expiración del bloqueo de tiempo, como se explicó anteriormente.

En tu aplicación de autenticación, añade un nuevo código, luego escanea el código QR proporcionado por Green.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Obviamente, nunca deberías compartir esta clave y código QR en internet, al contrario de lo que estoy haciendo en este tutorial. Esta billetera de ejemplo se utilizará solo en el Testnet y se eliminará al final del tutorial.*

Haz clic en el botón "*Continuar*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Ingresa el código dinámico de 6 dígitos presente en tu aplicación de autenticación.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

La autenticación de dos factores está ahora habilitada.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Al navegar por este menú, también puedes ajustar la duración del bloqueo temporal. Esta cuenta regresiva comienza al recibir bitcoins, y una vez que el bloqueo temporal expira, tus fondos pueden ser gastados solo con tu llave local, sin requerir la autenticación de dos factores (2FA). La duración predeterminada está establecida en 12 meses, pero para una cartera de ahorros, elegir 15 meses puede ser prudente para minimizar la frecuencia de renovaciones del bloqueo temporal. Por el contrario, para una cartera de gastos, un bloqueo temporal de 6 meses puede ser preferible, ya que se renovará frecuentemente con tus transacciones diarias, y un bloqueo temporal más corto reduce la espera en caso de problemas con el 2FA. Depende de ti determinar la duración del bloqueo temporal que mejor se adapte a tus necesidades.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Ahora puedes salir de este menú. ¡Tu cartera multisig está lista!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Configurando tu cartera en Blockstream Green

Si deseas personalizar tu cartera, haz clic en los tres pequeños puntos en la parte superior derecha.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
La opción "*Rename*" te permite personalizar el nombre de tu cartera, lo cual es particularmente útil si gestionas múltiples carteras en la misma aplicación.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

El menú "*Unit*" te da la opción de cambiar la unidad base de tu cartera. Por ejemplo, puedes elegir mostrarla en satoshis en lugar de en bitcoins.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

El menú "*Settings*" proporciona acceso a las diferentes opciones de tu cartera Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Aquí, por ejemplo, encontrarás tu clave pública extendida y su *descriptor*, útil si planeas configurar una cartera de solo visualización a partir de esta cartera.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

También puedes cambiar el código PIN de tu cartera y habilitar el inicio de sesión biométrico.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Usando Blockstream Green

Ahora que tu cartera Bitcoin está configurada, ¡estás listo para recibir tus primeros sats! Para hacerlo, simplemente haz clic en el botón "*Receive*".

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green mostrará entonces la primera dirección de recepción en blanco de tu cartera. Puedes escanear el código QR asociado o copiar la dirección directamente para enviar bitcoins a ella. Este tipo de dirección no especifica la cantidad a ser enviada por el pagador. Sin embargo, puedes generar una dirección que solicite una cantidad específica, haciendo clic en los tres pequeños puntos en la parte superior derecha, luego en "*Request Amount*", e ingresando la cantidad deseada.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Cuando la transacción se transmita en la red, aparecerá en tu cartera.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Espera a obtener suficientes confirmaciones para considerar la transacción como final.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Con bitcoins en tu cartera, ahora también puedes enviarlos. Haz clic en "*Send*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

En la página siguiente, ingresa la dirección del destinatario. Puedes ingresarla manualmente o escanear un código QR.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Elige la cantidad de pago.
![GREEN 2FA MULTISIG](assets/fr/44.webp)En la parte inferior de la pantalla, puedes seleccionar la tasa de comisión para esta transacción. Tienes la opción de seguir las recomendaciones de la aplicación o personalizar tus comisiones. Cuanto más altas sean las comisiones en comparación con otras transacciones pendientes, más rápido se procesará tu transacción. Para entender el mercado de comisiones, puedes visitar [Mempool.space](https://mempool.space/) en la sección "*Transaction Fees*".

![GREEN 2FA MULTISIG](assets/fr/45.webp)

Haz clic en "*Next*" para acceder a una pantalla resumen de tu transacción. Verifica que la dirección, cantidad y comisiones sean correctas.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Si todo te parece correcto, desliza el botón verde en la parte inferior de la pantalla hacia la derecha para firmar y transmitir la transacción en la red Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Este es el momento en el que necesitas ingresar tu código de autenticación para desbloquear la segunda llave del multisig mantenida por Blockstream. Ingresa el código de 6 dígitos mostrado en tu aplicación de autenticación.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Tu transacción ahora aparecerá en el tablero de tu billetera Bitcoin esperando confirmación.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

¡Y ahí lo tienes, ahora sabes cómo configurar fácilmente una billetera multisig 2/2 usando la opción 2FA de Blockstream Green!

Si encontraste útil este tutorial, te agradecería si pudieras dejar un pulgar verde abajo. Siéntete libre de compartir este artículo en tus redes sociales. ¡Muchas gracias!

También recomiendo revisar este otro tutorial completo sobre la aplicación móvil Blockstream Green para configurar una billetera Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid