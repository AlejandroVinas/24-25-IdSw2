# LEGIBILIDAD Y REVISION DE CODIGO

## Programacion 1

## Adivina

  ### Línea 3
```java
public class adivina {
```
- ❌ **Nombrado**: El nombre de la clase debe comenzar en mayúscula → `Adivina`.

---

### Línea 6
```java
try (Scanner lectura = new Scanner(System.in)) {
```
- ❌ **Nombrado**: `lectura` no es lo suficientemente claro. Sugerencia: `scanner` o `lectorDeTeclado`.

---

### Línea 7
```java
int suerte = (int)(Math.random()*100+1);
```
- ❌ **Nombrado**: `suerte` es ambiguo. Sugerido: `numeroSecreto`.

---

### Línea 9
```java
int restos = 6;
```
- ❌ **Nombrado**: `restos` es poco claro. Mejor usar `intentosRestantes`.

---

### Línea 10
```java
int solu = 0;
```
- ❌ **Nombrado**: `solu` es una abreviatura poco clara. Mejor: `numeroIngresado`.

---

### Línea 13
```java
System.out.println("Adivina el número que estoy pensando en solo 5 intentos");
```
- ❌ **Formato / lógica**: El mensaje menciona 5 intentos, pero el código da 6 → inconsistencia.

---

### Línea 17
```java
int dato = lectura.nextInt();
```
- ❌ **Nombrado**: `dato` es genérico. Mejor usar `numeroUsuario`.

---

### Línea 29
```java
System.out.println("Vuelve a intentarlo");
```
- ❌ **DRY**: Mensaje repetido en ambas ramas del `if`. Podría extraerse.

---

### Línea 37
```java
while (solu == suerte){
```
- ❌ **Código muerto**: `while` innecesario. Debe ser `if`.

---
## Ascii for java

### Línea 1
```java
public class AsciiFor {
```
- ✅ **Nombrado correcto**: Sigue la convención de nombres para clases (CamelCase y descriptivo).

---

### Línea 7
```java
String t = ("**********");
```
- ❌ **Formato**: Paréntesis innecesarios al asignar la cadena. Mejor: `String t = "**********";`.

---

### Línea 18
```java
String t = (i % 2 == 0 ? "**  **  **" : "  **  **  ");
```
- ❌ **Nombrado**: `t` es demasiado genérico. Mejor: `lineaPatron` o `patronAImprimir`.

---

### Línea 27
```java
String t = ("+--------------------+");
```
- ❌ **Formato**: Paréntesis innecesarios en la asignación de cadena.

---

### Línea 35
```java
t = ("+--------------------+");
```
- ❌ **Formato**: Paréntesis innecesarios en la asignación de cadena.

---

### Línea 41
```java
t = "    *";
```
- ❌ **Nombrado**: `t` sigue siendo poco descriptivo. Mejor: `arbolNavidad` o `formaFigura`.

---

### Línea 53
```java
System.out.println("********");
```
- ❌ **Código muerto**: Este `println` es redundante. Ya se imprime en la lógica del `for` siguiente.

---

### Línea 64
```java
if (i % 2 == 0) {
    t = "***   ***";
    System.out.println(t);
} else {
    t = "*********";
    System.out.println(t);
}
```
- ❌ **Código muerto**: Este `if-else` se repite en cada iteración. Puede simplificarse o centralizarse.

---

## Caracol

### Línea 3
```java
public class caracol {
```
- ❌ **Nombrado**: El nombre de la clase debe comenzar con mayúscula → `Caracol`.

---

### Línea 13-17
```java
final String BORDE_SUPERIOR = "...";
```
- ✅ Bien nombradas: constantes en mayúsculas, con guiones bajos.

---

### Línea 20
```java
String queImprimir;
```
- ❌ **Nombrado**: Aunque es entendible, `lineaADibujar` o `lineaVisual` sería más claro.

---

### Línea 35
```java
for (int dias = 10; dias != 0; dias = dias-1){
```
- ❌ **Formato**: `dias != 0` no es idiomático en Java. Mejor usar: `dias > 0`.

---

### Línea 38-40
```java
int profundidadCaracolm = profundidadCaracol - sube;
int profundidadCaracoln = profundidadCaracolm + baja;
int profundidadFinal = profundidadCaracoln;
```
- ❌ **Nombrado**: Variables con sufijos `m`, `n` no son expresivas. Sugerido: `alturaManana`, `alturaNoche`, `nuevaAltura`.

---

### Línea 51
```java
if (profundidad == profundidadFinal) {
```
- ❌ **Código duplicado**: Esta lógica ya existe antes, puede abstraerse en un método.

---

