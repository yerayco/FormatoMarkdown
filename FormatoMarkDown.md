# Markdown
## Indice

1. [Como se programa en MarkDown](#como-se-programa-en-markdown)
2. [¿Se sigue utilizando?](#se-sigue-utilizando)
3. [¿Cuando se invento?](#cuando-se-invento)
4. [Tipografía](#Tipografía)
5. [Listas desordenadas](#listas-desordenadas)
6. [Listas ordenadas](#lista-ordenada)
7. [Snippets de código](#snippets-de-código)
8. [citas](#citas)
9. [Imágenes externas](#imágenes-externas)
10. [Imagenes con enlaces](#imagenes-con-enlace)
11. [Tablas](#tablas)
12. [Lineas Horizontañes](#líneas-horizontales)
13. [Lista de tareas](#lista-de-tareas)
14. [Emojis](#emojis)
15. [Fórmulas matemáticas](#fórmulas-matemáticas)
16. [Referencias](#referencias)
17. [Referencias al pie](#referencias-al-pie)
## ¿Como se programa en MarkDown?

### ¿Se sigue utilizando?

#### ¿Cuando se invento?

**Tipografía**

**Negrita**

*cursiva*

~~tachado~~

==remarcado==

***Negrita y cursiva***

# Listas desordenadas
- ordenador
- ratón
- teclado
    - pantalla
    - ram
- gráfica

# Lista ordenada
1. Guantes
2. Mono
3. Moto 
    1. intercomunicador
    2. rodilleras
4. escape
 

## Snippets de código: 
```Java
public class OperacionesBancarias {

    /**
     *
     * @param cBanco Código del banco. Debe o bien estar en blanco o tener tres dígitos, en cuyo caso el primero debe ser mayor que 1
     * @param cSucursal Código de la sucursal. Debe ser un número de 4 dígitos, el primero distinto de 0
     * @param nCuenta Número de cuenta. Debe ser un número de 5 dígitos.
     * @param clave Clave personal. Debe ser una cadena de 5 caracteres.
     * @param orden Operación a realizar. Puede estar en blanco o tomar los valores "Talonario" o "Movimientos".
     * @return Si los parámetros son correctos enviará un talonario de cheques si la orden era "Talonario" 
     *         o los movimientos de la cuenta durante el mes en curso si la orden era "Movimientos". Si orden 
     *         está en blanco se enviarán ambos documentos.
     * @throws IllegalArgumentException Si alguno de los parámetros es incorrecto
     */
    public static String operacion(String cBanco,
                                   int cSucursal,
                                   String nCuenta,
                                   String clave,
                                   String orden) throws IllegalArgumentException {
        String resultado="";
        int cB;
        if (!cBanco.equals("")){
            try {
                cB=Integer.parseInt(cBanco);
            } catch (Exception e){
                throw new IllegalArgumentException("Código de Banco incorrecto");
            }
            if (cB < 100 || cB >999){
                throw new IllegalArgumentException("Código de Banco incorrecto");
            }
        }
        if (cSucursal < 1000 || cSucursal >9999){
            throw new IllegalArgumentException("Código de Sucursal incorrecto");
        }
        if (nCuenta.length()!= 5){
            throw new IllegalArgumentException("Número de cuenta incorrecto");
        } else {
            try {
                Integer.parseInt(nCuenta);
            } catch (Exception e){
                throw new IllegalArgumentException("Número de cuenta incorrecto");
            }            
        }
        if (clave.length()!=5){
            throw new IllegalArgumentException("Clave personal de longitud incorrecta");
        }
        
        
        if (orden.equals("Talonario")){
            resultado = "Talonario enviado";
        } else if (orden.equals("Movimientos")){
            resultado = "Movimientos enviados";
        } else {
            resultado = "Talonario y movimientos enviados";
        }
       
       
        if(!orden.equals("")&&
       !orden.equals("Talonario")&&
       !orden.equals("Movimientos")){
        throw new IllegalArgumentException("Orden incorrecta");
    }
       
        return resultado;
    }
    


}
```
## Citas

>La poesía es el sentimiento que le sobra al corazón y te sale por la mano.

Mi motor de busqueda favorito es [Google](https://google.com)

Para acceder a un enlace interno[prueba](prueba.md)

## Imágenes externas
![LogoMarkDown](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQdVKuf0TE3N69JJpjQYp6XqwXUyaqrXEpvWg&s)


## Imagenes con enlace
![LogoMarkDown](images/imagesmark.png)

## Tablas 
| Producto    | Código      |
| ----------- | ----------- |
| cocacola    | 98498       |
| agua        | 7884        |


## Líneas horizontales 
**Tipo 1**
***

**Tipo 2**
---

**Tipo 3**
_________________

## Saltos de línea
Doble enter

## Lista de tareas

* Ram
* Cpu 
* Gráfica

## Emojis

:grin:          :raised_hand:

:angry:         :raised_hands:

:sunglasses:    :clap:

:star:          :muscle:

:v:             :walking:

## Fórmulas matemáticas

$\sqrt{3x-1}+(1+x)^2$

$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

## Referencias
[referencias](https://www.markdownguide.org/basic-syntax/#reference-style-links)


## Referencias al pie
Aqui podremos saber el significado de la palabra  Efímero [^1] y el significado de la palabra Melifluo [^2]

[^1]:De corta duración" o "pasajero", algo que dura muy poco tiempo, como un instante, o que tiene la duración de un solo día; sus sinónimos son fugaz, breve, momentáneo, transitorio o perecedero, mientras que sus antónimos son duradero, perdurable o eterno, y también puede referirse a un fenómeno físico o biológico que ocurre en un breve intervalo de tiempo

[^2]:Algo dulce y delicado, a menudo refiriéndose a la manera de hablar o a los sonidos, y frecuentemente se usa con un sentido peyorativo para indicar una delicadeza exagerada o afectada, como en "un tono melifluo irritante" o "un discurso melifluo y empalagoso". 

  
 