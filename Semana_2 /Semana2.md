# Portafolio de evidencias.

## Semana 2.

Solidity
Solidity es un lenguaje de alto nivel orientado a contratos. Su sintaxis es similar a la de JavaScript y está enfocado específicamente a la Máquina Virtual de Etehreum (EVM). Solidity está tipado de manera estática y acepta, entre otras cosas, herencias, librerías y tipos complejos definidos por el usuario.

COMPILADOR
Remix es una herramienta online para crear smatrt contracts https://remix.ethereum.org/

Tipos de datos
int | uint <8-256>: Son números enteros, que pueden ser sin signo o con signo, y que pueden tener una capacidad de 8 a 256 bits.
bool: Verdadero o flaso
address: Guarda direcciones de ETH de 160 bits (20 bytes), y puede tener métodos extra como .transfer o .balance
string: Cadena de texto
bytes<8-256>: Cadena de bytes

Tipos de variables
Variables locales: Son aquellas que ocurren durante la ejecución. En la EVM es la parte correspondiente a memoria volátil
Variables de estado: Son variables que se almacenan en la parte de la ROM de la EVM. Es memoria persistente

Variables globales
msg: Toda transacción es un mensaje firmado. En este objeto vienen los datos de dicho mensaje (sender, value, etc.)
tx: Represena la transacción, es distitna respecto a msg porque cosas como el sender van variando conforme se concatenan llamadas entre contratos
block: Información respecto al bloque



