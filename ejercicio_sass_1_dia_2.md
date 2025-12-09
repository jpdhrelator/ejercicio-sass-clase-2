# 🎓 Tarea Práctica: "Las Tarjetas del Equipo Digital"

## 1. Preparación del Entorno

Crea una carpeta nueva para tu proyecto. Dentro, debes replicar la Arquitectura 7-1 (Simplificada).

Tu estructura de archivos debe verse así (créalos vacíos por ahora):

```text
/mi-proyecto
  index.html
  /scss
    main.scss                (Archivo principal)
    /abstracts
       _variables.scss       (Aquí irán los colores y fuentes)
       _mixins.scss          (Aquí irán tus herramientas reutilizables)
    /base
       _reset.scss           (Estilos básicos del body)
    /components
       _team-card.scss       (Todo el estilo de la tarjeta)
```

## 2. El HTML (Ya listo)

Copia y pega este código en tu index.html. Observa las clases: Usan BEM (block__element--modifier). Hay tres tarjetas, cada una con un modificador diferente: --design, --code, --marketing.

```html
<!DOCTYPE html>
   <html lang="es">
   <head>
      <meta charset="UTF-8">
      <title>Equipo Digital</title>
      <link rel="stylesheet" href="css/main.css">
   </head>
   <body>

    <main class="team-section">
        <h1 class="main-title">Conoce al Equipo</h1>
        
        <div class="grid-container">
            
            <article class="profile profile--design">
                <header class="profile__header">
                    <h2 class="profile__role">Diseño UI</h2>
                    <h3 class="profile__name">Ana López</h3>
                </header>
                <div class="profile__body">
                    <p>Experta en interfaces limpias y experiencia de usuario.</p>
                    <button class="profile__btn">Ver Portfolio</button>
                </div>
            </article>

            <article class="profile profile--code">
                <header class="profile__header">
                    <h2 class="profile__role">Desarrollo</h2>
                    <h3 class="profile__name">Carlos Dev</h3>
                </header>
                <div class="profile__body">
                    <p>Especialista en Backend Java y arquitecturas escalables.</p>
                    <button class="profile__btn">Ver GitHub</button>
                </div>
            </article>

            <article class="profile profile--marketing">
                <header class="profile__header">
                    <h2 class="profile__role">Marketing</h2>
                    <h3 class="profile__name">Sara Social</h3>
                </header>
                <div class="profile__body">
                    <p>Estratega de redes sociales y crecimiento orgánico.</p>
                    <button class="profile__btn">Contactar</button>
                </div>
            </article>

        </div>
    </main>

   </body>
</html>
```

## 3. Instrucciones de Estilo (Paso a Paso)
Sigue estos pasos en orden. Recuerda usar @use para conectar tus archivos.

### Paso A: Variables (abstracts/_variables.scss)
Define las siguientes variables:

1) Una fuente principal (ej: Helvetica, Arial).

2) Un color de fondo para la página (gris claro).

3) Tres colores específicos para los roles:

    * Uno para Diseño (ej: rosa/fucsia).

    * Uno para Código (ej: azul).

    * Uno para Marketing (ej: naranja).

### Paso B: Mixins (abstracts/_mixins.scss)
Aquí crearás dos mixins:

1) Mixin de Estructura: Uno llamado card-base que tenga el borde redondeado (ej: 10px), el fondo blanco, el padding (ej: 20px) y una sombra suave.

2) Mixin de Tema (El más importante): Crea un mixin llamado apply-theme que reciba un argumento (una variable de color).

    * Este mixin debe pintar el borde superior de la tarjeta con ese color.

    * Debe pintar el texto del "Rol" (h2) con ese color.

    * Debe pintar el fondo del botón con ese color.

    * Pista: mixin apply-theme($color-recibido) { ... }

### Paso C: Estilos Base (base/_reset.scss)
Escribe estilos simples para el body:

* Quita los márgenes por defecto.

* Aplica la fuente que definiste en variables.

* Aplica el color de fondo de página.


### Paso D: El Componente (components/_team-card.scss)
Aquí es donde debes usar BEM.

1) Importa tus variables y mixins al principio del archivo con @use.

2) Estila la clase .profile. Usa el mixin card-base para darle la forma básica.

3) Estila los elementos internos (__header, __name, __body, __btn) para que se vean ordenados.

4) Aplica los modificadores manualmente:

    * Dentro de &--design, llama al mixin apply-theme pasándole la variable de color de diseño.

    * Dentro de &--code, llama al mixin apply-theme pasándole la variable de color de código.

    * Haz lo mismo para marketing.

### Paso E: Unificar todo (main.scss)
1) Usa @use para llamar al archivo de reset.

2) Usa @use para llamar al archivo del componente team-card.

3) No escribas nada más aquí.