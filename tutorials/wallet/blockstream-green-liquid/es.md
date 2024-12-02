---
name: Blockstream Green - Liquid
description: Configuración de una cartera en la sidechain de Liquid Network
---
![cover](assets/cover.webp)
El protocolo de Bitcoin tiene limitaciones técnicas intencionales que ayudan a mantener la descentralización de la red y asegurar la distribución de la seguridad entre todos los usuarios. Sin embargo, estos límites a veces pueden frustrar a los usuarios, especialmente durante la congestión causada por un alto volumen de transacciones simultáneas. El debate sobre la escalabilidad de Bitcoin ha dividido a la comunidad durante mucho tiempo, particularmente durante la Guerra del Tamaño de Bloque. Desde ese episodio, es ampliamente reconocido dentro de la comunidad de Bitcoin que la escalabilidad debe asegurarse mediante soluciones fuera de la cadena, en sistemas de segunda capa. Entre estas soluciones están las sidechains, que aún son relativamente desconocidas y poco utilizadas en comparación con otros sistemas como la Lightning Network.

Una sidechain es una blockchain independiente que opera en paralelo a la blockchain principal de Bitcoin. Utiliza bitcoin como unidad de cuenta a través de un mecanismo llamado "*two-way peg*". Este sistema permite bloquear bitcoins en la cadena principal para replicar su valor en la sidechain, donde circulan como tokens respaldados por los bitcoins originales. Estos tokens normalmente mantienen una paridad de valor con los bitcoins bloqueados en la cadena principal, y el proceso puede revertirse para recuperar los fondos en Bitcoin.

El objetivo de las sidechains es ofrecer funcionalidades adicionales o mejoras técnicas, como transacciones más rápidas, tarifas reducidas o soporte para contratos inteligentes. Estas innovaciones no siempre pueden implementarse directamente en la blockchain de Bitcoin sin comprometer su descentralización o seguridad. Las sidechains permiten probar y explorar nuevas soluciones mientras se preserva la integridad de Bitcoin. Sin embargo, estos protocolos a menudo requieren compromisos, particularmente en términos de descentralización y seguridad, dependiendo del modelo de gobernanza y mecanismo de consenso elegidos.

Hoy en día, la sidechain más conocida es probablemente Liquid. En este tutorial, primero te presentaré qué es Liquid, y luego te guiaré sobre cómo comenzar a usarlo fácilmente a través de la aplicación Blockstream Green, para aprovechar sus beneficios.

![LIQUID GREEN](assets/fr/01.webp)

## ¿Qué es Liquid Network?

Liquid es una sidechain federada construida sobre Bitcoin, desarrollada por Blockstream, con el objetivo de mejorar la velocidad, privacidad y funcionalidades de las transacciones. Utiliza un mecanismo de anclaje bilateral establecido en una federación para bloquear bitcoins en la cadena principal y crear, a cambio, Liquid-bitcoins (L-BTC), tokens que circulan en Liquid mientras permanecen respaldados por los bitcoins originales.

![LIQUID GREEN](assets/fr/02.webp)
La red Liquid se basa en una federación de participantes, consistente en entidades reconocidas del ecosistema de Bitcoin, que validan bloques y gestionan el anclaje bilateral. Además de L-BTC, Liquid también permite la emisión de otros activos digitales, como stablecoins u otras criptomonedas.
![LIQUID GREEN](assets/fr/03.webp)

## Introducción a Blockstream Green

Blockstream Green es una cartera de software disponible para móviles y escritorio. Anteriormente conocida como *Green Address*, esta cartera se convirtió en un proyecto de Blockstream tras su adquisición en 2016.

Green es una aplicación que es particularmente fácil de usar, lo que la hace interesante para principiantes. Ofrece todas las características esenciales de una buena cartera de Bitcoin, incluyendo RBF (*Replace-by-Fee*), una opción para conectarse a través de Tor, la capacidad de conectar tu propio nodo, la opción SPV (*Simple Payment Verification*), etiquetado y control de monedas.

Blockstream Green también soporta la red Liquid, y eso es lo que vamos a explorar en este tutorial. Si deseas usar Green para otras aplicaciones, también recomiendo consultar estos otros tutoriales:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Instalación y Configuración de la Aplicación Blockstream Green

El primer paso es, naturalmente, descargar la aplicación Green. Ve a tu tienda de aplicaciones:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Para los usuarios de Android, también tienen la opción de instalar la aplicación a través del archivo `.apk` [disponible en el GitHub de Blockstream](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Inicia la aplicación, luego marca la casilla "*Acepto los términos...*".

![LIQUID GREEN](assets/fr/06.webp)

Cuando abres Green por primera vez, la pantalla de inicio aparece sin ninguna billetera configurada. Más tarde, si creas o importas billeteras, aparecerán en esta interfaz. Antes de pasar a crear una billetera, te aconsejo que ajustes la configuración de la aplicación según tus expectativas. Haz clic en "*Configuración de la Aplicación*".

![LIQUID GREEN](assets/fr/07.webp)

La opción "*Privacidad Mejorada*", disponible solo en Android, mejora la privacidad al deshabilitar las capturas de pantalla y ocultar las vistas previas de la aplicación. También bloquea automáticamente el acceso a la aplicación tan pronto como tu teléfono se bloquea, haciendo que tus datos sean más difíciles de exponer.
![LIQUID GREEN](assets/fr/08.webp)
Para aquellos que buscan mejorar su privacidad, la aplicación ofrece la opción de enrutar tu tráfico a través de Tor, una red que encripta todas tus conexiones y hace que tus actividades sean difíciles de rastrear. Aunque esta opción puede ralentizar ligeramente el rendimiento de la aplicación, se recomienda encarecidamente para proteger tu privacidad, especialmente si no estás usando tu propio nodo completo.

![LIQUID GREEN](assets/fr/09.webp)

Para los usuarios que tienen su propio nodo completo, Green Wallet te permite conectarte a él a través de un servidor Electrum, asegurando el control total sobre la información de la red Bitcoin y la transmisión de transacciones. Sin embargo, esta característica es relevante para las billeteras Bitcoin tradicionales, por lo que no la necesitas si estás usando Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Otra característica alternativa es la opción "*Verificación SPV*", que permite la verificación directa de ciertos datos de la blockchain, reduciendo así la necesidad de confiar en el nodo predeterminado de Blockstream, aunque este método no proporciona todas las garantías de un nodo completo. Nuevamente, esto solo concernirá a tus billeteras Bitcoin en cadena, y no a Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Una vez que estos ajustes estén configurados según tus necesidades, haz clic en el botón "*Guardar*" y reinicia la aplicación.

![LIQUID GREEN](assets/fr/12.webp)

## Creando una Billetera Liquid en Blockstream Green

Ahora estás listo para crear una billetera Liquid. Haz clic en el botón "*Comenzar*".

![LIQUID GREEN](assets/fr/13.webp)

Tienes la opción de crear una billetera de software localmente o gestionar una billetera fría a través de una billetera de hardware. Para este tutorial, nos centraremos en crear una billetera caliente en Liquid, por lo que necesitarás seleccionar la opción "*En Este Dispositivo*". También puedes usar una billetera de hardware compatible, como el Blockstream Jade, para asegurar tu billetera Liquid.

![LIQUID GREEN](assets/fr/14.webp)
Luego puedes elegir restaurar una cartera de Bitcoin existente o crear una nueva. Para los propósitos de este tutorial, crearemos una nueva cartera. Sin embargo, si necesitas regenerar una cartera Liquid existente a partir de su frase mnemotécnica, por ejemplo, debido a la pérdida de tu cartera de hardware, necesitarás elegir la segunda opción.
![LIQUID GREEN](assets/fr/15.webp)

Entonces tienes la opción entre una frase mnemotécnica de 12 palabras o una de 24 palabras. Esta frase te permitirá recuperar el acceso a tu cartera desde cualquier software compatible en caso de problemas con tu teléfono. Actualmente, optar por una frase de 24 palabras no ofrece más seguridad que una de 12 palabras. Por lo tanto, recomiendo elegir una frase mnemotécnica de **12 palabras**.
Green te proporcionará entonces tu frase mnemotécnica. Antes de continuar, asegúrate de no estar siendo observado. Haz clic en "*Mostrar frase de recuperación*" para mostrarla en la pantalla.
![LIQUID GREEN](assets/fr/16.webp)

**Esta frase mnemotécnica otorga acceso completo y sin restricciones a todos tus bitcoins.** Cualquiera en posesión de esta frase puede robar tus fondos, incluso sin acceso físico a tu teléfono.

Te permite restaurar el acceso a tus bitcoins en caso de pérdida, robo o daño a tu teléfono. Por lo tanto, es muy importante guardarla cuidadosamente **en un medio físico (no digital)** y almacenarla en un lugar seguro. Puedes escribirla en un pedazo de papel, o para más seguridad, si esta cartera es significativa, recomiendo grabarla en un medio de acero inoxidable para proteger contra los riesgos de incendios, inundaciones o colapsos (para una cartera caliente destinada a asegurar una pequeña cantidad de bitcoins, una copia de seguridad en papel simple probablemente sea suficiente).

*Obviamente, nunca debes compartir estas palabras en internet, al contrario de lo que estoy haciendo en este tutorial. Esta cartera de ejemplo se usará solo en el Liquid Testnet y se eliminará al final del tutorial.*

![LIQUID GREEN](assets/fr/17.webp)

Después de anotar correctamente tu frase mnemotécnica en un medio físico, haz clic en "*Continuar*". Green Wallet te pedirá entonces que confirmes algunas palabras de tu frase para verificar que las has registrado correctamente. Rellena los espacios en blanco con las palabras faltantes.

![LIQUID GREEN](assets/fr/18.webp)

Elige el código PIN para tu dispositivo, que se utilizará para desbloquear tu cartera Green. Por lo tanto, es una protección contra el acceso físico no autorizado. Este código PIN no juega un papel en la derivación de las claves criptográficas de tu cartera. Así, incluso sin acceso a este código PIN, la posesión de tu frase mnemotécnica de 12 o 24 palabras te permitirá recuperar el acceso a tus bitcoins.

Se recomienda elegir un código PIN de 6 dígitos tan aleatorio como sea posible. Además, asegúrate de guardar este código para no olvidarlo, de lo contrario, te verás obligado a recuperar tu cartera desde la frase mnemotécnica. Más tarde, puedes añadir una opción de bloqueo biométrico para evitar ingresar el PIN cada vez que lo uses. En términos generales, la biometría es mucho menos segura que el propio PIN. Por lo tanto, por defecto, aconsejo no configurar esta opción de desbloqueo.

![LIQUID GREEN](assets/fr/19.webp)

Ingresa tu PIN una segunda vez para confirmarlo.

![LIQUID GREEN](assets/fr/20.webp)
Espera a que se cree tu cartera, luego haz clic en el botón "*Crear una cuenta*".
![LIQUID GREEN](assets/fr/21.webp)
En el cuadro de "*Activos*", selecciona "*Liquid Bitcoin*". Luego tienes la opción entre una billetera de firma única estándar, que utilizaremos en este tutorial, o una billetera protegida por autenticación de dos factores (2FA).
![LIQUID GREEN](assets/fr/22.webp)

¡Y ahí lo tienes, tu billetera Liquid ha sido creada exitosamente usando la aplicación Green!

![LIQUID GREEN](assets/fr/23.webp)

Antes de recibir tus primeros bitcoins en tu billetera Liquid, **te aconsejo encarecidamente realizar una prueba de recuperación en vacío**. Anota una información de referencia, como tu xpub o la primera dirección de recepción, luego elimina tu billetera en la aplicación Green mientras aún está vacía. A continuación, intenta restaurar tu billetera en Green usando tus respaldos en papel. Verifica que la información de testigo generada después de la restauración coincida con la que inicialmente anotaste. Si es así, puedes estar seguro de que tus respaldos en papel son confiables. Para aprender más sobre cómo realizar una prueba de recuperación, te aconsejo consultar este otro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Configurando tu Billetera Liquid

Si deseas personalizar tu billetera, haz clic en los tres pequeños puntos en la parte superior derecha.

![LIQUID GREEN](assets/fr/24.webp)

La opción "*Renombrar*" te permite personalizar el nombre de tu billetera, lo cual es particularmente útil si manejas múltiples billeteras en la misma aplicación.

![LIQUID GREEN](assets/fr/25.webp)

El menú "*Unidad*" te da la opción de cambiar la unidad base de tu billetera. Por ejemplo, puedes elegir mostrarla en satoshis en lugar de en bitcoins.

![LIQUID GREEN](assets/fr/26.webp)

El menú "*Configuración*" proporciona acceso a las diferentes opciones de tu billetera Bitcoin.

![LIQUID GREEN](assets/fr/27.webp)

Aquí encontrarás, por ejemplo, tu *descriptor*, que puede ser útil si planeas configurar una billetera de solo visualización desde esta billetera Liquid.

![LIQUID GREEN](assets/fr/28.webp)

También puedes cambiar el código PIN de tu billetera y habilitar el inicio de sesión biométrico.

![LIQUID GREEN](assets/fr/29.webp)

## Usando tu Billetera Liquid

Ahora que tu billetera Liquid está configurada, ¡estás listo para recibir tus primeros L-sats!
Si aún no posees L-BTC, hay varias opciones disponibles para ti. La primera es que te lo envíen directamente. Si alguien quiere pagarte en bitcoins en Liquid, simplemente dáles una dirección de recepción. La otra solución es intercambiar tus bitcoins en cadena o aquellos en la red Lightning por L-BTC. Para hacer esto, puedes usar [un puente como Boltz](https://boltz.exchange/). Solo ingresa tu dirección Liquid en el sitio, luego realiza el pago ya sea a través de la red Lightning o en cadena.
![LIQUID GREEN](assets/fr/30.webp)

Para generar una dirección Liquid, haz clic en el botón "*Recibir*".

![LIQUID GREEN](assets/fr/31.webp)

Green mostrará entonces la primera dirección de recepción en blanco de tu billetera. Puedes escanear el código QR asociado o copiar la dirección directamente para enviar L-BTC a ella.

![LIQUID GREEN](assets/fr/32.webp)

Cuando la transacción se difunda en la red, aparecerá en tu billetera.

![LIQUID GREEN](assets/fr/33.webp)

Espera a obtener suficientes confirmaciones para considerar la transacción como final. En Liquid, las confirmaciones deberían ser rápidas, ya que un bloque se publica cada minuto.

![LIQUID GREEN](assets/fr/34.webp)
Con L-sats en tu billetera Liquid, ahora también puedes enviarlos. Haz clic en "*Enviar*".
![LIQUID GREEN](assets/fr/35.webp)

En la siguiente página, ingresa la dirección Liquid del destinatario. Puedes introducirla manualmente o escanear su código QR.

![LIQUID GREEN](assets/fr/36.webp)

Elige la cantidad del pago.

![LIQUID GREEN](assets/fr/37.webp)

Haz clic en "*Siguiente*" para acceder a una pantalla resumen de tu transacción. Verifica que la dirección, cantidad y comisiones sean correctas.

![LIQUID GREEN](assets/fr/38.webp)

Si todo te parece correcto, desliza el botón verde en la parte inferior de la pantalla hacia la derecha para firmar y transmitir la transacción en la red Bitcoin.

![LIQUID GREEN](assets/fr/39.webp)

Tu transacción ahora aparecerá en el tablero de tu billetera Bitcoin pendiente de confirmación.

![LIQUID GREEN](assets/fr/40.webp)

Y ahí lo tienes, ¡ahora sabes cómo usar fácilmente la sidechain Liquid con la aplicación Blockstream Green!

Si encontraste útil este tutorial, agradecería mucho un pulgar hacia arriba abajo. No dudes en compartir este artículo en tus redes sociales. ¡Muchas gracias!

También te recomiendo descubrir este otro tutorial completo sobre la aplicación móvil Blockstream Green para configurar una billetera caliente de Bitcoin onchain:

https://planb.network/tutorials/wallet/blockstream-green