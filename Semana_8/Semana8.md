# Portafolio de evidencias.

## Semana 8.
Polimorfismo

Capacidad de poder utilizar contratos derivados en estructuras superiores.


Instanciar un contrato en otro contrato

Dentro de un contrato podemos hacer referencia a otro contrato ya implementado en la red a través de su dirección. Para esto podemos utilizar el tipo de contrato al que referenciamos o bien alguna de sus clases superiores.

    // SPDX-License-Identifier: GPL-3.0

    pragma solidity >=0.7.0 <0.9.0;

    import "./Interface.sol";

    contract Polimorfismo {
    
    function sumarDesdeContrato(uint numero1, uint numero2, address direccionContrato)
        public returns(uint) {  
            Suma interfaceSuma = Suma(direccionContrato);
            return interfaceSuma.sumar(numero1,numero2);
    } 
    
}
