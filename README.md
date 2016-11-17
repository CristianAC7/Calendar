### Escuela Colombiana de Ingeniería
### Taller Bluemix
### Clonar, editar y desplegar una Aplicación en Bluemix


Este ejercicio se basa en la documentación oficial de Bluemix, para el [despliegue de una app](https://hub.jazz.net/tutorials/devopsweb/).

En este repositorio se encuentra una aplicación que está desarrollada en Ruby on Rails, un entorno de desarrollo web de código abierto que está optimizado para la satisfacción de los programadores y para la productividad sostenible.

## Parte I.


1. Seleccione la opción clone or download en la parte superior y copie la dirrección, ingrese a la consola del sistema y ejecute el siguiente comando:

	```bash
	git clone URL
    ```

2. Ingrese a la carpeta del proyecto e inicie el servidor de Rails con:

	```bash
	Rails s
```
3. Abra el navagador y digite la dirección localhost:3000. La aplicación debe poder visualizarse.
4. Ingrese los datos, ejecute la acción del botón, y verifique que en todas la pestañas se haya lanzado la alerta con los datos ingresados.
5. Haga commit de lo realizado, y agregue un TAG para demarcar el avance de la parte 1:

	```bash
git tag -a v0.1 -m "Parte1"
	```

## Parte II.

Ahora se va crear una aplicación en Bluemix para desplegar la aplicación.

1. Ingrese a su cuenta en Bluemix ingresando [aqui](https://console.ng.bluemix.net/).
2. Seleccione Create Application, en la parte izquierda seleccione Cloud Foundry Apps y seleccione Ruby.
3. En App name: seleccione un nombre para la aplicación y en la parte de abajo, seleccione Create.
4. Regrese a la página principal y seleccione la aplicación que acabo de crear y en la parte inferior en Continuous Delivery seleccione Click here.
5. Deseleccione la opción Llene el repositorio con el paquete de app de iniciador y habilite Build & Deploy Pipeline, seleccione Continuar y cerrar.

## Parte III.

En la configuración anterior, se creo la aplicación en Bluemix ahora se va a desplegar con el codigo que se descargo en la parte I.

1. Seleccione Edit code.
2. Seleccione un alias fácil de recordar ya que se utilizara mas adelante, seleccione Create y por ultimo Continue.
3. Seleccione en la parte superior derecha BUILD & DEPLOY.
4. En este paso se va a configurar la compilación y el despliegue, cuando se haga un cambio en el repositorio.
5. Seleccione Add Stage.
6. Cambie el nombre a Build, luego seleccione la segunda pestaña llamada JOBS, seleccione ADD JOB, Build.
7. Seleccione Save
8. Seleccione Add Stage.
9. Cambie el nombre a Deploy, luego seleccione la segunda pestaña llamada JOBS, seleccione ADD JOB, Deploy.
10. Seleccione Save.

## Parte IV.

En este momento la aplicación aun no ha sido empujada al repositorio en esta parte se hara el despliegue final.

1. En el menu superior seleccione DASHBOARD para volver al tablero de Bluemix, seleccione la aplicación que acabo de crear y copie el GIT URL que se enceuntra en la parte de abajo.
2. Abra la consola y ejecute
```bash
git remote add bluemix GIT URL
```
```bash
git push -u bluemix
```