### Línea 67
```java
} else if (dias == 0 && profundidadFinal > 0) {
```
- ❌ **Lógica innecesaria**: Este bloque nunca se alcanzará ya que `dias` se evalúa antes como `> 0` o se rompe el bucle si sale del pozo.

---

## Carrefur

### Línea 1
```java
public class carrefour {
```
- ❌ **Nombrado**: Las clases deben comenzar en mayúscula → `Carrefour`.

---

### Línea 4
```java
int probabilidadLlegadapersona = 60;
```
- ❌ **Nombrado**: Debe usar `CamelCase` correctamente → `probabilidadLlegadaPersona`.

---

### Línea 7
```java
int caja1 = 0, caja2 = 0, caja3 = 0, caja4 = 0;
```
- ❌ **Nombrado**: Mejor usar una estructura como arreglo o lista. Nombres repetitivos no escalan bien.

---

### Líneas 9-12
```java
if (cajaX >= 1) { cajaX = cajaX - 1; }
```
- ❌ **DRY**: Repetición de lógica. Se puede iterar sobre las cajas usando un arreglo.

---

### Líneas 14-17
```java
if (Math.random() * 100 <= probabilidadLlegadapersona) {
    cola = cola + 1;
}
```
- ✅ Correcto, aunque el nombre largo con mezcla de minúsculas y mayúsculas puede afectar legibilidad.

---

### Líneas 18-29
```java
if (cola >= 1 && cajaX == 0) {
    cola--;
    items = random...
    cajaX = items;
}
```
- ❌ **DRY**: Código repetido para cada caja. Se puede factorizar.

---

### Línea 31
```java
System.out.println("---------------------------------------------------------------------");
```
- ✅ Bien como separador visual. Podría extraerse como constante.

---

### Línea 33
```java
System.out.println("Caja 1 ["+caja1 +"] | Caja 2 ["+caja2+"] | Caja 3 ["+caja3+"]  | Caja 4 ["+caja4+"]" );
```
- ❌ **Formato**: Falta espacio después de los signos `+` y sobra uno antes del `);`.

---

## DevolverCambio

### 1. **Uso de variables no descriptivas**:
   - **Líneas**: 5-6
   - **Error**: Las variables `coste`, `pagado`, `vuelta`, `resto`, y `cantidad` no son lo suficientemente descriptivas.
   - **Mejora**: Utiliza nombres más específicos para que el código sea más claro.
     - `coste` → `precioTotal`
     - `pagado` → `montoPagado`
     - `vuelta` → `montoDeVuelta`
     - `resto` → `restoBilletes`
     - `cantidad` → `cantidadBilletes`

### 2. **Formato y estilo de código**:
   - **Líneas**: Todo el código
   - **Error**: El formato de las llaves `{` y `}` podría ser más consistente. Aunque no es estrictamente incorrecto, el estilo de las llaves debería seguir un patrón establecido, ya sea de estilo K&R o Allman.
   - **Mejora**: Asegúrate de que todas las llaves estén alineadas correctamente y de acuerdo con el estilo elegido por el equipo.

### 3. **Repetición de código (violación de DRY)**:
   - **Líneas**: 16-52
   - **Error**: El código es muy repetitivo debido a las muchas condiciones similares para cada denominación de billete y moneda.
   - **Mejora**: Podrías refactorizar este bloque de código para eliminar la duplicación, utilizando un array o lista que contenga las denominaciones y un bucle para manejar las impresiones.
     ```java
     double[] denominaciones = {500, 200, 100, 50, 20, 10, 5, 2, 1, 0.5, 0.2, 0.1, 0.05, 0.02, 0.01};
     String[] nombres = {"billetes de 500€", "billetes de 200€", "billetes de 100€", "billetes de 50€", "billetes de 20€", "billetes de 10€", 
                         "billetes de 5€", "monedas de 2€", "monedas de 1€", "monedas de 50 cent", "monedas de 20 cent", "monedas de 10 cent", 
                         "monedas de 5 cent", "monedas de 2 cent", "monedas de 1 cent"};
     
     for (int i = 0; i < denominaciones.length; i++) {
         if (vuelta / denominaciones[i] >= 1) {
             resto = vuelta % denominaciones[i];
             cantidad = (vuelta - resto) / denominaciones[i];
             System.out.println("Se le devuelven " + (int)cantidad + " " + nombres[i]);
             vuelta = Math.round((vuelta - (cantidad * denominaciones[i])) * 100.0) / 100.0;
         }
     }
     ```
     Esto hace el código mucho más limpio y fácil de mantener.

### 4. **Uso de `Math.round` innecesario**:
   - **Líneas**: 18, 25, 32, ..., 66
   - **Error**: El uso de `Math.round` para redondear la `vuelta` es innecesario ya que el cálculo está basado en monedas y billetes de valores exactos. Esto puede dar lugar a imprecisiones al redondear de nuevo.
   - **Mejora**: Si el propósito es mantener la precisión, no es necesario redondear en cada paso. Puedes simplemente realizar la operación sin usar `Math.round`.

### 5. **Verificación innecesaria de la condición `(vuelta / X) >= 1`**:
   - **Líneas**: 16-52
   - **Error**: La verificación `(vuelta / X) >= 1` es redundante, ya que puedes usar directamente una condición `if (vuelta >= X)` en lugar de hacer divisiones repetidas. Además, el operador `%` ya se encarga de verificar la cantidad restante.
   - **Mejora**: Cambia las verificaciones para ser más simples y directas:
     ```java
     if (vuelta >= 500) {
         cantidad = (int) (vuelta / 500);
         System.out.println("Se le devuelven " + cantidad + " billetes de 500€");
         vuelta -= cantidad * 500;
     }
     ```

### 6. **Problema con las comillas en los nombres de las denominaciones**:
   - **Líneas**: 16-52
   - **Error**: Los nombres de las denominaciones de las monedas y billetes deberían ser más coherentes en el uso de la notación "€" y "cent". Además, la palabra "cent" debería ir en singular cuando se habla de una moneda.
   - **Mejora**: Deberías asegurar que las denominaciones sean consistentes, como "monedas de 1 céntimo" y "billetes de 500€".

### 7. **Mensajes poco claros o innecesarios**:
   - **Líneas**: 10, 13
   - **Error**: Los mensajes como `"El cliente tiene que pagar ..."` o `"No le alcanza para pagar ..."` no son lo suficientemente claros, y no están bien estructurados para facilitar la lectura del resultado.
   - **Mejora**: Mejora la legibilidad de los mensajes al especificar la cantidad de cambio que se está devolviendo o indicar de manera más precisa los errores.

### 8. **Código muerto**:
   - **Líneas**: Ninguna en específico
   - **Error**: Aunque no hay código muerto explícito, siempre es importante asegurarse de que el código no incluya fragmentos innecesarios, como bloques de código comentados. Si no es necesario, elimina cualquier comentario innecesario.
   - **Mejora**: Revisa y elimina cualquier fragmento de código que no esté cumpliendo una función en el programa.

## DibujosAscii
### 1. **Indentación inconsistente**:
   - **Líneas**: Todo el código
   - **Error**: El código no tiene una indentación consistente en todo el bloque. Las líneas dentro de los bloques `for` o los métodos deben estar correctamente alineadas.
   - **Mejora**: Asegúrate de que todo el código dentro de las estructuras de control como `for`, `if`, y `else` esté correctamente indentado para mejorar la legibilidad. Aquí un ejemplo de cómo debería verse:
     ```java
     for (int dias = 10; dias != 0; dias = dias - 1) {
         Random rnd = new Random();
         int sube = (int) (rnd.nextDouble() * 4 + 1);
         int baja = (int) (rnd.nextDouble() * 2 + 1);
         System.out.print("VALOR SUBE " + sube + "   VALOR BAJA " + baja + "    ");
     }
     ```

### 2. **Generación de números aleatorios**:
   - **Líneas**: 15-16
   - **Error**: El uso de `rnd.nextDouble()` para generar números aleatorios enteros es innecesario y más complicado de lo que debería ser. La clase `Random` proporciona métodos como `nextInt()` que se utilizan con mayor eficiencia.
   - **Mejora**: Usa `nextInt()` para generar números enteros en el rango deseado de manera más sencilla.
     ```java
     int sube = rnd.nextInt(4) + 1; // Genera un número entre 1 y 4
     int baja = rnd.nextInt(2) + 1; // Genera un número entre 1 y 2
     ```

### 3. **Desperdicio de recursos en cada iteración**:
   - **Líneas**: 14-16
   - **Error**: Creas una nueva instancia de `Random` dentro del ciclo `for` en cada iteración. Esto es ineficiente porque la clase `Random` se puede reutilizar fuera del ciclo.
   - **Mejora**: Crea una sola instancia de `Random` antes del ciclo `for`, y luego reutilízala dentro del ciclo:
     ```java
     Random rnd = new Random();  // Instanciación fuera del ciclo
     for (int dias = 10; dias != 0; dias = dias - 1) {
         int sube = rnd.nextInt(4) + 1;
         int baja = rnd.nextInt(2) + 1;
         System.out.print("VALOR SUBE " + sube + "   VALOR BAJA " + baja + "    ");
     }
     ```

### 4. **Posibles errores de lógica en el ciclo `for`**:
   - **Líneas**: 13
   - **Error**: El ciclo `for` está usando la condición `dias != 0` como la condición de salida. Aunque esto funciona, es más común y legible usar la condición `dias > 0`.
   - **Mejora**: Cambia la condición del ciclo `for` a `dias > 0` para mejorar la legibilidad:
     ```java
     for (int dias = 10; dias > 0; dias--) {
         // Lógica del ciclo
     }
     ```

### 5. **Impresión de la salida (claridad de los resultados)**:
   - **Líneas**: 16
   - **Error**: Imprimir las variables `sube` y `baja` en una sola línea puede hacer que la salida sea difícil de leer, especialmente si no hay saltos de línea entre los valores generados.
   - **Mejora**: Agregar un salto de línea después de cada impresión de los valores de `sube` y `baja` para que cada par de valores esté en una línea separada:
     ```java
     System.out.println("VALOR SUBE " + sube + "   VALOR BAJA " + baja);
     ```

### 6. **Uso innecesario de comillas en los comentarios de la salida**:
   - **Líneas**: 14-16
   - **Error**: La forma en que las cadenas están impresas en el `System.out.print()` es correcta, pero se podría mejorar la presentación de los resultados.
   - **Mejora**: Utiliza el formato correcto en el `System.out.print()` para que el texto sea más legible y organizado. Además, al final del ciclo, puedes imprimir una línea para separar las ejecuciones de las iteraciones.

### 7. **Código no modularizado**:
   - **Líneas**: Todo el código
   - **Error**: El código realiza varias tareas: dibujar el cuadro y calcular los valores aleatorios, pero no está modularizado. Si necesitas expandir el código en el futuro, tendrías que repetir muchas líneas.
   - **Mejora**: Sería más limpio si modularizas el código en métodos. Por ejemplo, un método para dibujar el cuadro y otro para generar y mostrar los valores aleatorios.
     ```java
     public static void dibujarCuadro() {
         System.out.println("+--------------------+");
         System.out.println("|**  **  **  **  **  |");
         System.out.println("|**  **  **  **  **  |");
         System.out.println("|  **  **  **  **  **|");
         System.out.println("|  **  **  **  **  **|");
         System.out.println("|**  **  **  **  **  |");
         System.out.println("|**  **  **  **  **  |");
         System.out.println("|  **  **  **  **  **|");
         System.out.println("|  **  **  **  **  **|");
         System.out.println("+--------------------+");
     }

     public static void generarValoresAleatorios() {
         Random rnd = new Random();
         for (int dias = 10; dias > 0; dias--) {
             int sube = rnd.nextInt(4) + 1;
             int baja = rnd.nextInt(2) + 1;
             System.out.println("VALOR SUBE " + sube + "   VALOR BAJA " + baja);
         }
     }
     ```
## EDA 1

### Reto 001

- Fila.java
  
### **1. Nombres de Variables y Métodos**
- **Claridad de los nombres**: Los nombres de las variables y métodos son, en general, **claros y expresivos**. 
  - **Variables** como `fila`, `capacidad`, `cantidadActual` y `indice` son intuitivas y reflejan claramente lo que almacenan o representan. 
  - Los métodos como `abrirFila()`, `agregarPersona()`, `atenderPersona()`, `irseDeFila()`, `traerCosasA()`, etc., son **descriptivos** sobre la acción que realizan.
- **Consistencia**: Se mantiene una **consistencia** en el uso de nombres en español, lo cual es importante para evitar confusión. Sin embargo, en un entorno de desarrollo en inglés, se recomienda traducir estos términos a inglés.
  
### **2. Comentarios**
- El código **utiliza comentarios**, pero en algunos casos, se podrían ampliar para explicar con mayor detalle ciertos fragmentos del código. Los comentarios son breves y ayudan a **entender las acciones de los métodos**, pero no explican las decisiones de diseño o posibles casos particulares que podrían surgir.
  - Ejemplo:
    ```java
    // Abrir fila (inicializada vacía)
    ```
    Sería útil incluir más contexto o ejemplos de cómo se comporta este método si se ejecuta varias veces.

### **3. Estructura del Código**
- **Bloques y formato**: La indentación del código es consistente y está bien estructurada. Las llaves de apertura y cierre `{}` están alineadas adecuadamente, lo que hace que el código sea **fácil de seguir visualmente**.
- El uso de **espacios en blanco** entre los métodos mejora la **legibilidad**, ya que permite distinguir cada función de manera clara.
  
### **4. Uso de Condicionales y Ciclos**
- Las condicionales (if/else) dentro de los métodos están bien formuladas y son claras. 
  - Los métodos como `agregarPersona()`, `atenderPersona()`, `irseDeFila()` y otros comprueban condiciones de manera eficiente y muestran los mensajes de error apropiados cuando es necesario.
  - En algunas funciones como `colarLicita()` o `colarIlicita()`, la lógica de insertar una persona en la fila está bien estructurada mediante un **bucle `for`**, lo que facilita la comprensión de la **modificación de la estructura**.
  
### **5. Lógica del Código**
- En términos de **lógica y flujo de ejecución**, el código parece bien organizado. Cada función realiza un solo propósito, lo que hace que los métodos sean **fáciles de entender**.
  - Por ejemplo, el método `atenderPersona()` hace lo que promete: atender a la persona en la primera posición de la fila. Al mismo tiempo, **reajusta la fila** correctamente moviendo las personas hacia adelante.
  - Un punto que podría mejorar es la **validación de índice** y manejo de errores. Por ejemplo, se podrían agregar validaciones de **índices fuera de rango** de manera más consistente en todas las funciones que afectan a la fila.

### **6. Legibilidad de los Mensajes**
- Los mensajes impresos con `System.out.println()` son **claros y comprensibles**. 
  - Ejemplos:
    ```java
    System.out.println("La fila está llena.");
    System.out.println("No hay nadie en la fila.");
    ```
    Estos mensajes proporcionan retroalimentación inmediata al usuario de la acción que está tomando.

### **7. Oportunidades de Mejora**
- **Modularidad**: Aunque los métodos están relativamente bien estructurados, algunas acciones se repiten en múltiples lugares, como la impresión de los estados de la fila y las condiciones de error. Esto podría modularizarse mejor mediante un **método adicional para mostrar el estado de la fila**.
  - Ejemplo: Los bloques repetidos de impresión de la fila en varios métodos como `agregarPersona()`, `irseDeFila()`, etc. podrían extraerse en un método separado.
- **Nombres más específicos**: En métodos como `colarLicita()` y `colarIlicita()`, el uso de "Licita" y "Ilicita" puede ser ambiguo. Aunque el código tiene sentido, sería mejor cambiar estos nombres a algo más claro como `colarLegalmente()` y `colarIlegalmente()`. Esto haría que el propósito del método sea más claro para los futuros desarrolladores.

- Main.java
### **1. Nombres de Variables y Métodos**
- **Claridad de los nombres**: Los nombres de las variables y métodos son **claros y descriptivos**:
  - La variable `fila` es una **instancia de la clase `Fila`**, lo que queda claro de inmediato.
  - Las personas como `p1`, `p2`, `p3` tienen nombres sencillos y fáciles de identificar (aunque puede ser mejor usar nombres más descriptivos si se tratara de un código más complejo).
  - Los métodos como `agregarPersona()`, `atenderPersona()`, `mostrarFila()`, etc., son claramente entendibles y reflejan bien las acciones que realizan.

- **Consistencia**: El código sigue una **convención consistente** en cuanto a la nomenclatura de las variables y métodos, lo que facilita su comprensión.

### **2. Estructura del Código**
- **Organización de las acciones**: El flujo de acciones es muy claro. Cada paso en el método `main()` tiene una secuencia lógica:
  1. Se crea una fila y se abre.
  2. Se crean varias personas y se agregan a la fila.
  3. Se realizan varias acciones como atender a una persona, colarse, que alguien se vaya, traer cosas, etc.
  
  La estructura sigue un patrón **secuencial y sencillo**, lo que hace que el código sea fácil de leer.
  
- **Espaciado**: El código está bien espaciado entre las acciones, lo que mejora la **legibilidad**. Los bloques de código relacionados entre sí (como las operaciones con la fila) están agrupados y claramente separados por líneas en blanco.

### **3. Uso de Métodos**
- Los métodos que se invocan, como `agregarPersona()`, `atenderPersona()`, y `mostrarFila()`, son **claros en su propósito**. Cada uno está implementado correctamente y refleja una acción específica sobre la fila. 
  - **Ejemplo**: `fila.mostrarFila();` muestra el estado actual de la fila, lo que es muy útil para seguir el flujo del programa.

- **Secuencia de acciones**: El flujo de las operaciones es **intuitivo**:
  - Primero se agregan personas, luego se atienden, se permite que alguien se cuele y se retiran personas de la fila.
  - **Acciones como "colarse lícitamente" o "ilícitamente"** son interesantes y muestran el uso de métodos adicionales para modificar la fila. Aunque el concepto de "colarse" es más específico y puede ser confuso fuera de este contexto, está bien manejado en el código.
  
### **4. Lógica del Código**
- **Flujo secuencial**: El flujo del código es **lineal** y fácil de seguir. Los métodos de la clase `Fila` se invocan de manera ordenada, sin saltos ni procesos complejos.
  
  La implementación está bastante alineada con la funcionalidad deseada, permitiendo simular una fila de personas que pueden entrar, salir, ser atendidas y realizar varias otras interacciones.

- **Manejo de condiciones y errores**: El código **no maneja explícitamente errores o condiciones que podrían surgir** al agregar, atender o modificar la fila, como intentar atender a una persona cuando la fila está vacía. Aunque la clase `Fila` ya incluye estas comprobaciones, el código en `Main` sigue un flujo esperado sin validaciones adicionales.
  
### **5. Mensajes Informativos**
- Los mensajes impresos con `System.out.println()` proporcionan una **retroalimentación clara y directa** sobre cada acción realizada, lo que permite que el usuario (o el desarrollador que lo lea) entienda fácilmente el estado de la fila y las acciones ejecutadas.

  Ejemplos de mensajes claros:
  ```java
  System.out.println(p + " se ha añadido a la fila.");
  System.out.println(atendida + " ha sido atendida.");
  System.out.println("La fila está llena.");

- Persona.java

### **1. Nombres de Variables y Métodos**
- **Claridad de los nombres**:
  - La variable `nombre` es clara y descriptiva. Representa el nombre de la persona, lo cual es fácil de entender en el contexto de esta clase.
  
- **Consistencia**: El código sigue una **convención consistente** en cuanto a la nomenclatura de la variable `nombre`. El nombre es un atributo común y se maneja de forma clara y directa.

- **Método `toString()`**:
  - Este método sobrescribe el método `toString()` de la clase `Object` y devuelve el `nombre`. Es común en clases con atributos sencillos como `nombre`, ya que permite imprimir una representación más amigable del objeto cuando se usa en métodos como `System.out.println()`.
  
### **2. Estructura del Código**
- **Constructor**: El constructor está bien definido y claro. Recibe un parámetro `nombre` y lo asigna al atributo de la clase. Sin embargo, el punto y coma adicional (`;`) después de la asignación no es necesario y puede eliminarse.
  
  ```java
  public Persona(String nombre) {
      this.nombre = nombre;
  }


## Reto 004

- Album.java
  ## 1. Nombres de Variables y Métodos

- **Variables:**
  - `titulo`, `artista`, `año`: nombres adecuados y autoexplicativos.
  - `canciones`: el nombre es apropiado para representar una colección de objetos `Cancion`.

- **Métodos:**
  - `agregarCancion(Cancion cancion)`: claro y descriptivo.
  - `mostrarCanciones()`: también es claro y está bien nombrado.
  - `toString()`: sobrescribe correctamente el método para devolver una representación legible del álbum.

---

## 2. Estructura del Código

- La clase sigue una estructura lógica y ordenada:
  - Atributos declarados al inicio.
  - Constructor claro e inicialización correcta de la lista `canciones`.
  - Métodos bien definidos y relacionados con el comportamiento esperado de un álbum musical.

---

## 3. Lógica del Código

- El constructor inicializa los atributos correctamente y evita redundancia.
- La lista `canciones` es instanciada con una estructura genérica `Listalink<Cancion>` (presumiblemente una lista enlazada propia).
- `agregarCancion()` agrega una canción a la lista.
- `mostrarCanciones()` imprime el título del álbum y utiliza `canciones.display()` (asumiendo que este método imprime las canciones).
- El método `toString()` muestra correctamente una representación textual del álbum, incluyendo título, artista y año.

---

## 4. Oportunidades de Mejora

- **Encapsulamiento:**
  - La lista `canciones` es pública, lo cual rompe el principio de encapsulamiento. Debería ser `private` o `protected`, y accesible solo mediante métodos de la clase.

    ```java
    private Listalink<Cancion> canciones;
    ```

- **Validación de parámetros en el constructor:**
  - Sería útil agregar validaciones para asegurar que `titulo`, `artista` y `año` sean válidos (no nulos y año positivo).

    ```java
    public Album(String titulo, String artista, int año) {
        if (titulo == null || artista == null || año <= 0) {
            throw new IllegalArgumentException("Datos del álbum inválidos.");
        }
        this.titulo = titulo;
        this.artista = artista;
        this.año = año;
        this.canciones = new Listalink<>();
    }
    ```

- **Ortografía del atributo `año`:**
  - Técnicamente válido, pero puede generar advertencias por usar caracteres especiales (como la `ñ`) en nombres de variables. Aunque está en español, en entornos internacionales o configuraciones específicas podría causar inconvenientes.

    Alternativa segura:
    ```java
    private int anio;
    ```

---
- Reproductor.java

  ### ✔️ Nombres Claros y Descriptivos
- `colaReproduccion`, `historial`, `modoAleatorio`, `modoRepetir`: son representativos de su propósito.
- Los métodos como `reproducirCancion()`, `siguienteCancion()` y `verCola()` son autoexplicativos.

### ✔️ Estructura Clara
- Separación lógica de funcionalidades: reproducción, historial, modos, visualización.
- Uso adecuado de modificadores de acceso en algunos atributos y métodos.

