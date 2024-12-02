---
name: Aqua
description: Bitcoin, Lightning y Liquid en una sola billetera
---
![cover](assets/cover.webp)

Aqua es una aplicación móvil que permite la creación fácil de una billetera caliente (hot wallet) para Bitcoin y Liquid, y también ofrece la posibilidad de usar Lightning sin la complejidad de gestionar un nodo, gracias a los intercambios integrados. También soporta la gestión de stablecoins USDT a través de varias redes.

Desarrollada por la compañía JAN3 bajo el liderazgo de Samson Mow, la aplicación Aqua fue diseñada inicialmente específicamente para las necesidades de los usuarios en América Latina, aunque es adecuada para cualquier usuario en todo el mundo. Es particularmente interesante para principiantes y aquellos que usan Bitcoin diariamente para sus pagos.

En este tutorial, exploraremos cómo usar las muchas características de Aqua. Pero antes de eso, tomemos un momento para entender qué es una sidechain en Bitcoin y cómo funciona Liquid, lo que nos permitirá comprender plenamente el interés de Aqua.

![AQUA](assets/fr/01.webp)

## ¿Qué es una sidechain?

El protocolo de Bitcoin tiene limitaciones técnicas intencionales que ayudan a mantener la descentralización de la red y asegurar una distribución de seguridad entre todos los usuarios. Sin embargo, estos límites a veces pueden frustrar a los usuarios, especialmente durante la congestión causada por un alto volumen de transacciones simultáneas. El debate sobre la escalabilidad de Bitcoin ha dividido a la comunidad durante mucho tiempo, particularmente durante la Guerra del Tamaño de Bloque. Desde ese episodio, es ampliamente reconocido dentro de la comunidad de Bitcoin que la escalabilidad debe asegurarse mediante soluciones fuera de la cadena, en sistemas de segunda capa. Entre estas soluciones están las sidechains, que aún son relativamente desconocidas y poco utilizadas en comparación con otros sistemas como la Red Lightning.

Una sidechain es una blockchain independiente que opera en paralelo a la blockchain principal de Bitcoin. Utiliza bitcoin como una unidad de cuenta a través de un mecanismo llamado "*two-way peg*". Este sistema permite bloquear bitcoins en la cadena principal para replicar su valor en la sidechain, donde circulan como tokens respaldados por los bitcoins originales. Estos tokens normalmente mantienen una paridad de valor con los bitcoins bloqueados en la cadena principal, y el proceso puede revertirse para recuperar los fondos en Bitcoin.
El objetivo de las sidechains es ofrecer funcionalidades adicionales o mejoras técnicas, como transacciones más rápidas, tarifas reducidas o soporte para contratos inteligentes. Estas innovaciones no siempre pueden implementarse directamente en la blockchain de Bitcoin sin comprometer su descentralización o seguridad. Las sidechains permiten probar y explorar nuevas soluciones mientras se preserva la integridad de Bitcoin. Sin embargo, estos protocolos a menudo requieren compromisos, particularmente en términos de descentralización y seguridad, dependiendo del modelo de gobernanza y mecanismo de consenso elegidos.
## ¿Qué es Liquid?

Liquid es una sidechain federada construida sobre Bitcoin, desarrollada por Blockstream, con el objetivo de mejorar la velocidad, privacidad y funcionalidades de las transacciones. Utiliza un mecanismo de anclaje bilateral establecido en una federación para bloquear bitcoins en la cadena principal y crear a cambio Liquid-bitcoins (L-BTC), tokens que circulan en Liquid mientras permanecen respaldados por los bitcoins originales.

![AQUA](assets/fr/02.webp)

La red Liquid se basa en una federación de participantes, compuesta por entidades reconocidas del ecosistema de Bitcoin, que validan los bloques y gestionan el anclaje bilateral. Además de L-BTC, Liquid también permite la emisión de otros activos digitales, como la stablecoin USDT u otras criptomonedas.

![AQUA](assets/fr/03.webp)

## Instalando la App Aqua

