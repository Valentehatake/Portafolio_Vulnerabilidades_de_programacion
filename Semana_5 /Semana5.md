# Portafolio de evidencias.

## Semana 5.
Manejo de errores

    assert: Se utiliza para pruebas, compara dos valores
    revert: Es un error que regresa todas las modificaciones de estado realizadas durante la ejecución de la función. Recibe por parámetro un mensaje             de error
    require: Es una variación del revert que recibe por parámetro una expresión booleana y revierte si esta expresión es falsa.

Cabe destacar que cualquier consumo de gas ejecutado hasta el momento de un revert se debe pagar, porque el cómputo fué utilizado.

      // SPDX-License-Identifier: GPL-3.0
  
     pragma solidity >=0.7.0 <0.9.0;

      contract Errores {
    
    address private owner;
    
    constructor() {
        owner = msg.sender;
    }
    
    function Suma(uint numero1, uint numero2) public view EsOwner() returns (uint) {
        return numero1 + numero2;
    }
    
    modifier EsOwner() {
        require(msg.sender == owner, "El usuario no es el creador del contrato");
        _;
    }
    
}
Tipos de almacenamiento

    Storage: Memoria persistente. Es el más costoso. Similar a la memoria ROM
    Memory: Variables temporales durante ejecución. Se asimila a la RAM
    Calldata: Son constantes definidas en el entorno de ejecución de una variable. No son modificables.

Memoria dinámica

La razón por la que un string necesita un sufijo que indique el uso de memoria, es debido a que es memoria dinámica, por lo que calldata no puede alocar una cantidad definida de memoria, por lo que tenemos que indicarle que esa variable la pase por la memoria volátil (RAM/memory), para que la función la pueda manejar correctamente.

Este efecto ocurre con cualquier cosa que sea de tamaño no definido, por ejemplo:

    Un arreglo
    Un string
    
    // SPDX-License-Identifier: GPL-3.0

    pragma solidity >=0.7.0 <0.9.0;

    contract Almacenamiento {
    
    string private nombre;
    
    constructor(string memory palabra) {
        nombre = palabra;
    }
    
}


Gas y comisiones

El gas es una unidad de medida para el procesamiento de la EVM. Se mide en unidades de gas, y es constante para las mismas operaciones.

    gasPrice: Es la cantidad de ETH que pagamos por unidad de gas. Es decir, aunque el gas sea constante, la demanda por ese gas puede subir el                     precio.
    gasCost: Es la cantidad de unidades de gas que generó la ejecución
    gasFee: Gas cost * Gas Price

Priority fee

A partir del EIP1559 , se realizaron cambios importantes al mercado de gas, y se contempla el priority fee, que es el extra que menciona Sebastián, y es una propina para el minero con la cuál se obtiene prioridad en la ejecución

      // SPDX-License-Identifier: GPL-3.0

      pragma solidity >=0.7.0 <0.9.0;

      contract Gas {
    
    uint public numero;
    
    function asignarNumero(uint entrada) public {
        numero = entrada;
    }

}
