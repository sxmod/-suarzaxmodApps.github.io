
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Localhost by Suarzaxmod</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #000; /* Fondo negro */
            color: #28a; /* Texto blanco */
            margin: 0;
            padding: 0; /* Eliminar padding del body */
            box-sizing: border-box; /* Incluir bordes y padding en el tamaño total */
        }
        .banner {
            width: 100%;
            height: 150px; /* Altura ajustada del banner principal */
            margin-bottom: 10px; /* Menos margen inferior */
            overflow: hidden; /* Ocultar cualquier contenido que sobresalga */
        }
        .banner img {
            width: 100%;
            height: 100%; /* Ajustar a la altura del banner */
            object-fit: contain; /* Mantener la proporción de la imagen */
            border-radius: 10px;
        }
        h1 {
            color: #28a745; /* Color de acento */
            text-align: center;
            margin: 10px 0; /* Menos margen alrededor del título */
            font-size: 1.8rem; /* Tamaño reducido del título */
        }
        .slider-container {
            position: relative; /* Posicionamiento relativo para el contenedor */
            margin-bottom: 10px; /* Menos margen inferior */
            overflow: hidden; /* Ocultar contenido que sobresalga */
            height: 140px; /* Altura del slider ajustada para acomodar los títulos */
        }
        .slider {
            display: flex; /* Usar flexbox para el slider */
            transition: transform 0.5s ease; /* Transición suave para el desplazamiento */
        }
        .slider-item {
            min-width: calc(52.5% - 19px); /* Cada item ocupará el 50% del contenedor menos el margen */
            height: 100%; /* Altura completa */
            position: relative; /* Posicionamiento relativo para el título */
            margin-right: 10px; /* Espacio entre los banners */
            border-radius: 20px; /* Bordes redondeados */
            overflow: hidden; /* Ocultar contenido que sobresalga */
        }
        .slider img {
            width: 100%; /* Ajustar imagen al ancho */
            height: 100%; /* Ajustar imagen a la altura del banner */
            object-fit: cover; /* Mantener proporciones de la imagen y cubrir */
            border-radius: 20px; /* Bordes redondeados */
            transition: transform 0.3s ease; /* Transición suave para el efecto */
        }
        .slider-item:active img {
            transform: scale(1.5); /* Aumentar el tamaño al hacer clic */
        }
        .slider-title {
            position: absolute; /* Posicionamiento absoluto para el título */
            bottom: 10px; /* Espacio desde la parte inferior */
            left: 60%; /* Centrar horizontalmente */
            transform: translateX(-50%); /* Ajustar a la izquierda para centrar */
            color: #982245; /* Color del texto */
            font-size: 1.05rem; /* Tamaño del título */
            text-shadow: 1px 2px 5px rgba(0, 0, 0, 0.7); /* Sombra para mejorar legibilidad */
            text-align: center; /* Alinear texto al centro */
        }
        .sections-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center; /* Centrar secciones */
            gap: 10px; /* Espacio entre secciones */
            padding: 0 10px; /* Padding horizontal para evitar que los elementos toquen los bordes */
            margin-top: 10px; /* Ajustar margen superior */
        }
        .section {
            background: #000; /* Fondo de secciones más oscuro */
            border-radius: 10px;
            box-shadow: 4px 5px 8px rgba(250, 250, 250, 0.1);
            padding: 20px; /* Menos padding */
            width: calc(50% - 20px); /* Ancho adaptable */
            text-align: center;
            transition: transform 0.3s; /* Efecto al pasar el mouse */
            cursor: pointer; /* Cambia el cursor al pasar sobre la sección */
        }
        .section:active {
            transform: scale(1.2); /* Efecto son click más sutil */
            object-fit: cover; /* Mantener proporciones de la imagen */
        }
        .section img {
            width: 100%;
            border-radius: 9px;
            transition: transform 0.3s ease; /* Transición suave para el efecto */
        }
        .section h2 {
            color: #28a745; /* Color de título */
            margin: 5px 0; /* Menos margen */
            font-size: 1.2rem; /* Tamaño reducido del subtítulo */
        }
        .footer-text {
            text-align: center; /* Centrar el texto */
            margin-top: 10px; /* Espacio superior */
            font-size: 0.9rem; /* Tamaño del texto */
            color: #000; /* Color gris claro para el texto */
        }
        .separator-container {
            margin: 7px 0; /* Espacio superior e inferior para los separadores */
            text-align: center; /* Centrar los enlaces */
        }
        .separator-container img {
            width: 100%; /* Ancho completo para el separador */
            height: auto; /* Mantener la proporción del separador */
            max-width: 300px; /* Ancho máximo para el separador */
        }
        .suggestions-container {
            display: flex;
            justify-content: center; /* Centrar banners */
            gap: 10px; /* Espacio entre banners */
            margin-top: 15px; /* Espacio superior */
        }
        .suggestion-banner {
            background: #000; /* Fondo de la tarjeta */
            border-radius: 9px;
            padding: 9px;
            width: calc(20% - 9px); /* Ancho adaptable para 4 banners */
            text-align: center; /* Centrar texto */
            cursor: pointer; /* Cambiar cursor al pasar sobre la tarjeta */
            transition: transform 0.3s; /* Transición para efecto hover */
        }
        .suggestion-banner:active {
            transform: scale(1.1); /* Aumentar el tamaño al pasar el mouse */
        }
        .suggestion-banner img {
            width: 100%; /* Ajustar imagen al ancho */
            height: 70px; /* Altura fija para las imágenes */
            object-fit: cover; /* Mantener proporciones de la imagen */
            border-radius: 10px; /* Bordes redondeados */
        }
        .suggestion-banner h2 {
            color: #28a; /* Color del texto */
            font-size: 1rem; /* Tamaño del texto */
            margin-top: 5px; /* Margen superior del título */
        }
        
        /* Media Queries para responsive design */
        @media (max-width: 1200px) {
            .section {
                width: calc(100% - 5px); /* Secciones ocupan 1/3 del ancho en pantallas grandes */
            }
        }

        @media (max-width: 800px) {
            .section {
                width: calc(50% - 20px); /* Secciones ocupan 1/2 del ancho en pantallas medianas */
            }
            .suggestion-banner {
                width: calc(48% - 10px); /* Ancho adaptable para móviles */
            }
        }

        @media (max-width: 600px) {
            .section {
                width: 100%; /* En pantallas más pequeñas, las secciones ocupan el 100% */
            }
            .suggestion-banner {
                width: 100%; /* Ancho completo para las sugerencias en móviles */
                height: auto; /* Mantener proporción */
            }
        }
    </style>