El primer paso es, naturalmente, descargar la app Aqua. Ve a tu tienda de aplicaciones:
- [Para Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Para Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
Para los usuarios de Android, también tienen la opción de instalar la aplicación a través del archivo `.apk` [disponible en su GitHub](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Inicia la aplicación, luego marca la casilla "*He leído y aceptado los Términos de Servicio y la Política de Privacidad*".

![AQUA](assets/fr/06.webp)

## Creando Tu Cartera en Aqua

Haz clic en el botón "*Crear Cartera*".

![AQUA](assets/fr/07.webp)

¡Y ahí lo tienes, tu cartera ya está creada!

![AQUA](assets/fr/08.webp)

Pero antes que nada, dado que esta es una cartera de auto-custodia, es imperativo hacer una copia de seguridad física de tu frase mnemotécnica. **Esta frase mnemotécnica proporciona acceso completo y sin restricciones a todos tus bitcoins**. Cualquiera en posesión de esta frase puede robar tus fondos, incluso sin acceso físico a tu teléfono.
Te permite restaurar el acceso a tus bitcoins en caso de pérdida, robo o daño a tu teléfono. Por lo tanto, es muy importante respaldarla cuidadosamente en un medio físico (no digital) y almacenarla en un lugar seguro. Puedes escribirla en un pedazo de papel, o para más seguridad, si esta cartera es significativa, recomiendo grabarla en un medio de acero inoxidable para proteger contra los riesgos de incendios, inundaciones o colapsos (para una cartera caliente destinada a asegurar una pequeña cantidad de bitcoins, una simple copia de seguridad en papel probablemente sea suficiente).
Para hacer esto, haz clic en el menú de configuración.

![AQUA](assets/fr/09.webp)

Luego haz clic en "*Ver Frase Semilla*". Haz una copia de seguridad física de esta frase de 12 palabras.

![AQUA](assets/fr/10.webp)

En este mismo menú de configuración, también puedes cambiar el idioma de la aplicación así como la moneda fiat utilizada.

![AQUA](assets/fr/11.webp)

Antes de recibir tus primeros bitcoins en tu cartera, **te aconsejo encarecidamente realizar una prueba de recuperación en seco**. Anota una información de referencia, como tu xpub o la primera dirección de recepción, luego elimina tu cartera en la aplicación Aqua mientras aún está vacía. A continuación, intenta restaurar tu cartera en Aqua usando tus copias de seguridad en papel. Comprueba que la información de testigo generada después de la restauración coincide con la que inicialmente anotaste. Si este es el caso, puedes estar seguro de que tus copias de seguridad en papel son fiables. Para aprender más sobre cómo realizar una prueba de recuperación, te aconsejo que consultes este otro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Recibiendo bitcoins en Aqua

Ahora que tu cartera está configurada, ¡estás listo para recibir tus primeros sats! Simplemente haz clic en el botón "*Recibir*" en el menú "*Cartera*".

![AQUA](assets/fr/12.webp)

Puedes elegir recibir bitcoins onchain, en Liquid o vía Lightning.

![AQUA](assets/fr/13.webp)

Para transacciones onchain, Aqua generará una dirección de recepción específica donde puedes recibir tus sats.

![AQUA](assets/fr/14.webp)

De manera similar, al optar por Liquid, Aqua te proporcionará una dirección Liquid.

![AQUA](assets/fr/15.webp)

Si prefieres recibir fondos vía Lightning, primero necesitarás especificar la cantidad deseada.

![AQUA](assets/fr/16.webp)

Luego, haz clic en "*Generar Factura*".

![AQUA](assets/fr/17.webp)
Aqua creará una factura para recibir fondos desde una cartera Lightning. Es importante notar que, a diferencia de las opciones onchain y Liquid, los fondos recibidos vía Lightning serán automáticamente convertidos a L-BTC en Liquid usando la herramienta Boltz, ya que Aqua no es un nodo Lightning. Este proceso te permite recibir y enviar fondos vía Lightning, pero sin mantener tus bitcoins en Lightning. ![AQUA](assets/fr/18.webp)

Personalmente, comenzaré enviando bitcoins vía Lightning a Aqua. Una vez que la transacción se completa con la factura proporcionada, se recibe una confirmación.

![AQUA](assets/fr/19.webp)

Para seguir el progreso del intercambio, regresa a la página principal de tu cartera y haz clic en la cuenta "*L2 Bitcoin*", que lista las transacciones de Lightning (vía intercambio) y Liquid.

![AQUA](assets/fr/20.webp)

Aquí, puedes ver tu transacción así como tu saldo en L-BTC.

![AQUA](assets/fr/21.webp)

## Intercambiando bitcoins con Aqua

Ahora que tienes activos en tu cartera Aqua, tienes la opción de intercambiarlos directamente desde la aplicación, ya sea para transferirlos a la blockchain principal de Bitcoin o a Liquid. También puedes convertir tus bitcoins en la stablecoin USDT (u otras). Para hacer esto, accede al menú "*Marketplace*".

![AQUA](assets/fr/22.webp)

Haz clic en "*Swaps*".

![AQUA](assets/fr/23.webp)

En el cuadro "*Transfer from*", elige el activo que quieres intercambiar. Actualmente, solo tengo L-BTC, así que eso es lo que selecciono.

![AQUA](assets/fr/24.webp)

En el cuadro "*Transfer to*", elige el activo objetivo de tu intercambio. Por mi parte, opté por USDT en la red Liquid.

![AQUA](assets/fr/25.webp)

Ingresa la cantidad que deseas convertir.

![AQUA](assets/fr/26.webp)

Confirma haciendo clic en "*Continue*".

![AQUA](assets/fr/27.webp)

Asegúrate de que los ajustes del intercambio sean de tu agrado, luego confirma deslizando el botón "*Swap*" en la parte inferior de la pantalla.

![AQUA](assets/fr/28.webp)

Tu intercambio ahora está confirmado.

![AQUA](assets/fr/29.webp)

Si volvemos a nuestra cartera, podemos ver que ahora tenemos USDT en Liquid.

![AQUA](assets/fr/30.webp)

## Enviando bitcoins con Aqua

Ahora que tienes bitcoins en tu cartera Aqua, tienes la opción de enviarlos. Haz clic en el botón "*Send*".

![AQUA](assets/fr/31.webp)

Elige el activo que quieres enviar o selecciona la red para realizar la transacción. Por mi parte, enviaré bitcoins vía Lightning.

![AQUA](assets/fr/32.webp)
A continuación, ingresa la información necesaria para enviar el pago: para Bitcoin onchain o Liquid, necesitas ingresar una dirección de recepción; para Lightning, se requiere una factura. Puedes pegar esta información directamente en el campo designado o usar el icono de código QR para abrir tu cámara y escanear la dirección o factura. Luego haz clic en "*Continue*".
![AQUA](assets/fr/33.webp)

Haz clic en "*Continue*" nuevamente si toda la información parece correcta.

![AQUA](assets/fr/34.webp)
Aqua te presenta entonces un resumen de la transacción. Asegúrate de que toda la información sea correcta, especialmente la dirección de destino, las comisiones y el monto. Para confirmar la transacción, desliza el botón "*Deslizar para enviar*" ubicado en la parte inferior de la pantalla.
![AQUA](assets/fr/35.webp)

Luego se te proporciona una confirmación del envío.

![AQUA](assets/fr/36.webp)

Y ahí lo tienes, ahora sabes cómo usar la aplicación Aqua para recibir y gastar fondos en Bitcoin, Lightning y Liquid, todo desde una sola interfaz.

Si encontraste útil este tutorial, te agradecería mucho si pudieras dejar un pulgar hacia arriba abajo. Siéntete libre de compartir este artículo en tus redes sociales. ¡Muchas gracias!

También te aconsejo que revises este otro tutorial completo sobre la aplicación móvil Blockstream Green, que es otra solución interesante para configurar tu billetera Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid