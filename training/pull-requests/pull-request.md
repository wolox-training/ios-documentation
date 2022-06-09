# Pull Request & Code Review 

El objetivo de este documento es describir qué es un pull request y el code review, dos piezas centrales en la métodología del desarrollo.

## Pull Request 
Un Pull Request (PR) es un pedido del creador de la branch para que el código sea incluido en la branch principal (generalmente se llama `master` o `development`, depende de cada proyecto). El PR debe seguir un template predeterminado, que incluye un título, una descripción, un link a su card y algunas screenshots o screencasts mostrando los cambios realizados.
 
Una vez creado el PR, es importante que asignes a tus capacitadores como reviewers y assignees, para que de esta forma pueden revisar tu código.  
 
### Pasos

1. Para hacer un PR, entra al repositorio de Git en GitHub. Como ejemplo, vamos a usar [cat-andersen-ios](https://github.com/Wolox/cat-andersen-ios).
2. Una vez ahí, anda a la solapa de Pull Request que está arriba. 
3. Paso siguiente, andá a "New Pull Request".
4. Luego, elegí la branch que queres mergear, seleccionándola de la lista que aparece abajo o del dropdown inicial. También seleccioná la branch a la que quieres que sea incluida tu trabajo.

Dropdown:

Lista:

5. Hecho esto, te va a mostrar los cambios realizados en tu branch que se van a agregar al branch base, y si podés hacerlo directamente, o no. Si estás seguro de hacerlo, entonces andá a "Create pull request". 
6. Una vez allí, se va a mostrar la siguiente pantalla, en la que vas a tener el template que tenes que completar con los datos del PR. No te olvides de agregar todas las cosas que allí son requeridas para que tu reviewer entienda qué está corrigiendo. Si tu trabajo consta de solo algo visual, podés añadir los screenshots y omitir el screencast, pero si implementaste alguna funcionalidad, debés incluir el screencast donde se muestre el flujo correspondiente. No es necesario que agregues screenshots con todos los modelos de iPhone o iPad, alcanza con que pongas los que creas más relevantes.  

Template vacío:

Template completo:

7. Finalmente, asigná a quienes vayan a revisar tu código, tanto en la parte de reviewers como en la parte de assignees.
 
## Code Review

El Code Review (CR) es la revisión del código que se hace sobre el pull request. Cuando tus capacitadores hayan revisado tu código, van a dejarte comentarios sobre cosas a cambiar o mejorar. Es importante entender que esta es una instancia de aprendizaje, pues todos esos comentarios que te hagan van a servirte en el futuro y para todos los proyectos en los que formes parte. Prestales mucha atención, sacate todas las dudas, preguntá todo lo que quieras. Aprovechá esta instancia lo más que puedas.

Cuando tu reviewer revise tu código, te va a dejar comentarios sobre cosas a mejorar, como este:

Una vez que haya dejado todos los comentarios necesarios para que tu código sea el mejor, va a decidir una de estas tres opciones:

- Approve: significa que el código está bien. Puede que tengas que hacer algunos cambios menores antes de mergearlo.
- Request changes: significa que el PR requiere cambios para que pueda aprobarse. Por lo tanto, todavía no se puede mergear. 
- Comment: significa que te están dejando comentarios en general, sin necesariamente aprobarlo ni desaprobarlo. 

Esta es la pantalla que completa tu reviewer: 

Para que puedas realizar el merge de tu branch, es necesario que tengas al menos un approve de alguno de tus reviewers. Por lo tanto, en caso que te hayan solicitado hacer algún cambio, debés: 

- Hacer las correcciones en el código.
- Hacer push a tu branch.
- Verificar que todo siga funcionando correctamente.
- Asignar nuevamente a tu reviewer para que sepa que has completado los cambios.
- Esperar el nuevo code review.

Una vez que tus cambios hayan sido aprobados, podrás realizar el merge a la base branch. Siempre verificá que no existan conflictos para realizar el merge, y que una vez realizado, que todo siga funcionando de forma correcta. 
