@page
@model RIFA.Views.Home.politicaModel
@{
}

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Política de Privacidad | RIFA</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css&quot"; rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css&quot";  />
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css&quot"; rel="stylesheet" />
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js">
        </script>

            <style>
        * {
            box-sizing: border-box;
        }

        body {
            background-color: #0D1117;
            color: #C9D1D9;
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            overflow-y: auto;
        }

        main {
            position: relative;
            z-index: 1;
        }

        .video-wrap {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
        }

        .custom-video {
            position: absolute;
            top: 50%;
            left: 50%;
            min-width: 100%;
            min-height: 100%;
            transform: translate(-50%, -50%);
            object-fit: cover;
        }

        /* Video background (tu nuevo elemento .video-background) */
        .video-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -2; /* Más bajo que body::before para que la capa oscura esté encima */
        }

            .video-background video {
                min-width: 100%;
                min-height: 100%;
                width: auto;
                height: auto;
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                opacity: 0.8; /* Un poco más opaco el video */
                object-fit: cover; /* Asegura que el video cubra el área */
            }

        body::before {
            content: '';
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.75); /* Capa oscura encima del video */
            z-index: -1;
        }

        .main-content {
            margin-top: 150px; /* Ajustado para dar espacio al header fijo */
            padding: 0 1rem;
            position: relative; /* Asegura que el contenido esté por encima del video y la capa oscura */
            z-index: 1;
        }

        h1 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 30px;
            color: #38A1C3;
        }

        h2 {
            margin-top: 30px;
            color: #9EBFD9;
            font-size: 1.4rem;
        }

        p {
            line-height: 1.7;
            color: #DDE8F1;
        }

        .footer {
            text-align: center;
            padding: 20px;
            font-size: 0.9rem;
            color: #8396A6;
            position: relative; /* Asegura que el footer esté por encima del video y la capa oscura */
            z-index: 1;
        }

        .logo-floating {
            position: fixed;
            top: 20px;
            left: 20px;
            width: 80px;
            height: 80px;
            border-radius: 15px;
            background: rgba(255,255,255,0.05);
            display: flex;
            justify-content: center;
            align-items: center;
            border: 2px solid #38A1C3;
            z-index: 1000; /* Asegura que esté por encima de todo */
        }

            .logo-floating img {
                width: 100%;
                height: auto;
                object-fit: contain;
                border-radius: 10px;
            }

        .btn-return {
            display: inline-block;
            margin: 40px auto 0;
            padding: 12px 30px;
            background-color: #38A1C3;
            color: #fff;
            border: none;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1rem;
            transition: background 0.3s ease;
        }

            .btn-return:hover {
                background-color: #2e7fa2;
            }

            .btn-return i {
                margin-right: 8px;
            }

        .site-header {
            background-color: rgba(0, 0, 0, 0.7);
            border-radius: 40px;
            padding: 15px 30px;
            margin: 20px auto;
            max-width: 1200px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: fixed; /* Hacer el header fijo */
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: calc(100% - 40px); /* Ajustar el ancho para que respete el margen */
            z-index: 999; /* Asegura que el header esté siempre visible */
        }

            .site-header .container {
                display: flex;
                justify-content: center;
                align-items: center;
            }

            .site-header .row {
                display: flex;
                justify-content: space-between;
                align-items: center;
                width: 100%;
            }

        .site-header-text {
            display: flex;
            align-items: center;
            text-decoration: none;
            color: #fff;
            font-weight: 700;
            font-family: 'Unbounded', sans-serif;
            font-size: 1.5rem;
            margin-right: auto;
        }

            .site-header-text img {
                height: 40px;
                margin-right: 10px;
            }

        .social-icon {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            align-items: center;
        }

        .social-icon-item {
            margin-left: 15px;
        }

        .social-icon-link {
            color: #fff;
            font-size: 1.2rem;
            text-decoration: none;
            opacity: 0.7;
            transition: opacity 0.3s ease;
        }

            .social-icon-link:hover {
                opacity: 1;
            }

        .offcanvas-icon {
            color: #fff;
            font-size: 1.5rem;
            cursor: pointer;
            margin-left: 20px;
        }

        .offcanvas {
            background-color: #111;
            color: #fff;
        }

        .offcanvas-header .btn-close {
            color: #fff;
            opacity: 0.7;
        }

        .offcanvas-body nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
            text-align: center;
        }

            .offcanvas-body nav ul li {
                margin-bottom: 15px;
            }

                .offcanvas-body nav ul li a {
                    color: #fff;
                    text-decoration: none;
                    font-size: 1.1rem;
                    opacity: 0.8;
                    transition: opacity 0.3s ease;
                }

                    .offcanvas-body nav ul li a.active,
                    .offcanvas-body nav ul li a:hover {
                        opacity: 1;
                    }

        /* INICIO DE LOS ESTILOS PARA LA SECCIÓN "OBJETIVO GENERAL" Y REUSO PARA POLÍTICA DE PRIVACIDAD */
        /* Nota: el .container ya tiene muchos de estos estilos, pero los mantengo para consistencia */
        .project-content {
            max-width: 1000px;
            margin: 0 auto;
            padding: 3rem 1rem;
            color: #ffffff;
            text-align: center;
            height: auto;
            overflow: visible;
        }

        /* Clase info-section reusada para los bloques de contenido de la política */
        .info-section {
            background-color: rgba(0, 0, 0, 0.7); /* Fondo oscuro transparente */
            border-radius: 20px;
            padding: 2rem;
            margin: 1.5rem auto; /* Ajustado para que cada sección tenga margen */
            border: 1px solid #2E3A47;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
            height: auto;
            overflow: visible;
            word-wrap: break-word;
            overflow-wrap: break-word;
            text-align: initial; /* Para que el texto dentro de la sección no esté centrado por defecto */
        }

        .mission-vision .info-section {
            margin: 1rem; /* Ajusta los márgenes entre las columnas */
            width: calc(100% - 2rem); /* Ancho completo menos los márgenes */
        }

        media (min-width: 768px) { /* Corregido: añadido 'media' */
            .mission-vision .info-section

        {
            width: auto; /* Dejar que Bootstrap controle el ancho */
        }

        }

        .project-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 2rem;
            color: #F0F6FC; /* Color para el título principal del proyecto */
        }

        /* Clase info-title reusada para los subtítulos de la política */
        .info-title {
            font-size: 1.8rem;
            font-weight: bold;
            color: #ffffff;
            margin-bottom: 1rem;
        }

        /* Clase info-text reusada para los párrafos de la política */
        .info-text {
            font-size: 1rem;
            color: #C9D1D9;
        }

        .btn-orange {
            background-color: #143B5B;
            border: none;
            color: #fff;
            padding: 0.75rem 1.5rem;
            font-weight: bold;
            border-radius: 20px;
            transition: background-color 0.3s ease;
            text-decoration: none;
        }

            .btn-orange:hover {
                background-color: #0F2E45;
            }
        /* FIN DE LOS ESTILOS PARA LA SECCIÓN "OBJETIVO GENERAL" */


        /* Ajustes específicos para el offcanvas */
        .offcanvas {
            background-color: #161B22; /* Fondo oscuro similar al cuerpo */
            color: #C9D1D9; /* Color de texto general */
        }

        .offcanvas-header .btn-close {
            color: #C9D1D9; /* Color del botón de cerrar */
            opacity: 1; /* Asegura que sea visible */
        }

        .offcanvas-body nav ul li a {
            color: #C9D1D9; /* Color de los enlaces */
            text-decoration: none;
            transition: color 0.3s ease;
        }

            .offcanvas-body nav ul li a:hover,
            .offcanvas-body nav ul li a.active {
                color: #58A6FF; /* Color al pasar el ratón o si está activo */
            }
        </style>
