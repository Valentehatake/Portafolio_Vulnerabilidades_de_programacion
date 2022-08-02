# Portafolio de evidencias.

## Semana 3.
Mapas

Los mapas son estructuras de datos de tipo llave-valor, que permiten apuntar un tipo de dato a otro en forma de diccionario.
El tipo de la llave puede ser cualquier tipo de dato elemental, (por ejemplo, uint), y el tipo de dato del valor puede ser cualquier dato elemental o complejo, (se pueden inclusive hacer estructuras multidimensionales)

enum: Coleccion ordenada de valores, el primer elemento corresponde con el elemento 0 (cero).

pragma solidity >=0.7.0 <0.9.0;

contract Saldo {
    
    mapping(address => uint) public balance;
    
    enum Estado { Iniciado, Finalizado }
    
    Estado public estadoDelContrato;
    
    constructor() {
        estadoDelContrato = Estado.Iniciado;
        
        balance[msg.sender] = 1000;
        
        estadoDelContrato = Estado.Finalizado;
    }
    
    
}

Estructuras de control

    if/else: Estructura condicional. Ejecuta un bloque u otro dependiendo de una evaluación booleana
    for: Estructura cíclica que ejecuta un bloque de instrucciones un número determinado de veces
    while: Estructura cíclica que repite un bloque mientras se cumpla una condición
    do while: Estructura cíclica que se asmilia al while, con la diferencia que siempre se ejecuta almenos una vez

contract EstructuraDeControl {
    
    uint[] public numeros;
    string public resultado;
    
    constructor(bool condicion) {
        if (condicion) {
            resultado = "Condicion True";
        }
        else {
            resultado = "Condicion False";
        }
        
        for (uint iterador = 0; iterador < 10; iterador++) {
            numeros.push(iterador);
        }
    }
    
}
