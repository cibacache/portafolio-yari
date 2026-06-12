# ymondaca1.github.io
Portafolio profesional 
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Portafolio Profesional</title>
    <style>
        /* --- VARIABLES Y CONFIGURACIÓN BASE --- */
        :root {
            --color-principal: #FFFFFF;
            --color-secundario: #000000;
            --color-neutro: #F4F4F4;
            --color-acento: #FF0055;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth; 
            font-family: 'Montserrat', 'Helvetica Neue', Arial, sans-serif;
            background-color: var(--color-principal);
            color: var(--color-secundario);
        }

        body {
            line-height: 1.2;
        }

        /* --- ENCABEZADO Y MENÚ FIJO --- */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            z-index: 1000;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-weight: 800;
            font-size: 1.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none;
            color: var(--color-secundario);
        }

        .logo span {
            color: var(--color-acento);
        }

        nav a {
            text-decoration: none;
            color: var(--color-secundario);
            font-weight: 700;
            font-size: 0.9rem;
            text-transform: uppercase;
            margin-left: 25px;
            transition: color 0.3s ease;
        }

        nav a:hover {
            color: var(--color-acento);
        }

        /* --- SECCIONES (ESTILOS GENERALES) --- */
        section {
            padding: 120px 50px 80px 50px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
        }

        .titulo-seccion {
            font-size: 2.5rem;
            text-transform: uppercase;
            font-weight: 800;
            margin-bottom: 30px;
            letter-spacing: 1px;
        }

        /* --- 1. SECCIÓN: INICIO (CON VIDEO DE YOUTUBE EN FONDO) --- */
        #inicio {
            position: relative;
            overflow: hidden;
            color: white;
            text-align: center;
            align-items: center;
            justify-content: center;
        }

        /* Contenedor del video que fuerza la proporción y lo estira al fondo */
        .contenedor-video-youtube {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none; /* Evita que el usuario haga clic o pause el video accidentalmente */
        }

        .contenedor-video-youtube iframe {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 100vw;
            height: 56.25vw; /* Proporción 16:9 ideal para pantallas panorámicas */
            min-height: 100vh;
            min-width: 177.77vh; /* Ajuste proporcional para pantallas altas */
            transform: translate(-50%, -50%);
        }

        .filtro-oscuro {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.55);
            z-index: 2;
        }

        .contenido-hero {
            position: relative;
            z-index: 3;
        }

        #inicio h1 {
            font-size: 5rem;
            font-weight: 900;
            letter-spacing: 5px;
            font-weight: 300; /* ◄ AGREGA ESTO para un subtítulo más fino */
        }

        #inicio h1 span {
            color: var(--color-acento);
        }

        #inicio p {
            font-size: 1.2rem;
            text-transform: uppercase;
            font-weight: 400;
            letter-spacing: 2px;
            margin-top: 10px;
        }

        /* --- 2. SECCIÓN: PROYECTOS --- */
        #proyectos {
            background-color: var(--color-neutro);
        }

        .grid-proyectos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 20px;
        }

        .tarjeta-proyecto {
            background-color: var(--color-principal);
            border-radius: 6px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s ease;
        }

        .tarjeta-proyecto:hover {
            transform: translateY(-5px);
        }

        .proyecto-visual {
            width: 100%;
            height: 220px;
            background-color: #ddd;
            background-size: cover;
            background-position: center;
        }

        .proyecto-info {
            padding: 25px;
        }

        .proyecto-info p {
            font-weight: 100;
            text-align: justify;
        }

        .proyecto-info h3 {
            font-size: 1.2rem;
            text-transform: uppercase;
            margin-bottom: 10px;
           
        }

        /* --- 3. SECCIÓN: SOBRE MÍ --- */
        #sobre-mi {
            background-color: var(--color-principal);
        }

        #sobre-mi p {
            text-align: justify;
        }

        .contenedor-sobre-mi {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .foto-perfil-placeholder {
            width: 100%;
            height: 450px;
            background-color: #eee;
            border-radius: 4px;
            background-image: url('fondo-banner.jpg');
            background-size: cover;
            background-position: center;
        }

        .carrusel-sobre-mi {
            position: relative;
            width: 100%;
            height: 450px;
            overflow: hidden;
            border-radius: 8px;
            background-color: #111;
        }

        .slider-track {
            display: flex;
            width: 500%;
            height: 100%;
            transition: transform 0.8s ease;
        }

        .slide {
            min-width: 100%;
            height: 100%;
            flex: 0 0 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .slide img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
            display: block;
        }

        .carrusel-sobre-mi::before,
        .carrusel-sobre-mi::after {
            content: '';
            position: absolute;
            top: 0;
            width: 80px;
            height: 100%;
            z-index: 2;
            pointer-events: none;
        }

        .carrusel-sobre-mi::before {
            left: 0;
            background: linear-gradient(to right, rgba(17,17,17,1), rgba(17,17,17,0));
        }

        .carrusel-sobre-mi::after {
            right: 0;
            background: linear-gradient(to left, rgba(17,17,17,1), rgba(17,17,17,0));
        }

        .btn-cv {
            display: inline-block;
            margin-top: 25px;
            padding: 12px 30px;
            background-color: var(--color-secundario);
            color: var(--color-principal);
            text-decoration: none;
            font-weight: 700;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
            border: 2px solid var(--color-secundario);
            transition: all 0.3s ease;
        }

        .btn-cv:hover {
            background-color: transparent;
            color: var(--color-secundario);
        }

        /* --- 4. SECCIÓN: CONTACTO --- */
        #contacto {
            background-color: var(--color-secundario);
            color: var(--color-principal);
        }

        .footer-contacto {
            text-align: center;
        }

        .footer-contacto a {
            color: var(--color-acento);
            text-decoration: none;
        }

        .footer-contacto a:hover {
            text-decoration: underline;
        }

        .formulario-contacto {
            max-width: 600px;
            width: 100%;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .formulario-contacto input, .formulario-contacto textarea {
            width: 100%;
            padding: 15px;
            background-color: #222;
            border: 1px solid #444;
            color: white;
            font-family: inherit;
        }

        .formulario-contacto button {
            padding: 15px;
            background-color: var(--color-acento);
            color: white;
            border: none;
            font-weight: 700;
            text-transform: uppercase;
            cursor: pointer;
            transition: opacity 0.3s;
        }

        /* --- DISEÑO RESPONSIVO (MÓVILES) --- */
        @media (max-width: 768px) {
            header { padding: 20px; flex-direction: column; gap: 15px; }
            nav a { margin: 0 10px; font-size: 0.8rem; }
            #inicio h1 { font-size: 3rem; }
            .contenedor-sobre-mi { grid-template-columns: 1fr; }
            section { padding: 140px 20px 60px 20px; }
        }
    </style>
</head>
<body>

    <header>
        <a href="#inicio" class="logo">YARITZA MONDACA<span>.</span></a>
        <nav>
            <a href="#inicio">INICIO</a>
            <a href="#proyectos">PROYECTOS</a>
            <a href="#sobre-mi">SOBRE MÍ</a>
            <a href="#contacto">CONTACTO</a>
        </nav>
    </header>

    <section id="inicio">
        <div class="contenedor-video-youtube">
            <iframe src="https://www.youtube.com/embed/4pi-T4LH3cc?autoplay=1&mute=1&loop=1&playlist=4pi-T4LH3cc&controls=0&showinfo=0&rel=0&modestbranding=1&iv_load_policy=3" 
                    frameborder="0" 
                    allow="autoplay; encrypted-media" 
                    allowfullscreen>
            </iframe>
        </div>
        
        <div class="filtro-oscuro"></div>
        <div class="contenido-hero">
            <h1>PORTAFOLIO<span>.</span></h1>
            <p>Contenido audiovisual y fotografia con enfoque en la divulgación del conocimiento</p>
        </div>
    </section>

    <section id="proyectos">
        <h2 class="titulo-seccion">Proyectos destacados</h2>
        <div class="video-responsive">
                    <iframe src="https://www.youtube.com/embed/BrDQabOUr4E" allowfullscreen></iframe>
                </div>
                <div class="proyecto-info">
                    <h3>Teoría de Lycal Radio</h3>
                    <p>Dirección, locución y montaje audiovisual del podcast La Teoría de Lycal Radio, espacio de conversación sobre el desarrollo científico tecnológico de la Universidad de La Serena, emitido en la Radio Userena y @divulgacionuserena en YouTube.</p>
                </div>
            </div>

            <div class="tarjeta-proyecto">
                <div class="video-responsive">
                    <iframe src="https://www.youtube.com/embed/2t5Kt0qk4ow" allowfullscreen></iframe>
                </div>
                <div class="proyecto-info">
                    <h3>Soli, la cazadora del desierto</h3>
                    <p>Locución y montaje audiovisual del audiolibro.</p>
                </div>
            </div>

            <div class="tarjeta-proyecto">
                <div class="video-responsive">
                    <iframe src="https://www.youtube.com/embed/A7o6tiGTN14" allowfullscreen></iframe>
                </div>
                <div class="proyecto-info">
                    <h3>Nivel Curioso CL</h3>
                    <p>Creadora del canal de datos curiosos con enfoque en la divulgación del conocimiento.</p>
                </div>
    </section>

    <section id="sobre-mi">
        <h2 class="titulo-seccion">Sobre Mí</h2>
        <div class="contenedor-sobre-mi">
            <div>
                <p style="font-size: 1.2rem; font-weight: 300; margin-bottom: 15px;">Periodista y Especialista en Generación de Contenidos Audiovisuales.</p>
                <p>Me dedico a la creación de contenido audiovisual y fotografía con un enfoque en la divulgación del conocimiento. Mi objetivo es transformar ideas y conceptos complejos en relatos narrativos visuales potentes y atractivos.</p>
                <br>
                <p>Cuento con más de 10 años de experiencia en generación de contenidos audiovisuales para medios digitales. Manejo en redacción periodista, comunicación cientifica, escritura creativa, redacción y escritura de guión audiovisual, locución, manejo de equipos audiovisuales como cámaras y micrófonos, manejo avanzado de programas de edición de video, fotografía y animación, conocimiento básico de programas de audio y diseño.</p>
                <a href="curriculum.pdf" target="_blank" class="btn-cv">Descargar Currículum (PDF)</a>
            </div>
            <div class="carrusel-sobre-mi">
                <div class="slider-track" id="slider-sobre-mi">
                    <div class="slide"><img src="foto1.png" alt="Imagen sobre mí 1"></div>
                    <div class="slide"><img src="foto2.jpg" alt="Imagen sobre mí 2"></div>
                    <div class="slide"><img src="foto3.JPG" alt="Imagen sobre mí 3"></div>
                    <div class="slide"><img src="foto4.jpg" alt="Imagen sobre mí 4"></div>
                    <div class="slide"><img src="foto5.jpg" alt="Imagen sobre mí 5"></div>
                </div>
            </div>
        </div>
    </section>

    <section id="contacto">
       <footer class="footer-contacto">
        <h2>Contacto</h2>
        <p style="font-size: 1.4rem; color: #fff; margin-bottom: 15px;">Yaritza Mondaca Rodríguez</p>
        <p>Correo: <a href="mailto:ymondaca1@gmail.com">ymondaca1@gmail.com</a></p>
        <p>Instagram: <a href="https://instagram.com/ymondaca_1" target="_blank">@ymondaca_1</a></p>
    </footer>

    <script>
        (function() {
            const track = document.getElementById('slider-sobre-mi');
            const totalSlides = track ? track.children.length : 0;
            let currentIndex = 0;

            function nextSlide() {
                if (!track) return;
                currentIndex = (currentIndex + 1) % totalSlides;
                track.style.transform = `translateX(-${currentIndex * 100}%)`;
            }

            if (totalSlides > 1) {
                setInterval(nextSlide, 5000);
            }
        })();
    </script>
</body>
</html>
