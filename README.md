# Acerca de

Este repositorio contiene un conjunto de archivos que definen una template para generar tesis en la UDP.

Adicionalmente, la clase contiene varios macros para facilitar la escritura de su tesis. Vea la sección de [Macros](#macros)

# Archivos

* `udpthesis.cls`: Es la template que debe incluirse para pode generar el documento.
* `udpthesisEIT.sty`: Es el tema donde se define la configuración para utilizar la template en la EIT.
* `udpthesisEIT-MS.sty`: Es el tema donde se define la configuración para utilizar la template del magíster en la EIT.
* Carpeta `ejemplo`: Contiene un conjunto de archivos que demuestran el uso de la template.

## Ejemplo

Para ejecutar el ejemplo reproduzca la siguiente secuencia (sin el signo $) para obtener el PDF de ejemplo, o en su IDE de preferencia.

```bash
$ pdflatex thesis
$ bibtex thesis
$ pdflatex thesis
```

# Instalación

El archivo de la clases (`udpthesis.cls`), y el(los) estilo(s) de los respectivos temas (ej., `udpthesisEIT.sty`) deben de desplegarse en un directorio que semeje su instalación de LaTeX. Por lo general dicho despliegue se realiza en el local texmf de su sistema TeX.

Por ejemplo, puede instalarlos en un directorio `~/texmf/tex/latex/udp-thesis`, donde el directorio `udp-thesis` puede tener el nombre que le parezca. Note que de no existir dicha estructura (`~/texmf/tex/latex/`) debe crearla. Dentro de la última carpeta `latex` usted puede crear carpetas que tengan cualquier nombre para almacenar clases y estilos.

Para más información sobre el establecimiento de un local texmf en su sistema revise la documentación del sistema TeX que instaló.


## Generación de estilos

En caso necesite generar un nuevo estilo, puede utilizar el estilo incluido (`udpthesisEIT.sty`) como base.

Note que debe de definir las cadenas correspondientes al nombre de la institución utilizando:
```tex
\udpschool{Escuela de Foo}
\udpfaculty{Facultad de Bar}
\degree{Ingeniero Foo en Bar}
```

Adicionalmente, puede cambiar las cadenas que aparecen en la portada del grado y del tipo de la tesis utilizando:
```tex
\degreetext{t\'{i}tulo}% o grado
\thesistype{Tesis}% o Memoria
\professortext{Profesor gu\'{i}a}
\committeetext{Comit\'{e}}
```

Si desea alterar el logo que está en las portadas, puede hacerlo estableciendo el macro `\logoXXX`, donde `XXX` es el nombre que desea darle a su logo de la siguiente manera
```tex
\def\logoXXX{\macroDelLogo}
```

donde `\macroDelLogo` es un macro que contiene el logo, en el caso de éstos ejemplos, se utilizó `tikz` para generarlos (ver detalle dentro de `udpthesisEIT.sty`).

# Macros

La clase `udpthesis.cls` provee los siguientes macros para ayudarle a escribir su tesis:
* `\eg` inserta la abreviación *e.g.*, y su versión en mayúsculas `\Eg`, que inserta *E.g.*. Ambas significan *por ejemplo*, del latín *exampli gratia*.
* `\ie` inserta la abreviación *i.e.*, y su versión en mayúsculas `\Ie`, que inserta *I.e.*. Ambas significan *en esencia* o *en otras palabras*, del latín *id est*. Sirve para aclarar algo, no para introducir ejemplos.
* `\cf` inserta la abreviación *cf.*, y su versión en mayúsculas `\Cf`, que inserta *Cf.*. Ambas significan *compare* o *ver*, del latín *confer*. Sirve para comparar la cláusula que le precede con otra que se coloca después. A pesar que el significado *ver* es usado ammpliamente, el *Manual de Estilo de Chicago* no defiende ese significado.
* `\etal` inserta la abreviación *et al.*. Que significa *y otros*, del latín *et alii*. Sirve para comprimir el número de autores al citarlos cuando el documento a citar tiene 3 o más autores.
* `\etc` inserta la abreviación *etc.*. Que significa *etcétera* o *y otras cosas*, del latín *et cetera*. Sirve para interrumpir el discurso indicando que en él se omite lo que quedaba por decir y esto se pude sobreentender.
* `\adhoc` inserta las palabras en latín *ad hoc*, que significa *para esto*. Sirve expresar que una solución esta diseñada a la medida del problema en específico, no es generalizable, y no se pretende que sea extensible a otros propósitos.
* `\wrt` inserta la abreviación *w.r.t.*. Que significa *con respecto a*, del inglés *with respect to*. Sirve para contextualizar la cláusula donde se usa.