</head>

<body>
    <main>
        <header class="site-header">
            <div class="container">
                <div class="row justify-content-between align-items-center">
                    <div class="col-auto">
                        <a class="site-header-text d-flex align-items-center" href="/">
                            <img src="~/imagenes/logo.png" alt="Logo" style="height: 40px; margin-right: 10px;">
                            RIFA
                        </a>
                    </div>
                    <div class="col-auto d-flex align-items-center">
                        <p class="mb-0 me-2">
                            <a href="https://www.instagram.com/rifa_cecyt13&quot"; target="_blank" style="color: #fff;">¡Conócenos!</a>
                        </p>
                        <ul class="social-icon d-flex align-items-center me-3 mb-0">
                            <li class="social-icon-item">
                                <a href="https://www.instagram.com/rifa_cecyt13&quot"; class="social-icon-link instagram" target="_blank">
                                    <i class="fab fa-instagram"></i>
                                </a>
                            </li>
                        </ul>
                        <a class="bi-list offcanvas-icon" data-bs-toggle="offcanvas" href="#offcanvasMenu" role="button" aria-controls="offcanvasMenu"></a>
                    </div>
                </div>
            </div>
        </header>

        <div class="offcanvas offcanvas-end" data-bs-scroll="true" tabindex="-1" id="offcanvasMenu" aria-labelledby="offcanvasMenuLabel">
            <div class="offcanvas-header">
                <button type="button" class="btn-close ms-auto" data-bs-dismiss="offcanvas" aria-label="Close"></button>
            </div>
            <div class="offcanvas-body d-flex flex-column justify-content-center align-items-center">
                <nav>
                    <ul>
                        <li> <a href="@Url.Action("index", "Home")">Inicio</a></li>
        @* Mostrar "Ingresar" o "Cerrar Sesión" dependiendo del estado *@
        @if (User.Identity.IsAuthenticated)
        {
                            <li> <a href="@Url.Action("Logout", "Home")">Cerrar Sesión</a></li>
        }
        else
        {
                            <li> <a href="@Url.Action("ingresar", "Home")">Ingresar</a></li>
                            <li> <a href="@Url.Action("register", "Home")">Crear una Cuenta</a></li>
        }

        @* Enlaces generales, visibles para todos *@
                        <li> <a href="@Url.Action("passwordreset", "Home")">Cambiar Contraseña</a></li>
                        <li> <a href="@Url.Action("dudas", "Home")">Contacto</a></li>
                        <li> <a href="@Url.Action("historial", "Home")">Historial</a></li>
                        <li> <a href="@Url.Action("nosotros", "Home")">Nosotros</a></li>
                        <li> <a href="@Url.Action("paginainformativa", "Home")">Pagina Informativa</a></li>
                        <li> <a href="@Url.Action("politica", "Home")">Politica de Privacidad</a></li>
                        <li> <a href="@Url.Action("productos", "Home")">Productos</a></li>

                        <li> <a href="@Url.Action("reglas", "Home")">Reglamento</a></li>
                        <li> <a href="@Url.Action("dash", "Home")">Dashboard</a></li>

        @* --- NUEVO: Enlace a alba.cshtml visible SÓLO para Administradores --- *@
        @if (User.Identity.IsAuthenticated && User.IsInRole("Administrador"))
        {
                            <li> <a href="@Url.Action("alba", "Home")">Administración de Alba</a></li>
                            <li> <a href="@Url.Action("puntosacumulados", "Home")">Puntos Acumulados</a></li>
        }
                    </ul>
                </nav>
            </div>
        </div>

        <div class="video-background">
            <video autoplay muted loop class="custom-video">
                <source src="videos/video.mp4" type="video/mp4">
                Tu navegador no soporta el video.
            </video>
        </div>

        <div class="main-content">
            <div class="container">
                <h1 class="project-title">Política de Privacidad</h1> @* Se aplica project-title para estilo similar *@

                <div class="info-section">
        @* Envuelto en info-section *@
                    <h2 class="info-title">1. Información que Recopilamos</h2> @* Se aplica info-title *@
                    <p class="info-text">
        @* Se aplica info-text *@
                        Recopilamos datos personales básicos como nombre, correo electrónico y puntos acumulados, exclusivamente para ofrecerte una mejor experiencia de usuario dentro de la plataforma.
                    </p>
                </div>

                <div class="info-section">
        @* Envuelto en info-section *@
                    <h2 class="info-title">2. Uso de la Información</h2> @* Se aplica info-title *@
                    <p class="info-text">
        @* Se aplica info-text *@
                        Usamos tu información para gestionar tu cuenta, registrar tus puntos obtenidos mediante reciclaje y permitir la redención de premios. Nunca compartiremos tus datos con terceros sin tu consentimiento.
                    </p>
                </div>

                <div class="info-section">
        @* Envuelto en info-section *@
                    <h2 class="info-title">3. Protección de Datos</h2> @* Se aplica info-title *@
                    <p class="info-text">
        @* Se aplica info-text *@
                        Aplicamos medidas técnicas y organizativas adecuadas para proteger tus datos conforme a lo establecido por la Ley Federal de Protección de Datos Personales en Posesión de los Particulares de México.
                    </p>
                </div>

                <div class="info-section">
        @* Envuelto en info-section *@
                    <h2 class="info-title">4. Derechos del Usuario</h2> @* Se aplica info-title *@
                    <p class="info-text">
        @* Se aplica info-text *@
                        Tienes derecho a acceder, rectificar, cancelar u oponerte al tratamiento de tus datos personales (Derechos ARCO). Puedes ejercerlos en cualquier momento escribiéndonos a nuestro correo de contacto o a nuestras redes sociales.
                    </p>
                </div>

                <div class="info-section">
        @* Envuelto en info-section *@
                    <h2 class="info-title">5. Cambios a esta Política</h2>@* Se aplica info-title *@
                    <p class="info-text">
        @* Se aplica info-text *@
                        Nos reservamos el derecho de modificar esta política para adaptarla a cambios legislativos o mejoras en nuestros servicios. Te notificaremos oportunamente cualquier cambio significativo.
                    </p>
                </div>

                <div class="info-section">
        @* Envuelto en info-section *@
                    <h2 class="info-title">6. Contacto</h2>@* Se aplica info-title *@
                    <p class="info-text">
        @* Se aplica info-text *@
                        Si tienes dudas o deseas ejercer tus derechos, contáctanos en
                        <a href="munozhuizardaniela@gmail.com" style="color: #38A1C3; text-decoration: underline;">rifa.voca13@gmail.com</a> o en nuestro
                        <a href="https://www.instagram.com/rifa_cecyt13?igsh=NDg0eHJ6NWpzOG9n&authuser=0&quot"; target="_blank" style="color: #38A1C3; text-decoration: underline;">Instagram</a>.
                    </p>
                </div>

                <div style="text-align: center; margin-top: 40px;">
                    <a href="@Url.Action("index", "Home")" class="btn-return"><i class="fas fa-arrow-left"></i> Volver a la página principal</a>
                </div>
            </div>
        </div>

        <div class="footer">
            © 2025 RIFA | Proyecto de Reciclaje - Todos los derechos reservados
        </div>
    </main>
</body>
</html>