</head>
<body>

<h1>Apoya este proyecto</h1>

<div class="banner">
    <img src="https://i30.servimg.com/u/f30/20/30/93/75/d3fe1410.gif" alt="Banner Tienda de Aplicaciones">
</div>

<h1>Recomendaciones y Socios</h1>

<p class="footer-text">
    Recuerda que al entrar a las secciones recomendadas por nuestros socios ya accedes a una extensión donde las políticas de la aplicación cambian.<br>
    Derechos reservados por Suarzaxmod Corporation ™.
</p>

<!-- Nuevo Slider de Banners -->
<div class="slider-container">
    <div class="slider" id="newSlider">
        <div class="slider-item" onclick="window.location.href='go:Apks'">
            <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjguqgHtRCzHj-227IPIZorftpybavFzRQXkXHaEW5i7NOAwME7HuLbgpi5gTzK6H1gZTILb1vzjLMu5iWawckV6J8PGCy4f56eHJdM6-tkV5b-bvh7llSNbIMGkiLgd11hFcoXH6E-F5nLdAiGmLWSwXi96Y4jSWuN1tevWvciE4IZmhs8LkLX7wwISkc/s400/MP4_20240901_012253VLOG.gif" alt="Suarzaxmod apps">
            <div class="slider-title">Suarzaxmod apps</div>
        </div>
        <div class="slider-item" onclick="window.location.href='https://apkgstore.com/'">
            <img src="https://i30.servimg.com/u/f30/20/30/93/75/apkgst10.jpg" alt="Apkgstore">
            <div class="slider-title">ApkGstore</div>
        </div>
        <div class="slider-item" onclick="window.location.href='https://espacioapk.com/'">
            <img src="https://i30.servimg.com/u/f30/20/30/93/75/espaci10.jpg" alt="espacioapk">
            <div class="slider-title">Espacio apks</div>
        </div>
        <div class="slider-item" onclick="window.location.href='https://modilimitado.io/'">
            <img src="https://i30.servimg.com/u/f30/20/30/93/75/com_na10.jpg" alt="modilimitado">
            <div class="slider-title">Modilimitado apks</div>
        </div>
        <div class="slider-item" onclick="window.location.href='https://allmodapk.de/'">
            <img src="https://i30.servimg.com/u/f30/20/30/93/75/allmod10.jpg" alt="allmodapk">
            <div class="slider-title">Allá mod apks</div>
        </div>
        <div class="slider-item" onclick="window.location.href='https://getmodsapk.com/'">
            <img src="https://i30.servimg.com/u/f30/20/30/93/75/how-to10.jpg" alt="getmodsapk">
            <div class="slider-title">Getmods apks</div>
        </div>
    </div>
