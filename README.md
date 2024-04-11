# propagacion-excepciones

En el siguiente diagrama se muestra gráficamente cómo se propaga la excepción que se genera en el código, a través de la pila de llamadas durante la ejecución del código:


![Ejemplo](https://dis.um.es/~bmoros/Tutorial/parte9/cap9-2.gif)

Cuando se crea una nueva excepción, derivando de una clase Exception ya existente, se puede cambiar el mensaje que lleva asociado. La cadena de texto puede ser recuperada a través de un método. Normalmente, el texto del mensaje proporcionará información para resolver el problema o sugerirá una acción alternativa. Por ejemplo:

        class SinGasolina extends Exception {
            SinGasolina( String s ) {    // constructor
                super( s );
                }
            ....

      // Cuando se use, aparecerá algo como esto
          try {
              if( j < 1 )
                  throw new SinGasolina( "Usando deposito de reserva" );
          } catch( SinGasolina e ) {
              System.out.println( o.getMessage() );
              }
Esto, en tiempo de ejecución originaría la siguiente salida por pantalla:

      > Usando deposito de reserva
