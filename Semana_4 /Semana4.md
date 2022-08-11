# Portafolio de evidencias.

## Semana 4.

Eventos

Los eventos son un tipo de dato que sirve para emitir avisos de que ocurrió alguna acción en particular.
Puede ser utilizado por clientes para escuchar cambios importantes, y también pueden utilizarse para indexar información.
Protocolos como TheGraph utilizan indexación de eventos para agregación de información
https://thegraph.com/en/

contract Eventos {
    
    uint[] public numeros;
    string public resultado;
    
    event NotificacionDeCondicion(bool condicion);
    
    constructor(bool condicion) {
        if (condicion) {
            resultado = "Condicion True";
        }
        else {
            resultado = "Condicion False";
        }
        
        emit NotificacionDeCondicion(condicion);
        
        for (uint iterador = 0; iterador < 10; iterador++) {
            numeros.push(iterador);
        }
    }
    
Es importante comentar que en la declaración del evento, el parámetro se puede llamar como queramos, es decir, no es necesario que ese nombre coincida con lo que vamos a emitir salvo en el tipo.

Esto es, lo pudimos declarar como:

     event NotificacionDeCondicion( bool nombreCualquiera );

Y ese “nombreCualquiera” es el que vamos a ver en el log como argumento.


¿Qué son las funciones en Solidity?

Las funciones son secciones de un programa que se encargar de ejecutar instrucciones de forma independiente. Estas pueden recibir parametros para usarlos dentro del código y pueden retornar una o más varibales. (Conocido como input y output)

Tienen visibilidad al igual que las variables de estado, pueden ser.

  Public: Totalmente accesible, sea cual sea el origen.
  Private: Accesible únicamente a través de una función incluida en el mismo contrato.
  Internal: Accesible únicamente a través de otra función incluida en el mismo contrato, o desde una función de un contrato que deriva del mismo. NO es accesible desde un                 mensaje de un contrato externo o una transacción externa.
  External: Accesible desde una cuenta de propiedad externa y a través de un mensaje (llamada desde otro contrato). No es accesible desde una función del mismo contrato o       uno derivado del mismo.

     contract Funciones{

     uint private resultado;

     function Suma( uint _numero1, uint _numero2 ) public returns (uint) {
         resultado = sumaInterna(_numero1, _numero2);
         return resultado;
     }

     function sumaInterna( uint _num1, uint _num2) private pure returns (uint){
         return _num1 + _num2;
     }

     function ObtenerResultado() public view returns (uint){
         return resultado;
     }
     Modificadores

Los modificadores son funciones especiales por el usuario y que se añaden a otra función para envolver su funcionamiento

modifier <name>(<type> <parameter>..., [,...]) {
  <content>
}

El guión bajo

El guión bajo (también conocido como placeholder), es una instrucción especial del modificador que indica dónde se va a ejecutar el código de la función inicial que envuelve al modifier.

Por ejemplo
## Primero valida y luego ejecuta

    modifier isOwner() {
  if(<condicion>) revert()
  _;
}

## Primero ejecuta y luego valida
    
    modifier isOwner() {
   _;
  if(<condicion>) revert()
}

## Ejecuta, valida y vuelve a ejecutar

    modifier isOwner() {
   _;
  if(<condicion>) revert()
   _;
}


 }
 podríamos modificar la función “Suma” y asignar el resultado a la variable privada “resultado”, luego devolver esa variable. Será necesaroi que la función Suma no sea pure.
 
