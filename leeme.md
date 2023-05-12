#Problemas

Todavía está patas pa'rriba, pero ya es utilizable,



Al parecer no es posible programáticamente agregar archivos (file objects) a un input, pero hay de tres:

1. Puedes agregarlos manualmente cuando vayas a enviar la http request:

```js
const formData = new FormData();
formData.append('file', file); //habría que haerlo para cada file en el array fileListAdHoc
```

En el array`fileListAdHoc` están los file objects de las imágenes (formato webp, que se pueden abrir con un navegador web)

2. Las puedes guardar como dataURL: es decir como una cadena de caracteres de una URL encodifican toda la imágen. En el archivo [imgProblem.html](imgProblem.html) se puede ver como el elemento `<img>` usa de `src` esa cadenota de caracteres, y así se puede usar para despegar las imágenes. Esa dataURL se puede guardar como varchar en sql y no mas poner ese valor en el `src` del `<img>`. Los valores de las imágenes en dataURL están en el array `webpURLArrAdHoc`, de ahí igual te los mandas con la request de la form.

3. Es convertir el dataUrl a blob, con la función `url2Blob`, y ya mysql tiene un datatype de [blob](https://dev.mysql.com/doc/refman/8.0/en/blob.html). Ese habría que reconvertirlo a dataURL


Probablemente lo más fácil sea el dos, o el uno, pero igual los dos requerirían algo más de código. Le podría intentar la próxima semana para ya integrarlo con lo que tienes, de mientras, aquí va.

¡Saludos!