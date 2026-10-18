# lab-builder: construye imágenes de laboratorios de contenedores desde el repositorio público de GitHub de un profesor

[English](README.md) | [Français](README.fr.md) | [日本語](README.ja.md) | [Español](README.es.md)

Construye los servicios de un [laboratorio de contenedores de MitsuruTech](https://mitsurutech.co.uk/es/help/labs) a partir del
repositorio público de GitHub de un profesor, y publica cada imagen en
[`ghcr.io/mitsurutech/lab-images`](https://github.com/orgs/mitsurutech/packages/container/package/lab-images).

Un laboratorio es un conjunto de contenedores descrito por un archivo compose. Cuando un profesor publica un commit
de un laboratorio cuyo archivo compose dice `build:`, el sitio lanza aquí `Build a lab image` una vez
por cada servicio que se construye. La imagen lleva la etiqueta `<lab>-<service>-<commit>`, y las máquinas del laboratorio la descargan
de aquí. Ningún Dockerfile de un profesor se ejecuta nunca en una máquina del laboratorio.

**Lo que se publica es público.** Solo se construyen repositorios públicos. Cualquier cosa que un Dockerfile
copie, y cualquier valor que fije con `ENV` o `ARG`, lo puede leer cualquiera que descargue la
imagen: guarda los secretos en un `env_file`, que el sitio añade cuando arranca una copia y que
nunca se integra en la imagen.

Las construcciones se ejecutan en los ejecutores de GitHub, lanzadas solo por el sitio con un token que no puede
hacer nada más. Para avisar de una imagen que no debería estar aquí, escribe a la dirección de la
[página de contacto](https://mitsurutech.co.uk/es/contact) de mitsurutech.co.uk.

## Licencia

Esta obra está bajo licencia [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Puedes compartirla y adaptarla para aprender y enseñar, si citas a Mitsuru Technologies Ltd, no la usas comercialmente y compartes lo que hagas con ella bajo la misma licencia. El texto completo está en el archivo `LICENSE`.

## Acerca de

Hecho por [Mitsuru Technologies](https://mitsurutech.co.uk/es) para la
[plataforma de aprendizaje MitsuruTech](https://mitsurutech.co.uk/es/learning): Python, Java, Go, Node, SQL y
Linux en el navegador para escuelas y centros, con laboratorios de contenedores, aplicaciones web desplegadas desde GitHub y
cuestionarios que se califican solos. Prueba código sin cuenta en el
[entorno de pruebas](https://mitsurutech.co.uk/es/playground).

¿Das clase? Mira [el precio](https://mitsurutech.co.uk/es/pricing) o [crea una cuenta de centro](https://mitsurutech.co.uk/es/signup).
