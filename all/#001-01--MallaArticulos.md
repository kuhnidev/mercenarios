# `#001-01` MallaArticulos

31 de diciembre de 2019 (**$0 MXN**)

## Piezas relacionadas

(_Sin dependencias_)

## Diseño

![diseño de la pieza](@001-01.d1.png)

## Funcionalidades

* Se muestra un contenedor con borde que contiene tres regiones, arriba el `Selector de Vista`, al centro el `Selector de Artículo` y abajo el `Configurador de Artículo`.
* El contenedor principal tiene 100% de alto y con _scroll_ deshabilitado.
* El `Selector de Artículo` posee _scroll_ vertical.
* En el `Selector de Vista` aparecen dos íconos: [border-all](https://fontawesome.com/icons/border-all?style=solid) y [list-alt](https://fontawesome.com/icons/list-alt?style=regular) de los cuales el primero está seleccionado y color primario y el segundo en color secundario. 
* Cuándo se pulsa el otro cambia el `modoVista` del estado y llamar a `onModoVistaCambiado`.
* En el `Selector de Artículo` se muestra la lista de artículos (entrada `articulos`). Si el `modo de vista` es `"tarjetas"` se muestran tarjetas y se manda a llamar el método `renderArticulo($modoVista, articulo, $articuloSeleccionado)` en caso que haya sido definido (descrito en el protocolo de entrada), pasando el artículo (estructura de datos `Articulo`) y el artículo seleccionado con misma estructura. Si no hay artículos mostrar una leyenda centrada.
* Al seleccionar un artículo se debe cambiar el `articuloSeleccionado` del estado y llamar `onArticuloSeleccionado`. Si el artículo es el mismo que el seleccionado se debe entonces poner `articuloSeleccionado` a `null`. 
* En el `Configurador de Artículo` se manda a llamar el método `renderConfigurarArticulo(articuloSeleccionado, onArticuloConfigurado)`, el cuál se describe en el protocolo de entrada.

## Protocolo

__Estructuras de datos__

`Articulo` - Representa un objeto _json_ con estructura libre.

``` json
{
    ...
}
```

`modoVista` - Texto, puede ser `"tarjetas"` o `"detalles"` 

__Entrada__

`articulos [Opcional]` - Representa un arreglo de objetos `Articulo` los cuáles contienen la información de los artículos que serán colocados en la malla.

``` json
[
    {
        ...
    },
    {
        ...
    },
    {
        ...
    },
    ...
]
```

`renderArticulo (modoVista, ) [Opcional]` - Representa un arreglo de objetos `ColorBox` los cuáles contienen la información de la caja de color.

``` json
[
    {
        "name": "Rojo",
        "color": "#FF0000"
    },
    {
        "name": "Azúl",
        "color": "rgb(0, 0, 255)"
    },
    ...
]
```

__Salida__

`onTallaColorChange (tallaBox, colorBox, talla, color) [Opcional]` - Representa una función que se llama cuándo el usuario selecciona una caja cambiando la talla o cambiando el color, el primer parámetro será el objeto idéntico de la caja de talla (el `TallaBox` asociado al arreglo `tallas`), el segundo parámetro será la caja asociada al color (el `ColorBox`), el tercer parámetro serán las siglas de la talla (el _string_ de la propiedad `TallaBox.sign`) y como cuarto parámetro será el color seleccionado (el _string_ de la propiedad `ColorBox.color` ).

## Pruebas Unitarias

* __Test 1__ - Probar el componente sin parámetros de entrada
* __Test 2__ - Probar el componente con `tallas` arreglo vacío
* __Test 3__ - Probar el componente con `colores` arreglo vacío
* __Test 4__ - Probar el componente con `tallas` y `colores` arreglos vacío
* __Test 5__ - Probar el componente con 3 tallas y 4 colores diferentes.
* __Test 6__ - Probar el componente con 6 tallas y 8 colores diferentes.
* __Test 6__ - Probar el componente con 6 tallas y 128 colores diferentes aleatorios.
* __Test 7__ - Probar el componente con tallas y colores diferentes y mostrar una alerta con los datos de las cajas (nombre de talla y color) cada que cambie.

## Complejidad

### __Diseño__ (12/6)

| Descripción | Indicador | Valoración |
| --- | :-: | :-: |
| Profundidad máxima | 4 | 1 |
| Maquetación dinámica | &#x2713; | 4 |
| Responsivo | &#x2713; | 4 |
| Controles personalizados | &#x2715; | 1 |
| Efectos animados | &#x2715; | 1 |
| Ajustes de región  | &#x2715; | 1 |

### __Funcionalidad__ (6/6)

| Descripción | Indicador | Valoración |
| --- | :-: | :-: |
| Fórmulas matemáticas | &#x2715; | 1 |
| Validaciones de estado | &#x2713; | 1 |
| Almacenamiento local | &#x2715; | 1 |
| Temporizadores | &#x2715; | 1 |
| Sincronización | &#x2715; | 1 |
| APIs externas | &#x2715; | 1 |

### __Construcción__ (7/6)

| Descripción | Indicador | Valoración |
| --- | :-: | :-: |
| Estado | &#x2713; | 2 |
| Efectos | &#x2715; | 1 |
| Reductores | &#x2715; | 1 |
| Contexto | &#x2715; | 1 |
| Hooks personalizados | &#x2715; | 1 |
| Memorización | &#x2715; | 1 |

### __Pruebas unitarias__ (5/4)

| Descripción | Indicador | Valoración |
| --- | :-: | :-: |
| Generación de datos aleatorios | &#x2713; | 2 |
| Uso de componentes externos | &#x2715; | 1 |
| Creación de contexto de pruebas | &#x2715; | 1 |
| Creación de secuencia de pruebas | &#x2715; | 1 |

## Valor

> Complejidad total: **1.3541**

> Precio por complejidad: **$80 MNX**

> Valor total: **$109 MXN**

## Código

AES 256 bit (Código de pieza + Código de programador)

_No disponible_

## Video

_No disponible_