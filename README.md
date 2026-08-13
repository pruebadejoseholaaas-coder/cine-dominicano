<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Cine Dominicano</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --rojo-rd: #E50914;
            --azul-rd: #002D62;
            --blanco-rd: #FFFFFF;
            --fondo-oscuro: #050814;
            --gris-claro: #CCCCCC;
        }

        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background: radial-gradient(circle at top, #0b1630 0, #050814 45%, #000000 100%);
            color: var(--blanco-rd);
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        /* HEADER */

        header {
            position: sticky;
            top: 0;
            z-index: 10;
            background: rgba(5, 8, 20, 0.95);
            backdrop-filter: blur(8px);
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        .header-inner {
            max-width: 1100px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px 15px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        .logo-flag {
            width: 26px;
            height: 18px;
            border-radius: 3px;
            overflow: hidden;
            display: flex;
        }

        .flag-band {
            flex: 1;
        }

        .flag-band.blue {
            background: var(--azul-rd);
        }

        .flag-band.white {
            background: var(--blanco-rd);
        }

        .flag-band.red {
            background: var(--rojo-rd);
        }

        .logo-text-main {
            font-size: 18px;
        }

        .logo-text-sub {
            font-size: 11px;
            color: var(--gris-claro);
        }

        nav {
            display: flex;
            gap: 15px;
            font-size: 13px;
        }

        nav span {
            cursor: pointer;
            padding: 4px 8px;
            border-radius: 999px;
        }

        nav span:hover {
            background: rgba(255,255,255,0.08);
        }

        .search-box {
            display: flex;
            align-items: center;
            gap: 6px;
            background: rgba(255,255,255,0.06);
            padding: 4px 8px;
            border-radius: 999px;
        }

        .search-box input {
            background: transparent;
            border: none;
            outline: none;
            color: var(--blanco-rd);
            font-size: 12px;
            width: 140px;
        }

        .search-box span {
            font-size: 14px;
        }

        /* PANTALLAS */

        .pantalla {
            display: none;
            max-width: 1100px;
            margin: 0 auto;
            padding: 20px 15px 40px;
        }

        .visible {
            display: block;
        }

        /* PANTALLA INICIO */

        .inicio-hero {
            display: grid;
            grid-template-columns: minmax(0, 1.3fr) minmax(0, 1fr);
            gap: 25px;
            margin-top: 30px;
        }

        @media (max-width: 800px) {
            .inicio-hero {
                grid-template-columns: 1fr;
            }
        }

        .inicio-texto h1 {
            font-size: 28px;
            margin-bottom: 8px;
        }

        .inicio-texto h1 span {
            color: var(--rojo-rd);
        }

        .inicio-texto p {
            font-size: 14px;
            color: var(--gris-claro);
            max-width: 420px;
        }

        .inicio-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 12px;
        }

        .badge {
            font-size: 11px;
            padding: 4px 10px;
            border-radius: 999px;
            border: 1px solid rgba(255,255,255,0.12);
            background: rgba(255,255,255,0.03);
        }

        .badge.flag {
            border-color: var(--rojo-rd);
            color: var(--rojo-rd);
        }

        .inicio-acciones {
            margin-top: 18px;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .btn {
            border: none;
            cursor: pointer;
            border-radius: 999px;
            padding: 8px 16px;
            font-size: 13px;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .btn-primary {
            background: var(--rojo-rd);
            color: var(--blanco-rd);
        }

        .btn-primary:hover {
            background: #ff1b24;
        }

        .btn-secondary {
            background: rgba(255,255,255,0.06);
            color: var(--blanco-rd);
        }

        .btn-secondary:hover {
            background: rgba(255,255,255,0.12);
        }

        .inicio-form {
            background: linear-gradient(135deg, rgba(0,45,98,0.9), rgba(229,9,20,0.9));
            border-radius: 16px;
            padding: 18px;
            box-shadow: 0 12px 30px rgba(0,0,0,0.6);
        }

        .inicio-form h2 {
            font-size: 18px;
            margin-bottom: 6px;
        }

        .inicio-form p {
            font-size: 12px;
            color: #f5f5f5;
            margin-bottom: 12px;
        }

        .inicio-form input {
            width: 100%;
            padding: 10px;
            border-radius: 999px;
            border: none;
            outline: none;
            font-size: 13px;
            margin-bottom: 10px;
        }

        .inicio-form button {
            width: 100%;
        }

        .inicio-destacada {
            margin-top: 30px;
        }

        .destacada-card {
            display: flex;
            gap: 16px;
            background: rgba(255,255,255,0.03);
            border-radius: 14px;
            padding: 14px;
            border: 1px solid rgba(255,255,255,0.06);
        }

        @media (max-width: 700px) {
            .destacada-card {
                flex-direction: column;
            }
        }

        .destacada-poster {
            width: 120px;
            height: 170px;
            border-radius: 10px;
            background: linear-gradient(135deg, #1b2a4a, #e50914);
        }

        .destacada-info h3 {
            margin: 0 0 4px;
            font-size: 16px;
        }

        .destacada-meta {
            font-size: 11px;
            color: var(--gris-claro);
            margin-bottom: 6px;
        }

        .destacada-desc {
            font-size: 12px;
            color: var(--gris-claro);
            margin-bottom: 10px;
        }

        .destacada-actions {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        /* PANTALLA APP */

        .usuario-info {
            font-size: 12px;
            color: var(--gris-claro);
            margin-bottom: 10px;
        }

        .seccion-titulo {
            font-size: 18px;
            margin-bottom: 8px;
        }

        .peliculas-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 16px;
            margin-top: 10px;
        }

        .pelicula-card {
            background: rgba(255,255,255,0.03);
            border-radius: 12px;
            padding: 10px;
            border: 1px solid rgba(255,255,255,0.06);
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .pelicula-poster {
            width: 100%;
            height: 140px;
            border-radius: 10px;
            background: linear-gradient(135deg, #1b2a4a, #e50914);
        }

        .pelicula-titulo {
            font-size: 14px;
            font-weight: 600;
        }

        .pelicula-meta {
            font-size: 11px;
            color: var(--gris-claro);
        }

        iframe {
            width: 100%;
            height: 150px;
            border-radius: 10px;
            border: none;
        }

        .comentarios {
            margin-top: 4px;
        }

        .comentarios h4 {
            font-size: 12px;
            margin: 0 0 4px;
        }

        .comentarios-lista {
            max-height: 80px;
            overflow-y: auto;
            background: rgba(0,0,0,0.4);
            padding: 4px;
            border-radius: 6px;
            font-size: 11px;
        }

        .comentario-item {
            border-bottom: 1px solid rgba(255,255,255,0.06);
            padding: 3px 0;
        }

        .comentario-item:last-child {
            border-bottom: none;
        }

        .comentarios input[type="text"] {
            width: 100%;
            padding: 6px;
            border-radius: 999px;
            border: none;
            outline: none;
            font-size: 11px;
            margin-top: 4px;
        }

        .comentarios button {
            margin-top: 4px;
            padding: 5px 10px;
            font-size: 11px;
        }

        /* ADMIN */

        .admin-btn {
            position: fixed;
            bottom: 18px;
            right: 18px;
            background: rgba(0,45,98,0.9);
            color: var(--blanco-rd);
            border-radius: 999px;
            border: none;
            padding: 8px 14px;
            font-size: 11px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 6px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.6);
        }

        .admin-btn:hover {
            background: rgba(0,60,130,0.95);
        }

        .admin-contenido {
            max-width: 420px;
            margin: 40px auto;
            background: rgba(255,255,255,0.03);
            border-radius: 16px;
            padding: 18px;
            border: 1px solid rgba(255,255,255,0.08);
        }

        .admin-contenido h2 {
            font-size: 18px;
            margin-bottom: 8px;
            text-align: center;
        }

        .admin-contenido p {
            font-size: 12px;
            color: var(--gris-claro);
            text-align: center;
            margin-bottom: 12px;
        }

        .admin-contenido input {
            width: 100%;
            padding: 9px;
            border-radius: 999px;
            border: none;
            outline: none;
            font-size: 12px;
            margin-bottom: 8px;
        }

        .admin-contenido button {
            width: 100%;
        }

        .admin-panel-inner h3 {
            font-size: 14px;
            margin-bottom: 8px;
            text-align: left;
        }

        /* UTILIDADES */

        .chips-row {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-top: 8px;
        }

        .chip {
            font-size: 11px;
            padding: 3px 9px;
            border-radius: 999px;
            background: rgba(255,255,255,0.06);
        }

        .chip.genre {
            background: rgba(229,9,20,0.18);
            border: 1px solid rgba(229,9,20,0.5);
        }

        .chip.year {
            background: rgba(0,45,98,0.3);
            border: 1px solid rgba(0,45,98,0.6);
        }

        .seccion-sub {
            font-size: 12px;
            color: var(--gris-claro);
            margin-bottom: 4px;
        }
    </style>
</head>
<body>

<header>
    <div class="header-inner">
        <div class="logo">
            <div class="logo-flag">
                <div class="flag-band.blue"></div>
                <div class="flag-band.white"></div>
                <div class="flag-band.red"></div>
            </div>
            <div>
                <div class="logo-text-main">Cine Dominicano</div>
                <div class="logo-text-sub">Cine de República Dominicana</div>
            </div>
        </div>
        <nav>
            <span id="navInicio">Inicio</span>
            <span id="navPeliculas">Películas</span>
            <span>Géneros</span>
            <span>Actores</span>
            <span id="navSorprendeme">🎲 Sorpréndeme</span>
        </nav>
        <div class="search-box">
            <span>🔎</span>
            <input type="text" id="buscadorGlobal" placeholder="Buscar película, actor, año...">
        </div>
    </div>
</header>

<!-- PANTALLA INICIO -->
<div id="pantallaInicio" class="pantalla visible">
    <div class="inicio-hero">
        <div class="inicio-texto">
            <h1><span>Cine Dominicano</span><br>Todo el cine de RD en un solo lugar.</h1>
            <p>
                Descubre películas dominicanas, clásicos, comedias, dramas y más. Encuentra dónde verlas oficialmente
                y comparte el cine de tu país.
            </p>
            <div class="inicio-badges">
                <div class="badge flag">🇩🇴 República Dominicana</div>
                <div class="badge">🎬 Cine dominicano</div>
                <div class="badge">🎭 Comedia · Drama · Romance</div>
                <div class="badge">📱 Diseñado para móvil</div>
            </div>
            <div class="inicio-acciones">
                <button class="btn btn-primary" id="btnIrPeliculas">▶ Ver películas</button>
                <button class="btn btn-secondary">🔥 Tendencias</button>
                <button class="btn btn-secondary">🆕 Últimas añadidas</button>
                <button class="btn btn-secondary">🇩🇴 Clásicos dominicanos</button>
            </div>

            <div class="inicio-destacada">
                <div class="seccion-sub">Película destacada</div>
                <div class="destacada-card">
                    <div class="destacada-poster"></div>
                    <div class="destacada-info">
                        <h3>QUÉ LEÓN</h3>
                        <div class="destacada-meta">Comedia · Romance · 2018 · República Dominicana</div>
                        <div class="destacada-desc">
                            Una de las películas dominicanas más populares. Ideal para reír, enamorarse y ver el talento
                            dominicano en pantalla grande.
                        </div>
                        <div class="destacada-actions">
                            <button class="btn btn-primary">▶ Ver película</button>
                            <button class="btn btn-secondary">＋ Añadir a favoritos</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="inicio-form">
            <h2>Entrar a Cine Dominicano</h2>
            <p>Escribe tu nombre para entrar, comentar y guardar tus películas favoritas.</p>
            <input type="text" id="nombreUsuario" placeholder="Tu nombre">
            <button class="btn btn-primary" id="btnEntrar">Entrar</button>
        </div>
    </div>
</div>

<!-- PANTALLA PRINCIPAL -->
<div id="pantallaApp" class="pantalla">
    <div class="usuario-info">
        Usuario: <span id="nombreMostrado"></span> · 🇩🇴 Bienvenido a Cine Dominicano
    </div>

    <div class="seccion-titulo">Catálogo de películas dominicanas</div>
    <div class="seccion-sub">Explora, comenta y descubre dónde ver cada película.</div>

    <div class="chips-row">
        <div class="chip genre">Comedia</div>
        <div class="chip genre">Drama</div>
        <div class="chip genre">Romance</div>
        <div class="chip genre">Acción</div>
        <div class="chip year">2020–2026</div>
        <div class="chip year">2010–2019</div>
        <div class="chip year">Clásicos</div>
    </div>

    <div class="peliculas-container" id="peliculasContainer"></div>
</div>

<!-- PANTALLA ADMIN -->
<div id="pantallaAdmin" class="pantalla">
    <div class="admin-contenido">
        <h2>Panel de administración</h2>
        <p>Gestiona el catálogo de Cine Dominicano. Solo para administrador.</p>

        <div id="adminLogin">
            <input type="password" id="adminPass" placeholder="Contraseña de administrador">
            <button class="btn btn-primary" id="btnLoginAdmin">Entrar</button>
        </div>

        <div id="adminPanel" style="display:none;">
            <div class="admin-panel-inner">
                <h3>Agregar nueva película</h3>
                <input type="text" id="tituloPeli" placeholder="Título de la película">
                <input type="text" id="descPeli" placeholder="Descripción / sinopsis breve">
                <input type="text" id="metaPeli" placeholder="Año · Género · País">
                <input type="text" id="youtubePeli" placeholder="ID de YouTube (lo que va después de /watch?v=)">
                <button class="btn btn-primary" id="btnAgregarPeli">Agregar al catálogo</button>
            </div>
        </div>
    </div>
</div>

<!-- BOTÓN ADMIN -->
<button class="admin-btn" id="btnAdmin">⚙ Admin</button>

<script>
    // CONTRASEÑA DEL ADMIN
    const ADMIN_PASSWORD = "dominicana123";

    // PELÍCULAS (se cargan de localStorage o se inicia con base)
    let peliculas = JSON.parse(localStorage.getItem("peliculas_db")) || [
        {
            id: 1,
            titulo: "Qué León",
            descripcion: "Comedia romántica dominicana sobre el amor entre dos jóvenes de clases sociales diferentes.",
            meta: "2018 · Comedia · República Dominicana",
            youtubeId: "VIDEO_ID_1"
        },
        {
            id: 2,
            titulo: "Película Dominicana 2",
            descripcion: "Descripción breve de otra película dominicana.",
            meta: "2020 · Drama · República Dominicana",
            youtubeId: "VIDEO_ID_2"
        }
    ];

    function guardarPeliculas() {
        localStorage.setItem("peliculas_db", JSON.stringify(peliculas));
    }

    // COMENTARIOS
    let comentarios = JSON.parse(localStorage.getItem("comentarios_db")) || {};

    function guardarComentarios() {
        localStorage.setItem("comentarios_db", JSON.stringify(comentarios));
    }

    // ELEMENTOS
    const pantallaInicio = document.getElementById("pantallaInicio");
    const pantallaApp = document.getElementById("pantallaApp");
    const pantallaAdmin = document.getElementById("pantallaAdmin");

    const nombreUsuarioInput = document.getElementById("nombreUsuario");
    const nombreMostrado = document.getElementById("nombreMostrado");
    const peliculasContainer = document.getElementById("peliculasContainer");

    const btnEntrar = document.getElementById("btnEntrar");
    const btnIrPeliculas = document.getElementById("btnIrPeliculas");
    const btnAdmin = document.getElementById("btnAdmin");
    const btnLoginAdmin = document.getElementById("btnLoginAdmin");
    const btnAgregarPeli = document.getElementById("btnAgregarPeli");

    const navInicio = document.getElementById("navInicio");
    const navPeliculas = document.getElementById("navPeliculas");
    const navSorprendeme = document.getElementById("navSorprendeme");
    const buscadorGlobal = document.getElementById("buscadorGlobal");

    let usuarioActual = "";

    function mostrarPantalla(id) {
        pantallaInicio.classList.remove("visible");
        pantallaApp.classList.remove("visible");
        pantallaAdmin.classList.remove("visible");

        document.getElementById(id).classList.add("visible");
    }

    // ENTRAR A LA WEB
    btnEntrar.addEventListener("click", () => {
        const nombre = nombreUsuarioInput.value.trim();
        if (!nombre) {
            alert("Escribe tu nombre para entrar.");
            return;
        }
        usuarioActual = nombre;
        nombreMostrado.textContent = usuarioActual;
        mostrarPantalla("pantallaApp");
        renderPeliculas();
    });

    // IR A PELÍCULAS DESDE HERO
    btnIrPeliculas.addEventListener("click", () => {
        mostrarPantalla("pantallaInicio");
        // si ya hay usuario, ir directo a app
        if (usuarioActual) {
            mostrarPantalla("pantallaApp");
            renderPeliculas();
        }
    });

    // NAVEGACIÓN
    navInicio.addEventListener("click", () => {
        mostrarPantalla("pantallaInicio");
    });

    navPeliculas.addEventListener("click", () => {
        if (!usuarioActual) {
            alert("Primero escribe tu nombre para entrar.");
            mostrarPantalla("pantallaInicio");
            return;
        }
        mostrarPantalla("pantallaApp");
        renderPeliculas();
    });

    navSorprendeme.addEventListener("click", () => {
        if (!usuarioActual) {
            alert("Primero entra con tu nombre para usar Sorpréndeme.");
            return;
        }
        if (!peliculas.length) return;
        const random = peliculas[Math.floor(Math.random() * peliculas.length)];
        alert("🎲 Te recomendamos: " + random.titulo + "\n" + random.meta);
    });

    // BUSCADOR GLOBAL
    buscadorGlobal.addEventListener("input", () => {
        const q = buscadorGlobal.value.trim().toLowerCase();
        if (!usuarioActual) return;
        renderPeliculas(q);
    });

    // ABRIR PANEL ADMIN
    btnAdmin.addEventListener("click", () => {
        mostrarPantalla("pantallaAdmin");
    });

    // LOGIN ADMIN
    btnLoginAdmin.addEventListener("click", () => {
        const pass = document.getElementById("adminPass").value;
        if (pass === ADMIN_PASSWORD) {
            document.getElementById("adminLogin").style.display = "none";
            document.getElementById("adminPanel").style.display = "block";
        } else {
            alert("Contraseña incorrecta.");
        }
    });

    // AGREGAR PELÍCULA
    btnAgregarPeli.addEventListener("click", () => {
        const titulo = document.getElementById("tituloPeli").value.trim();
        const desc = document.getElementById("descPeli").value.trim();
        const meta = document.getElementById("metaPeli").value.trim();
        const youtube = document.getElementById("youtubePeli").value.trim();

        if (!titulo || !desc || !meta || !youtube) {
            alert("Completa todos los campos para agregar la película.");
            return;
        }

        peliculas.push({
            id: Date.now(),
            titulo,
            descripcion: desc,
            meta,
            youtubeId: youtube
        });

        guardarPeliculas();
        alert("Película agregada al catálogo.");

        document.getElementById("tituloPeli").value = "";
        document.getElementById("descPeli").value = "";
        document.getElementById("metaPeli").value = "";
        document.getElementById("youtubePeli").value = "";
    });

    // RENDER PELÍCULAS
    function renderPeliculas(filtro = "") {
        peliculasContainer.innerHTML = "";

        const lista = peliculas.filter(p => {
            if (!filtro) return true;
            const t = (p.titulo || "").toLowerCase();
            const d = (p.descripcion || "").toLowerCase();
            const m = (p.meta || "").toLowerCase();
            return t.includes(filtro) || d.includes(filtro) || m.includes(filtro);
        });

        lista.forEach(p => {
            const card = document.createElement("div");
            card.className = "pelicula-card";

            const poster = document.createElement("div");
            poster.className = "pelicula-poster";

            const titulo = document.createElement("div");
            titulo.className = "pelicula-titulo";
            titulo.textContent = p.titulo;

            const meta = document.createElement("div");
            meta.className = "pelicula-meta";
            meta.textContent = p.meta || "Película dominicana";

            const desc = document.createElement("div");
            desc.style.fontSize = "11px";
            desc.style.color = "#CCCCCC";
            desc.textContent = p.descripcion;

            const iframe = document.createElement("iframe");
            iframe.src = `https://www.youtube.com/embed/${p.youtubeId}`;
            iframe.setAttribute("allowfullscreen", "true");

            const comentariosDiv = document.createElement("div");
            comentariosDiv.className = "comentarios";

            const comentariosTitulo = document.createElement("h4");
            comentariosTitulo.textContent = "Comentarios";

            const comentariosLista = document.createElement("div");
            comentariosLista.className = "comentarios-lista";
            comentariosLista.id = "c_" + p.id;

            const inputComentario = document.createElement("input");
            inputComentario.type = "text";
            inputComentario.placeholder = "Escribe un comentario...";

            const btnComentar = document.createElement("button");
            btnComentar.className = "btn btn-secondary";
            btnComentar.textContent = "Comentar";

            btnComentar.addEventListener("click", () => {
                const texto = inputComentario.value.trim();
                if (!texto) return;
                if (!comentarios[p.id]) comentarios[p.id] = [];
                comentarios[p.id].push({
                    usuario: usuarioActual,
                    texto,
                    fecha: new Date().toLocaleString()
                });
                guardarComentarios();
                inputComentario.value = "";
                mostrarComentarios(p.id);
            });

            comentariosDiv.appendChild(comentariosTitulo);
            comentariosDiv.appendChild(comentariosLista);
            comentariosDiv.appendChild(inputComentario);
            comentariosDiv.appendChild(btnComentar);

            card.appendChild(poster);
            card.appendChild(titulo);
            card.appendChild(meta);
            card.appendChild(desc);
            card.appendChild(iframe);
            card.appendChild(comentariosDiv);

            peliculasContainer.appendChild(card);

            mostrarComentarios(p.id);
        });
    }

    // MOSTRAR COMENTARIOS
    function mostrarComentarios(id) {
        const cont = document.getElementById("c_" + id);
        if (!cont) return;
        cont.innerHTML = "";
        (comentarios[id] || []).forEach(c => {
            const div = document.createElement("div");
            div.className = "comentario-item";
            div.textContent = `${c.usuario}: ${c.texto} (${c.fecha})`;
            cont.appendChild(div);
        });
    }
</script>

</body>
</html>