### ✔️ Uso de Objetos Personalizados
- Se usan listas genéricas `Listalink<Cancion>`, lo cual indica una implementación personalizada de estructuras enlazadas.

---

## ⚠️ Problemas de Legibilidad y Lógica

| Línea(s) | Tipo de Problema | Descripción |
|----------|------------------|-------------|
| 5        | **Mal Encapsulamiento** | `colaReproduccion` es pública cuando debería ser privada. |
| 12       | **Inconsistencia** | Se recibe un parámetro `cancion` pero **no se usa** para eliminarla. Solo se remueve el primer elemento. |
| 45-47    | **Falta Validación** | Si la cola está vacía, `remove()` puede devolver `null`, causando `NullPointerException` en `reproducirCancion()`. |
| 55       | **Encapsulamiento** | `modoAleatorio` es público. Debería ser privado con métodos getter/setter. |
| 58       | **Acoplamiento** | `reproducirPlaylist()` agrega todas las canciones directamente a la cola sin verificar duplicados ni estado previo. |

---

- Playlist.java
  

---

## ✅ Buenas Prácticas y Legibilidad

| Aspecto | Evaluación |
|--------|------------|
| **Nombres de variables y métodos** | Claros y descriptivos (`agregarCancion`, `mostrarCanciones`, `getNombre`) |
| **Organización del código** | Clara y estructurada, métodos agrupados por propósito |
| **Uso de herencia** | Hereda correctamente de `Album` aunque no aprovecha completamente sus atributos |

---

## ⚠️ Problemas de Legibilidad y Diseño

| Línea(s) | Tipo de Problema | Descripción |
|----------|------------------|-------------|
| 2        | ❗ **Diseño Innecesario** | Heredar de `Album` no es semánticamente correcto. Una `Playlist` no es un tipo de `Album`. Mejor usar composición. |
| 12       | ❌ **Lógica Incorrecta** | `eliminarCancion(Cancion)` llama a `remove()` sin pasar el parámetro `cancion`. Elimina la primera canción sin relación con la entrada. |
| 3-5      | ⚠️ **Redundancia** | `nombre` se pasa a `super` como título y se guarda también localmente, causando ambigüedad. |
| 24       | ❌ **Violación del Principio de Sustitución** | Si `Playlist` se usa como `Album`, los atributos `artista` y `año` estarán vacíos/irrelevantes. |

---

- Main.java

  ## ✅ Buenas Prácticas Identificadas

| Aspecto | Evaluación |
|--------|------------|
| **Estructura del menú principal** | Claramente segmentada en secciones: Reproducción, Biblioteca, Salida |
| **Uso de clases auxiliares** | Uso correcto de `Reproductor`, `Biblio`, y `Playlist` |
| **Entrada del usuario** | Utiliza `Scanner` de forma adecuada para capturar interacciones |

---

## ⚠️ Problemas de Legibilidad y Lógica

| Línea(s) | Tipo de Problema | Descripción |
|----------|------------------|-------------|
| 2        | ❌ **Variable no usada** | `Biblio biblioteca = new Biblio();` fuera del `main()` nunca se utiliza. Se puede eliminar. |
| 34-125   | ❗ **Falta de `break` en `switch`** | Cada `case` de los submenús no termina con `break`, provocando ejecución de múltiples opciones en cadena (fall-through). |
| 126-209  | ❗ **Mismo error en submenús de Biblioteca y Playlist** | Todos los `switch` internos carecen de `break`, lo cual provoca comportamientos no deseados. |
| 81-84    | ⚠️ **Repetición innecesaria de código** | Se crea una nueva instancia de `Cancion` sin verificar si ya existe en la biblioteca. |
| 31       | ⚠️ **Interfaz de usuario poco clara** | El menú principal imprime múltiples líneas sin separación visual, puede mejorar con líneas divisoras o encabezados. |
| 36-123   | 🔁 **Demasiado anidamiento** | `switch` dentro de `switch` dentro de `switch`, lo que dificulta la legibilidad. Mejor dividir en métodos separados. |
| General  | ❌ **No manejo de errores** | No se controla la entrada del usuario (por ejemplo, letras donde se esperan números), puede causar `InputMismatchException`. |
| General  | ❗ **Repetición de código** | Varias acciones similares se repiten, como pedir el título/artista/duración. Se puede modularizar. |

---

- Biblio.java
  
  ## ✅ Buenas Prácticas Identificadas

