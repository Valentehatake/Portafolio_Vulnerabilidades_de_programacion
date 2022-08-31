# Portafolio de evidencias.

## Semana 7.
Manejo de dependencias y librerías

Importar una dependencia

   Con la sentencia “import” podemos hacer referencia a un contrato que esté definido en el mismo ámbito en el que estemos trabajando.
   También podemos importar contratos que se encuentren en un repositorio o en un paquete como npm.
   Además de contratos podemos importar librerías que son similares a los contratos, pero no contienen estado y solo brindan utilidad.
      
      // SPDX-License-Identifier: GPL-3.0

       pragma solidity >=0.7.0 <0.9.0;

    import "@openzeppelin/contracts/utils/math/SafeMath.sol";

    contract Importacion {
    
    function sumarNumeros(uint numero1, uint numero2) public pure returns (uint) {
        return SafeMath.add(numero1,numero2);
    }
    
    }

Herencia

Es la habilidad de usar la lógica escrita en otros contratos en nuestro propio contrato. Se hace por medio de la palabra is:
Si un contrato tiene un constructor con parámetros debemos indicar qué valores debe tomar ese constructor para poder derivarse.
.
Override

Podemos definir funciones del tipo virtual para indicar que pueden ser redefinidas en sus contratos derivados.

Cuando se redefine una función se debe indicar el tipo override en su declaración.

Si una función no define implementación (esto es si la función está vacía), el contrato se convierte en un contrato abstracto.

Interfaces

Nos permiten definir el comportamiento que queremos que tenga un contrato

Se implementa igual que la herencia de contratos.

Sus funciones no tienen implementación, solo encabezados.

Super

Podemos hacer referencia a algún elemento o función de la clase superior por medio de la sentencia super.

    // SPDX-License-Identifier: GPL-3.0

     pragma solidity >=0.7.0 <0.9.0;

     import "./Interface.sol";
     import "./Modificadores.sol";

     contract Herencia is Suma, Modificadores {
    
    constructor(string memory nombreNuevo) Modificadores(nombreNuevo) {
        
    }
    
    function sumar(uint numero1, uint numero2) public override EsOwner() view returns(uint) {
        return numero1 + numero2;
    }
    
    }