</div>

<h1>Sugerencias</h1>
<div class="suggestions-container">
    <div class="suggestion-banner" onclick="window.location.href='https://ejemplo1.com'">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/d3fe1410.gif" alt="Sugerencia 1">
        <h2>Sugerencia 1</h2>
    </div>
    <div class="suggestion-banner" onclick="window.location.href='https://ejemplo2.com'">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/d3fe1410.gif" alt="Sugerencia 2">
        <h2>Sugerencia 2</h2>
    </div>
    <div class="suggestion-banner" onclick="window.location.href='https://ejemplo3.com'">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/d3fe1410.gif" alt="Sugerencia 3">
        <h2>Sugerencia 3</h2>
    </div>
    <div class="suggestion-banner" onclick="window.location.href='https://ejemplo4.com'">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/d3fe1410.gif" alt="Sugerencia 4">
        <h2>Sugerencia 4</h2>
    </div>
</div>

<h1>Tal vez sea de tu interés</h1>
<div class="separator-container">
    <img src="https://i30.servimg.com/u/f30/20/30/93/75/separa10.gif" alt="separador">
</div>
<div class="sections-container">
    <div class="section" onclick="zoomIn(this); setTimeout(() => { window.location.href='go:Libros'; }, 300);">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/tenor-10.gif" alt="Libros">
        <h2>Libros (PDF)</h2>
        <p>Encuentra los mejores libros en formato PDF. Derechos reservados por Suarzaxmod Corporation ™.</p>
    </div>

    <div class="separator-container">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/separa10.gif" alt="separador">
    </div>

    <div class="section" onclick="zoomIn(this); setTimeout(() => { window.location.href='go:Apks'; }, 300);">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/softwa10.gif" alt="Aplicaciones">
        <h2>Aplicaciones (APK)</h2>
        <p>Descarga aplicaciones increíbles Derechos reservados por Suarzaxmod Corporation™.</p>
    </div>

    <div class="separator-container">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/separa10.gif" alt="separador">
    </div>

    <div class="section" onclick="zoomIn(this); setTimeout(() => { window.location.href='go:Lista'; }, 300);">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/iptv10.gif" alt="M3U">
        <h2>M3U</h2>
        <p>Accede a listas M3U para tus servicios Derechos reservados por Suarzaxmod Corporation™.</p>
    </div>

    <div class="separator-container">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/separa10.gif" alt="separador">
    </div>

    <div class="section" onclick="zoomIn(this); setTimeout(() => { window.location.href='go:Electricid'; }, 300);">
        <img src="https://i30.servimg.com/u/f30/20/30/93/75/dc-aut10.gif" alt="Electricidad">
        <h2>Electricidad</h2>
        <p>Recursos y archivos sobre electricidad Derechos reservados por Suarzaxmod Corporation™.</p>
    </div>
</div>

<script>
    let newSlideIndex = 0;

    function moveNewSlider() {
        const newSlider = document.getElementById('newSlider');
        newSlideIndex++;
        if (newSlideIndex >= 5) { // Cambia este valor según la cantidad de elementos en el slider
            newSlideIndex = 0;
        }
        newSlider.style.transform = `translateX(-${newSlideIndex * 50}%)`; // Cambiar a 50% para mostrar dos banners
    }

    // Iniciar el movimiento del slider cada 8 segundos
    setInterval(moveNewSlider, 8000);

    // Funciones para el efecto de zoom y redirección
    function zoomIn(element) {
        element.style.transform = 'scale(1.1)'; // Aumentar el tamaño al hacer clic
    }
</script>

</body>
</html>