| Aspecto | Evaluación |
|--------|------------|
| **Nombres de métodos** | Los nombres de los métodos como `añadirCancionFavorita()`, `verFavoritas()`, y `buscarCancion()` son descriptivos y fáciles de entender. |
| **Modularidad** | Los métodos están bien divididos para realizar tareas específicas, lo que hace que el código sea más fácil de mantener. |
| **Estructura general** | La clase está organizada y tiene una estructura clara con métodos bien definidos para añadir, eliminar y buscar canciones, albums y playlists. |
| **Uso de clases** | Se utilizan correctamente las clases `Cancion`, `Album`, y `Playlist` para organizar la información y funciones relacionadas. |

---

## ⚠️ Problemas de Legibilidad y Lógica

| Línea(s) | Tipo de Problema | Descripción |
|----------|------------------|-------------|
| 56 | ❌ **Eliminación incorrecta de canciones favoritas** | En el método `eliminarCancionFavorita()`, el código usa `cancionesFavoritas.remove()` sin especificar el objeto a eliminar. Esto puede causar que el método elimine un elemento incorrecto o falle. |
| 72-75 | ❌ **Uso incorrecto de la variable `playlist`** | En los métodos `buscaPlaylist()` y `borraPlaylist()`, se hace referencia a `playlist` sin obtener el objeto correspondiente de `albums`. Esto causará que siempre se compare o elimine la misma instancia de `playlist`. |
| 109 | ❌ **Uso incorrecto de la variable `cancion`** | En el método `buscarCancion()`, se usa la variable `cancion` sin acceder a los elementos de la lista `lista`. Esto generará una comparación errónea. |
| 117-118 | ⚠️ **Repetición de código para visualizar playlists y albums** | Los métodos `verAlbums()` y `verPlaylist()` realizan exactamente la misma acción (`albums.display()`). Esto puede crear confusión, ya que los métodos deberían tener un propósito distinto. |
| 38 | ⚠️ **Inconsistencia en el nombre del método** | El método `iniciarpredeterminados()` no sigue la convención de nomenclatura en Java, que debería ser `iniciarPredeterminados()` (uso de `camelCase`). |
| 133 | ⚠️ **Falta de validaciones al agregar canciones** | No se comprueba si una canción ya está en la lista de canciones favoritas antes de añadirla, lo que podría resultar en duplicados no deseados. |
| General | ⚠️ **Falta de manejo de excepciones** | No hay manejo de excepciones para casos como listas vacías o elementos no encontrados en `cancionesFavoritas`, `albums`, y `playlist`. Esto podría causar errores en tiempo de ejecución si las colecciones no contienen los elementos esperados. |
| 98-108 | ⚠️ **Falta de comentarios explicativos** | El código carece de comentarios que expliquen el propósito de cada bloque o lógica compleja. Esto dificulta la comprensión del código. |
| 36-42 | ⚠️ **Posible confusión en la gestión de playlists** | Los métodos `verPlaylist()` y `buscaPlaylist()` utilizan el mismo nombre de colección `albums`, lo que puede causar confusión, ya que contiene tanto `Album` como `Playlist`. |


- Cancion.java

## ✅ Buenas Prácticas Identificadas

| Aspecto | Evaluación |
|--------|------------|
| **Nombres descriptivos de atributos** | Los nombres de los atributos como `titulo`, `artista`, `duracion`, `favorita` y `reproducida` son claros y fáciles de entender. |
| **Uso adecuado del constructor** | El constructor de la clase `Cancion` está correctamente configurado para inicializar los atributos y establecer valores predeterminados para `favorita` y `reproducida`. |
| **Uso de `toString()`** | El método `toString()` está correctamente implementado para representar a la canción de manera legible y clara. |

---

## ⚠️ Problemas de Legibilidad y Lógica

| Línea(s) | Tipo de Problema | Descripción |
|----------|------------------|-------------|
| 26-27 | ⚠️ **Falta de validación de parámetros** | El constructor no valida que los parámetros proporcionados (como `titulo`, `artista`, `duracion`) sean correctos o no nulos. Esto podría resultar en la creación de objetos con valores inválidos. |
| 18 | ⚠️ **Métodos setters sin lógica adicional** | Los métodos `setFavorita()` y `setReproducida()` simplemente asignan valores a los atributos, pero no tienen validaciones o lógica adicional que podría ser útil (por ejemplo, asegurarse de que una canción no se marque como "favorita" si no se ha reproducido). |
| 24 | ⚠️ **Falta de getter para `favorita` y `reproducida`** | Aunque el código permite modificar los atributos `favorita` y `reproducida` mediante los setters, no hay métodos getters que permitan acceder a estos valores. Esto limita el acceso a estos atributos fuera de la clase. |
| 14 | ⚠️ **Falta de comentarios explicativos** | El código carece de comentarios explicativos, lo que dificulta la comprensión del propósito de cada sección, especialmente para quienes puedan revisar el código más tarde. |

## EDA 2



  

