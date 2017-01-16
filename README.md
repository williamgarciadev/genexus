# Guia de estilo para el desarrollo en GeneXus de Sincrum {

## Tabla de Contenidos

  1. [Definición de nombres](#definición-de-nombres)
  1. [Dominios enumerados](#dominios-enumerados)
  1. [Identación](#identación)
  1. [Contributors](#contributors)
  1. [License](#license)

## Definición de nombres

  <a name="naming--descriptive"></a><a name="1.1"></a>
  - [1.1](#naming--descriptive) Se debe ser descriptivo con los nombres.

    ```foxpro
    // mal
    Proc: CliCre

    // bien
    Proc: ClienteCrear
    ```

  <a name="naming--camelCase"></a><a name="1.2"></a>
  - [1.2](#naming--PascalCase) Utilizar PascalCase al nombrar objetos, atributos y variables.

    ```foxpro
    // mal
    clientecrear

    // bien
    ClienteCrear
    ```

  <a name="naming--commands"></a><a name="1.3"></a>
  - [1.3](#naming--commands) Utilizar minúsculas al nombrar comandos.
	> Se intenta reservar la utilización de CASE en los casos que se necesite dar sentido a una entidad, ej. Variables, Atributos y Objetos.

    ```foxpro
    // mal
    For Each
    	Where CliCod = &CliCod
        Msg(CliNom)
    EndFor

    // bien
    for each
    	where CliCod = &CliCod
        msg(CliNom)
    endfor
    ```

  <a name="naming--leading-underscore"></a><a name="1.4"></a>
  - [1.4](#naming--leading-underscore) No utilizar underscore al inicio o final en ningún tipo de objeto, atributo o variable. 

    > Esto puede hacer suponer a un programador proveniente de otros lenguajes que tiene algún significado de privacidad.

    ```foxpro
    // mal
    &_CliNom = "John Doe"
    &CliNom_ = "John Doe"
    Proc: _ClienteCrear

    // bien
    &CliNom = "John Doe"
    ```

  <a name="naming--enums"></a><a name="1.5"></a>
  - [1.5](#naming--enums) Nombrar los dominios enumerados comenzando con la entidad en singular y siguiendo con el enumerado en plural sin abreviar estos.

    ```javascript
    // mal
    DocumentoTipo
    DocumentosTipos
    DocTipos
    
    // bien
    DocumentoTipos (Venta,Compra,etc)
    DocumentoModos (Credito, Débito)
    ```

**[⬆ back to top](#table-of-contents)**


## Identación
  <a name="enums--use"></a><a name="2.1"></a>
  - [2.1](#enums--use) Utilizar una identación/tabulación de 3 espacios.
    > Esto es porque la mayoría de los comandos queda mas legibles con esta tabulación.

	 ```javascript
    // mal
    if &DocumentoTipo = DocumentoTipos.Venta
    msg("Venta")
    endif

    // mal
    if &DocumentoTipo = DocumentoTipos.Venta
      msg("Venta")
    endif

    // mal
    if &DocumentoTipo = DocumentoTipos.Venta
        msg("Venta")
    endif

    // bien
    if &DocumentoTipo = DocumentoTipos.Venta
       msg("Venta")
    endif
    ```

  <a name="enums--use"></a><a name="2.2"></a>
  - [2.2](#enums--use) Se deben identar las condiciónes y comandos dentro de un for each.

	 ```javascript
    // mal
    for each
    where DocumentoTipo = DocumentoTipos.Venta
    ...
    endfor

    // mal
    for each
    defined by ClienteNombre
    ...
    endfor

    // bien
    for each
    	where DocumentoTipo = DocumentoTipos.Venta
    	...
    endfor
    ```

**[⬆ back to top](#table-of-contents)**

## Dominios enumerados
  <a name="enums--use"></a><a name="3.1"></a>
  - [3.1](#enums--use) Evitar la utilización de textos/números fijos cuando pueden existir multiples opciones.
    > Simplificar la lectura y no necesitar recordar el texto específico de cada opción.

    ```javascript
    // mal
    if &HttpResponse = "GET"
    
    // bien
    if &HttpResponse = HttpMethods.Get
    ```

**[⬆ back to top](#table-of-contents)**

## Resources

**Further Reading**

  - [GeneXus Wiki](http://wiki.genexus.com/) - GeneXus

## Contributors

  - You are welcome


## License

[The MIT License](LICENSE)

**[⬆ back to top](#table-of-contents)**

# };