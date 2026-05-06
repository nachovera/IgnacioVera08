<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
  <meta name="theme-color" content="#070c18" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
  <meta name="apple-mobile-web-app-title" content="Guardian Shield" />
  <title>Guardian Shield v10</title>
  <style>
    html, body, #root { margin:0; min-height:100%; background:#070c18; color:#f1f5f9; font-family:Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif; }
    * { box-sizing:border-box; }
    a { text-decoration:none; }
    button, input, textarea { font-family:inherit; }
    @keyframes _sp { to { transform: rotate(360deg); } }
    @keyframes _pl { 0%,100% { opacity:1; } 50% { opacity:.35; } }
    @keyframes _up { from { opacity:0; transform:translate(-50%, 12px); } to { opacity:1; transform:translate(-50%, 0); } }
  </style>
</head>
<body>
  <div id="root"></div>

  <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

  <script type="text/babel">
const { useState, useRef, useCallback, useEffect } = React;

/* ─── DESIGN TOKENS ─────────────────────────────────── */
const C = {
  bg:"#070c18", s1:"#0c1324", s2:"#111b30", s3:"#16233d",
  blue:"#2563eb", blue2:"#1d4ed8", cyan:"#0ea5e9",
  green:"#22c55e", red:"#ef4444", amber:"#f59e0b", purple:"#8b5cf6",
  text:"#f1f5f9", mid:"#94a3b8", dim:"#475569", faint:"#1e2d47",
  mono:"'SF Mono','Fira Code','Courier New',monospace",
};
const SEV = { CRÍTICO:"#ef4444", ALTO:"#f97316", MEDIO:"#f59e0b", BAJO:"#3b82f6" };
const CATS = {
  gaming:{l:"Gaming",i:"🎮"}, social:{l:"Social",i:"👥"},
  email:{l:"Email & Chat",i:"💬"}, stream:{l:"Streaming",i:"🎬"},
  finance:{l:"Finanzas",i:"💳"}, work:{l:"Trabajo",i:"💼"},
  cloud:{l:"Cloud",i:"☁️"}, shop:{l:"Compras",i:"🛒"}, other:{l:"Otros",i:"◈"},
};

/* ─── PLATAFORMAS (sin Twitter) ──────────────────────── */
const PLATFORMS = [
  // Gaming
  {id:"psn",cat:"gaming",icon:"🎮",name:"PlayStation Network",desc:"PS4 · PS5 · Plus · Store",url:"https://account.sonyentertainmentnetwork.com",steps:["PlayStation.com → Mi cuenta → Seguridad → Actividad de inicio de sesión","Cerrar sesiones en todos los dispositivos desconocidos","Activar verificación en dos pasos con app autenticadora","Revisar historial de compras y métodos de pago guardados","Desactivar la opción de compartir datos con terceros"]},
  {id:"xbox",cat:"gaming",icon:"🟩",name:"Xbox / Microsoft",desc:"Game Pass · Cloud · Store",url:"https://account.microsoft.com/security",steps:["account.microsoft.com → Seguridad → Actividad reciente","Revisar dispositivos de confianza registrados","Activar 2FA con app autenticadora (Microsoft Authenticator)","Suscripciones activas y pagos: verificar","Configurar alertas de seguridad por email"]},
  {id:"steam",cat:"gaming",icon:"🕹️",name:"Steam",desc:"PC · Workshop · Items",url:"https://store.steampowered.com/account/",steps:["Ajustes → Cuenta → Historial de accesos recientes","Activar Steam Guard Mobile Authenticator","Revisar y revocar API Keys de terceros","Verificar email y teléfono vinculados","Revisar historial de intercambios y compras"]},
  {id:"epic",cat:"gaming",icon:"◈",name:"Epic Games",desc:"Fortnite · Rocket League · Store",url:"https://www.epicgames.com/account/personal",steps:["epicgames.com/account → Seguridad → Historial de inicio","Activar 2FA con app autenticadora","Revisar plataformas conectadas (PSN, Xbox, etc.)","Desconectar cuentas de plataformas no utilizadas","Verificar historial de compras y V-Bucks"]},
  {id:"nintendo",cat:"gaming",icon:"🔴",name:"Nintendo Account",desc:"Switch · eShop · NSO",url:"https://accounts.nintendo.com",steps:["accounts.nintendo.com → Seguridad → Registro de inicio de sesión","Activar verificación en 2 pasos con app","Revisar consolas registradas como principales","Control Parental para cuentas de menores","Verificar suscripciones NSO activas"]},
  {id:"riot",cat:"gaming",icon:"⚡",name:"Riot Games",desc:"Valorant · LoL · TFT",url:"https://account.riotgames.com/",steps:["account.riotgames.com → Seguridad → Historial de inicio","Activar 2FA con app autenticadora","Revisar regiones y cuentas vinculadas","Verificar transacciones de RP recientes","Revisar clubs y torneos configurados"]},
  {id:"blizzard",cat:"gaming",icon:"🌀",name:"Battle.net",desc:"WoW · Diablo · Overwatch",url:"https://account.blizzard.com",steps:["account.blizzard.com → Seguridad → Historial de acceso","Activar Blizzard Authenticator (app)","Revisar intentos fallidos de inicio de sesión","Actualizar email y SMS de recuperación","Revisar juegos y suscripciones activas"]},
  {id:"twitch",cat:"gaming",icon:"💜",name:"Twitch",desc:"Streaming · Clips · Drops",url:"https://www.twitch.tv/settings/security",steps:["twitch.tv/settings/security → Activar 2FA","Revocar acceso de apps de terceros antiguas","Revisar correos de seguridad recibidos","Revisar historial de suscripciones y bits","Verificar roles asignados en canales de terceros"]},
  {id:"roblox",cat:"gaming",icon:"🟥",name:"Roblox",desc:"Metaverso · Robux · Creator",url:"https://www.roblox.com/my/account#!/security",steps:["Ajustes → Seguridad → Activar 2FA con app","Cerrar todas las sesiones activas","Verificar transacciones de Robux recientes","Configurar restricciones de privacidad adecuadas","Revisar grupos y permisos de desarrollador"]},
  // Social
  {id:"google",cat:"social",icon:"🔵",name:"Google",desc:"Gmail · YouTube · Drive · Pay",url:"https://myaccount.google.com/security-checkup",steps:["myaccount.google.com → Comprobación de seguridad completa","Actividad reciente → Revisar cada inicio de sesión","Revocar acceso de apps de terceros no reconocidas","Activar 2FA con Google Prompt o llave física","Actualizar teléfono y email de rescate"]},
  {id:"facebook",cat:"social",icon:"📘",name:"Facebook / Meta",desc:"Perfil · Grupos · Marketplace",url:"https://www.facebook.com/settings?tab=security",steps:["Config → Seguridad y privacidad → Dónde iniciaste sesión","Cerrar TODAS las sesiones desconocidas de una vez","Activar alertas de inicio de sesión por email","Revocar todas las apps conectadas que no reconoces","Comprobar email y teléfono de recuperación"]},
  {id:"instagram",cat:"social",icon:"📷",name:"Instagram",desc:"Fotos · Stories · Reels",url:"https://www.instagram.com/accounts/login_activity/",steps:["Config → Seguridad → Actividad de inicio de sesión","Cerrar sesiones en dispositivos no reconocidos","Activar 2FA con app autenticadora (no SMS)","Revocar acceso de apps autorizadas antiguas","Descargar tu información: Config → Tu actividad"]},
  {id:"tiktok",cat:"social",icon:"🎵",name:"TikTok",desc:"Vídeos · Live · Shop",url:"https://www.tiktok.com/setting/",steps:["Perfil → Config → Seguridad → Actividad de inicio","Gestionar dispositivos con sesión activa","Activar verificación en 2 pasos","Revisar apps de terceros conectadas","Configurar privacidad: quién ve tu contenido"]},
  {id:"linkedin",cat:"social",icon:"💼",name:"LinkedIn",desc:"Red profesional · Jobs",url:"https://www.linkedin.com/psettings/sign-in-&-security",steps:["Ajustes → Inicio de sesión y seguridad → Dónde iniciaste","Activar verificación en 2 pasos","Revisar y revocar todas las apps de terceros","Configurar la visibilidad de tu perfil","Revisar solicitudes de conexión pendientes"]},
  {id:"discord",cat:"social",icon:"🟣",name:"Discord",desc:"Comunidades · Voz · Nitro",url:"https://discord.com/settings/sessions",steps:["Ajustes → Privacidad y seguridad → Sesiones activas","Cerrar todas las sesiones excepto la actual","Activar 2FA (obligatorio para moderar servidores)","Revisar bots con acceso a tus servidores","Actualizar email y teléfono de respaldo"]},
  {id:"reddit",cat:"social",icon:"🟠",name:"Reddit",desc:"Foros · Comunidades",url:"https://www.reddit.com/settings/privacy",steps:["Config → Privacidad y seguridad → Dispositivos","Activar 2FA con app autenticadora (nunca SMS)","Verificar correo asociado a la cuenta","Revisar comunidades moderadas y permisos","Verificar historial de premios"]},
  {id:"snapchat",cat:"social",icon:"👻",name:"Snapchat",desc:"Mensajes · Snaps · Spotlight",url:"https://accounts.snapchat.com/",steps:["accounts.snapchat.com → Mis datos → Historial de accesos","Activar verificación en 2 pasos","Configurar quién puede contactarte y ver tu ubicación","Revisar sesiones activas en todos los dispositivos","Limpiar caché y conversaciones antiguas"]},
  // Email & Chat
  {id:"gmail",cat:"email",icon:"📧",name:"Gmail",desc:"Google Mail · Filtros · Alias",url:"https://myaccount.google.com/security",steps:["myaccount.google.com → Seguridad → Actividad reciente","Verificar filtros y reglas de reenvío automático","Revocar acceso de apps de terceros al correo","Revisar alias y cuentas vinculadas","Activar avisos de actividad inusual"]},
  {id:"yahoo",cat:"email",icon:"💜",name:"Yahoo Mail",desc:"Correo · Noticias",url:"https://login.yahoo.com/account/security",steps:["account.yahoo.com → Seguridad → Actividad reciente","Revisar y revocar apps de terceros conectadas","Actualizar teléfono y email de recuperación","Verificar reenvíos automáticos configurados","Revisar la clave de cuenta Yahoo para apps"]},
  {id:"outlook",cat:"email",icon:"📫",name:"Outlook / Hotmail",desc:"Microsoft Mail · Calendar",url:"https://account.microsoft.com/security",steps:["account.microsoft.com → Seguridad → Actividad reciente","Activar 2FA con Microsoft Authenticator","Comprobar alias de correo activos","Revisar dispositivos de confianza registrados","Verificar reglas de bandeja de entrada"]},
  {id:"proton",cat:"email",icon:"🔒",name:"ProtonMail",desc:"Email cifrado E2E · Drive",url:"https://account.proton.me/",steps:["account.proton.me → Seguridad → Historial de autenticación","Activar 2FA con app TOTP autenticadora","Revisar vencimiento de claves PGP activas","Cerrar sesiones activas en dispositivos desconocidos","Gestionar alias de email configurados"]},
  {id:"telegram",cat:"email",icon:"✈️",name:"Telegram",desc:"Mensajería · Canales · Bots",url:"https://my.telegram.org",steps:["Ajustes → Privacidad y seguridad → Sesiones activas → Cerrar otras","Activar contraseña de cuenta + verificación en 2 pasos","Revisar bots con acceso a tus mensajes","Configurar autodestrucción si cuenta inactiva","Ajustar quién puede ver tu número: Solo contactos"]},
  {id:"whatsapp",cat:"email",icon:"💬",name:"WhatsApp",desc:"Mensajería · Grupos · Llamadas",url:"https://web.whatsapp.com/",steps:["Ajustes → Dispositivos vinculados → Cerrar todos los desconocidos","Activar verificación en dos pasos (PIN de 6 dígitos)","Configurar email de recuperación del PIN","Ajustar privacidad: foto de perfil y estado","Salir de grupos que no reconoces"]},
  {id:"signal",cat:"email",icon:"🔐",name:"Signal",desc:"Cifrado E2E · Llamadas",url:"https://signal.org/",steps:["Ajustes → Cuenta → Activar PIN de Signal","Activar bloqueo de pantalla en la app","Revocar dispositivos vinculados no reconocidos","Verificar copias de seguridad cifradas","Configurar mensajes efímeros por defecto"]},
  // Streaming
  {id:"netflix",cat:"stream",icon:"🔴",name:"Netflix",desc:"Series · Películas · Juegos",url:"https://www.netflix.com/YourAccount",steps:["Mi cuenta → Acceso y contraseña → Gestionar el acceso","Revisar actividad reciente y ubicaciones de inicio","Cerrar sesión en TODOS los dispositivos de una vez","Activar notificaciones de inicio de sesión","Verificar plan activo y método de pago"]},
  {id:"spotify",cat:"stream",icon:"🟢",name:"Spotify",desc:"Música · Podcasts · Audiolibros",url:"https://www.spotify.com/es/account/apps/",steps:["account.spotify.com → Seguridad → Acceso reciente","Cerrar sesión en todos los dispositivos","Revocar acceso de apps de terceros","Verificar suscripción y fecha de renovación","Revisar redes sociales conectadas"]},
  {id:"amazon",cat:"stream",icon:"📦",name:"Amazon / Prime",desc:"Tienda · Video · Music · Audible",url:"https://www.amazon.es/gp/css/account/info/view.html",steps:["Mi cuenta → Inicio de sesión y seguridad → Actividad","Revisar dispositivos registrados en Amazon","Verificar suscripciones activas: Prime, Music, Audible…","Eliminar métodos de pago obsoletos","Verificar direcciones de envío guardadas"]},
  {id:"disney",cat:"stream",icon:"✨",name:"Disney+",desc:"Disney · Marvel · Star Wars · Pixar",url:"https://www.disneyplus.com/",steps:["Perfil → Cuenta → Dispositivos → Ver todos los activos","Cerrar sesión en dispositivos desconocidos","Activar contraseñas de perfil individuales","Revisar plan familiar y miembros","Verificar método de pago y renovación"]},
  {id:"hbomax",cat:"stream",icon:"🎬",name:"Max / HBO",desc:"HBO · Max Originals · DC",url:"https://www.max.com/",steps:["Mi cuenta → Seguridad → Historial de inicio de sesión","Gestionar y desconectar dispositivos activos","Revisar perfiles creados y quién los usa","Verificar suscripción y fecha de renovación","Comprobar método de pago registrado"]},
  // Finanzas
  {id:"paypal",cat:"finance",icon:"🅿️",name:"PayPal",desc:"Pagos · Transferencias · Crédito",url:"https://www.paypal.com/myaccount/security/",steps:["Config → Seguridad → Actividad reciente → Ver todo","Activar notificaciones para CADA transacción","Revisar y cancelar pagos automáticos autorizados","Eliminar métodos de pago que ya no uses","Activar 2FA con app autenticadora"]},
  {id:"revolut",cat:"finance",icon:"💳",name:"Revolut",desc:"Banco digital · Cripto · Viajes",url:"https://app.revolut.com/",steps:["Perfil → Seguridad → Dispositivos conectados: revocar desconocidos","Activar bloqueo biométrico y PIN seguro","Congelar o eliminar tarjetas virtuales no usadas","Congelar tarjeta principal si hay actividad sospechosa","Activar notificaciones para todas las transacciones"]},
  {id:"wise",cat:"finance",icon:"💱",name:"Wise",desc:"Transferencias internacionales",url:"https://wise.com/es/settings/",steps:["Config → Seguridad → Historial de inicio de sesión","Activar 2FA con app autenticadora","Revisar y eliminar destinatarios guardados obsoletos","Verificar cuentas multi-divisa activas","Revisar historial de transferencias recientes"]},
  {id:"binance",cat:"finance",icon:"🟡",name:"Binance",desc:"Exchange cripto · Staking · Web3",url:"https://www.binance.com/es/my/security",steps:["Seguridad → Gestión de dispositivos → Revocar desconocidos","Activar Google Authenticator (NUNCA usar SMS para cripto)","Revisar y revocar todos los permisos de API","Activar lista blanca de direcciones de retiro","Configurar código anti-phishing en ajustes"]},
  {id:"coinbase",cat:"finance",icon:"🔵",name:"Coinbase",desc:"Cripto · Wallet · Staking",url:"https://www.coinbase.com/settings/security",steps:["Config → Seguridad → Historial de inicio de sesión","Activar 2FA con app autenticadora (NUNCA SMS)","Revocar API keys no usadas o sospechosas","Activar bloqueo avanzado de la cuenta","Desconectar dApps antiguas de Coinbase Wallet"]},
  {id:"stripe",cat:"finance",icon:"💎",name:"Stripe",desc:"Pagos API · Atlas · Billing",url:"https://dashboard.stripe.com/settings/user",steps:["Dashboard → Perfil → Seguridad → Activar 2FA","Rotar claves API si ha habido actividad sospechosa","Verificar webhooks configurados en endpoints","Revisar usuarios del equipo y sus roles","Activar Stripe Radar para detectar fraude"]},
  // Trabajo
  {id:"slack",cat:"work",icon:"💬",name:"Slack",desc:"Mensajería · Canales · Huddles",url:"https://slack.com/account/settings",steps:["Ajustes de cuenta → Seguridad → Sesiones activas","Cerrar sesión en workspaces desconocidos","Activar 2FA (obligatorio en planes Enterprise)","Revisar permisos de apps y bots integrados","Verificar workspaces a los que perteneces"]},
  {id:"notion",cat:"work",icon:"📝",name:"Notion",desc:"Notas · Docs · Bases de datos · AI",url:"https://www.notion.so/profile/security",steps:["Ajustes → Mi cuenta → Seguridad → Sesiones activas","Activar 2FA con app autenticadora","Revisar apps conectadas con acceso a tu cuenta","Revisar espacios de trabajo compartidos","Auditar páginas publicadas públicamente"]},
  {id:"github",cat:"work",icon:"🐙",name:"GitHub",desc:"Código · Repos · Actions · Copilot",url:"https://github.com/settings/security",steps:["Ajustes → Contraseña y autenticación → Historial de seguridad","Activar 2FA (GitHub lo exige obligatoriamente)","Revocar tokens de acceso personal obsoletos","Revisar todas las apps OAuth autorizadas","Verificar deploy keys en repositorios"]},
  {id:"gitlab",cat:"work",icon:"🦊",name:"GitLab",desc:"DevOps · CI/CD · Repos",url:"https://gitlab.com/-/profile/account",steps:["Perfil → Preferencias → Seguridad → Activar 2FA","Revocar tokens de acceso personal no usados","Cerrar sesiones activas en dispositivos desconocidos","Verificar claves SSH registradas","Revisar grupos y proyectos con acceso"]},
  {id:"figma",cat:"work",icon:"🎨",name:"Figma",desc:"Diseño UI · Prototipado · Dev Mode",url:"https://www.figma.com/settings",steps:["Config → Cuenta → Seguridad → Sesiones activas","Activar 2FA con app autenticadora","Revisar apps de terceros con acceso","Revisar miembros de equipos y organizaciones","Auditar archivos publicados públicamente"]},
  {id:"zoom",cat:"work",icon:"🎥",name:"Zoom",desc:"Videollamadas · Webinars · Clips",url:"https://zoom.us/profile",steps:["Perfil → Seguridad → Activar 2FA","Cerrar sesiones activas en dispositivos desconocidos","Revisar apps integradas de Zoom Marketplace","Gestionar grabaciones en la nube y su acceso","Asegurar que reuniones recurrentes tienen contraseña"]},
  {id:"dropbox",cat:"work",icon:"📂",name:"Dropbox",desc:"Cloud · Paper · Transfer · Sign",url:"https://www.dropbox.com/account/security",steps:["Seguridad → Sesiones web activas → Cerrar desconocidas","Revocar dispositivos vinculados obsoletos","Activar 2FA con app autenticadora","Revisar apps de terceros con acceso","Auditar carpetas y archivos compartidos con externos"]},
  // Cloud & Tech
  {id:"apple",cat:"cloud",icon:"🍎",name:"Apple ID / iCloud",desc:"iPhone · Mac · App Store · Pay · TV",url:"https://appleid.apple.com/",steps:["appleid.apple.com → Seguridad → 2FA obligatorio","Revisar y eliminar dispositivos vinculados no reconocidos","Actualizar emails de rescate verificados","Activar Protección Avanzada de Datos (cifrado E2E)","Verificar suscripciones: App Store, iCloud+, Apple One"]},
  {id:"adobe",cat:"cloud",icon:"🅰️",name:"Adobe Creative Cloud",desc:"Photoshop · Premiere · Acrobat · AI",url:"https://account.adobe.com/security",steps:["account.adobe.com → Seguridad → Historial de inicio de sesión","Activar 2FA con app autenticadora","Revisar dispositivos autorizados para Creative Cloud","Verificar suscripciones y fechas de renovación","Auditar proyectos y archivos compartidos"]},
  {id:"microsoft",cat:"cloud",icon:"🪟",name:"Microsoft 365",desc:"Office · OneDrive · Teams · Copilot",url:"https://account.microsoft.com/",steps:["account.microsoft.com → Seguridad → Actividad reciente","Revocar dispositivos registrados no reconocidos","Activar 2FA con Microsoft Authenticator","Verificar licencias y suscripciones activas","Revisar apps con acceso OAuth a tu cuenta"]},
  {id:"openai",cat:"cloud",icon:"🤖",name:"ChatGPT / OpenAI",desc:"GPT-4 · DALL-E · Sora · API · Plus",url:"https://platform.openai.com/settings",steps:["platform.openai.com → Config → Activar 2FA","Revocar claves API que no estés usando","Configurar un límite máximo de gasto mensual","Desactivar historial de conversaciones si lo prefieres","Revisar GPTs personalizados publicados"]},
  // Compras
  {id:"ebay",cat:"shop",icon:"🛍️",name:"eBay",desc:"Subastas · Compras · Ventas",url:"https://www.ebay.es/",steps:["Mi eBay → Cuenta → Información personal → Seguridad","Activar 2FA para la cuenta","Revisar anuncios activos como vendedor","Verificar métodos de pago guardados","Revisar historial de compras recientes"]},
  {id:"wallapop",cat:"shop",icon:"🟠",name:"Wallapop",desc:"Segunda mano · España · Envíos",url:"https://es.wallapop.com/",steps:["Perfil → Config → Seguridad → Cambiar contraseña","Verificar teléfono y email asociados","Revisar chats activos y conversaciones","Verificar historial de transacciones","Revisar visibilidad de artículos publicados"]},
  {id:"vinted",cat:"shop",icon:"🟢",name:"Vinted",desc:"Ropa segunda mano · Subscripción",url:"https://www.vinted.es/",steps:["Perfil → Config de cuenta → Cambiar contraseña","Verificar teléfono y email","Revisar pagos activos y métodos guardados","Verificar historial de compras y ventas","Revisar valoraciones y visibilidad del perfil"]},
  {id:"booking",cat:"shop",icon:"🏨",name:"Booking.com",desc:"Hoteles · Vuelos · Atracciones",url:"https://account.booking.com/sign-in",steps:["Mi cuenta → Seguridad → Activar 2FA","Revisar historial de inicio de sesión","Eliminar tarjetas de crédito guardadas no usadas","Verificar todas las reservas activas","Comprobar nivel Genius y beneficios"]},
  {id:"airbnb",cat:"shop",icon:"🏠",name:"Airbnb",desc:"Alojamientos · Experiencias",url:"https://www.airbnb.es/account-settings/login-and-security",steps:["Cuenta → Inicio de sesión y seguridad → Dispositivos recientes","Activar 2FA","Verificar reservas activas como huésped y anfitrión","Actualizar métodos de cobro y pago","Revisar estado de la verificación de identidad"]},
  // Otros
  {id:"canva",cat:"other",icon:"🎨",name:"Canva",desc:"Diseño · Templates · Brand · AI",url:"https://www.canva.com/settings/",steps:["Config → Seguridad → Sesiones activas","Activar 2FA con app autenticadora","Revisar apps de terceros con acceso","Revisar miembros de equipos y organizaciones","Auditar diseños publicados o compartidos públicamente"]},
  {id:"patreon",cat:"other",icon:"🎭",name:"Patreon",desc:"Membresías · Creadores · Tienda",url:"https://www.patreon.com/settings/security",steps:["Config → Seguridad → Activar 2FA","Cerrar sesiones activas no reconocidas","Actualizar métodos de pago guardados","Revisar membresías activas y sus beneficios","Gestionar privacidad de creadores seguidos"]},
];

/* ─── BRECHAS DOCUMENTADAS ──────────────────────────── */
const BREACHES = {
  linkedin:{n:"LinkedIn",y:2021,c:"533 M",s:"ALTO",f:["Nombre completo","Email","Teléfono","Empresa","Cargo","URL perfil"],d:"Scraping masivo de perfiles públicos y privados. Datos ampliamente usados en campañas de phishing laboral y fraude de identidad profesional."},
  facebook:{n:"Facebook",y:2021,c:"533 M",s:"CRÍTICO",f:["Teléfono","Email","Nombre","Localización","Fecha nac.","Género","Estado civil"],d:"Vulnerabilidad en 'Importar contactos'. 106 países afectados. Uno de los datasets más usados en estafas de suplantación de identidad a escala global."},
  snapchat:{n:"Snapchat",y:2014,c:"4.6 M",s:"MEDIO",f:["Nombre de usuario","Teléfono (parcial)"],d:"Base de datos publicada tras ignorar durante meses los avisos de investigadores de seguridad independientes."},
  discord:{n:"Discord.io",y:2023,c:"760 K",s:"ALTO",f:["Usuario","Email","Hash contraseña","Dirección IP","Fecha de registro"],d:"Servicio no oficial de invitaciones comprometido. El operador fue arrestado por las autoridades policiales."},
  reddit:{n:"Reddit",y:2018,c:"N/A",s:"ALTO",f:["Email","Usuario","Hash contraseña","Mensajes privados 2005-2007"],d:"Interceptación de códigos SMS en el proceso de 2FA. Principal argumento contra usar SMS como segundo factor de autenticación."},
  twitch:{n:"Twitch",y:2021,c:"125 GB",s:"ALTO",f:["Código fuente completo","Ingresos de streamers","Proyectos internos no anunciados"],d:"Mala configuración de servidor Git. Expuso el código fuente íntegro de Twitch y datos financieros internos de creadores."},
  spotify:{n:"Spotify",y:2020,c:"350 K",s:"MEDIO",f:["Email","Contraseña","País","Usuario"],d:"Credential stuffing usando bases de datos de contraseñas de otras brechas. Contraseñas reutilizadas comprometidas."},
  yahoo:{n:"Yahoo",y:2016,c:"3.000 M",s:"CRÍTICO",f:["Email","Contraseña MD5 (sin sal)","Nombre","Teléfono","Fecha nac.","Preguntas de seguridad (texto plano)"],d:"La mayor brecha de la historia. TODAS las cuentas Yahoo afectadas. Las preguntas de seguridad en texto plano comprometieron además otras cuentas vinculadas."},
  adobe:{n:"Adobe",y:2013,c:"153 M",s:"CRÍTICO",f:["Email","Contraseña 3DES (débil)","Usuario","Pista de contraseña (texto plano)"],d:"Cifrado obsoleto (3DES) y pistas en texto plano. El análisis cruzado de pistas y hashes permitió descifrar millones de contraseñas reales."},
  dropbox:{n:"Dropbox",y:2012,c:"68.6 M",s:"ALTO",f:["Email","Hash contraseña (bcrypt/SHA1)"],d:"Tardó 4 años en aparecer públicamente. Las contraseñas hasheadas son vulnerables a ataques de diccionario offline."},
  paypal:{n:"PayPal",y:2022,c:"34.9 K",s:"CRÍTICO",f:["Nombre completo","Fecha nac.","Dirección postal","Historial de transacciones"],d:"Credential stuffing con datos de otras brechas. Datos financieros y personales muy sensibles expuestos a los atacantes."},
  binance:{n:"Binance",y:2019,c:"~40 M$",s:"CRÍTICO",f:["Fotos KYC","Claves API","7.000 BTC robados"],d:"Phishing sofisticado y exploits de API. Binance cubrió las pérdidas con su fondo de reserva SAFU. Mayor brecha en un exchange cripto."},
  coinbase:{n:"Coinbase",y:2021,c:"6.000",s:"CRÍTICO",f:["Email","Teléfono","Nombre completo","Acceso directo a cuentas y fondos"],d:"Vulnerabilidad en el proceso de recuperación por SMS. Atacantes vaciaron las cuentas de 6.000 clientes verificados."},
  github:{n:"GitHub",y:2020,c:"N/A",s:"ALTO",f:["Email","Hash de contraseña"],d:"Credential stuffing con contraseñas reutilizadas. GitHub forzó un reset masivo preventivo de contraseñas de todas las cuentas potencialmente afectadas."},
  uber:{n:"Uber",y:2016,c:"57 M",s:"ALTO",f:["Email","Nombre completo","Número de teléfono"],d:"Uber pagó 100.000$ a los atacantes para ocultar la brecha. La notificó más de un año después. Fue multada con millones por las autoridades reguladoras."},
  slack:{n:"Slack",y:2015,c:"N/A",s:"MEDIO",f:["Email","Hash contraseña (bcrypt)","Número de teléfono","Usuario"],d:"Brecha en la base de datos principal de usuarios. Slack forzó un reset masivo preventivo de contraseñas de todos los afectados."},
  openai:{n:"OpenAI / ChatGPT",y:2023,c:"N/A",s:"MEDIO",f:["Historial de conversaciones","Datos de pago (parciales)","Emails de usuarios"],d:"Vulnerabilidad en un componente Redis expuso el historial de chats activos y datos de suscripción de usuarios durante un período de tiempo."},
};

/* ─── PATRONES DE DETECCIÓN ─────────────────────────── */
const SMS_PAT=[
  {r:/urgente|inmediato|acción requerida|actúa ahora|expira hoy|actúe ahora/i,m:"Lenguaje de urgencia extrema",p:25},
  {r:/has? ganado|winner|has won|premio|regalo gratis|gift card|sorteo|lotería/i,m:"Promesa de premio o regalo",p:30},
  {r:/cuenta (bloqueada?|suspendida?|desactivada?|verificar)/i,m:"Amenaza de bloqueo de cuenta",p:30},
  {r:/contraseña|password|datos bancarios|tarjeta|iban|pin|número de tarjeta|cvc/i,m:"Solicita credenciales o datos bancarios",p:35},
  {r:/banco|bbva|santander|caixabank|sabadell|ing|paypal|amazon|apple|google|correos|hacienda|dgt/i,m:"Suplanta entidad financiera o gubernamental",p:22},
  {r:/http:\/\/|bit\.ly|tinyurl|cutt\.ly|ow\.ly|short\.link/i,m:"Enlace acortado o HTTP sin cifrar",p:25},
  {r:/paquete|entrega|envío|aduanas|dhl|fedex|ups|mensajería/i,m:"Posible estafa de entrega de paquete",p:20},
  {r:/tu iphone|tu dispositivo|virus detectado|infected|malware|troyano/i,m:"Alerta falsa de virus en el dispositivo",p:35},
  {r:/código de seguridad|otp|código de verificación|código único|código de acceso/i,m:"Solicita código OTP de seguridad",p:30},
  {r:/haz clic|pincha aquí|accede ahora|click here|verify now|confirma tu identidad/i,m:"Solicita acción urgente en un enlace",p:15},
  {r:/multa|infracción|denuncia|guardia civil|policía|agencia tributaria|hacienda/i,m:"Suplanta autoridad o administración pública",p:28},
  {r:/refinanc|deuda|préstamo|crédito rápido|dinero fácil/i,m:"Posible fraude financiero o préstamo fraudulento",p:20},
];
const EMAIL_PAT=[
  {r:/urgente|acción requerida|actúa inmediatamente|expira en \d+/i,m:"Lenguaje de urgencia extrema",p:25},
  {r:/has? ganado|winner|premio|gift card|sorteo/i,m:"Promesa de premio o beneficio",p:30},
  {r:/contraseña|password|datos bancarios|tarjeta|número de cuenta|pin|cvc/i,m:"Solicita credenciales o datos bancarios",p:35},
  {r:/haz clic aquí|click here|accede ahora|verifica tu cuenta|confirma tu identidad/i,m:"Solicita acción urgente en un enlace",p:20},
  {r:/banco|hacienda|correos|dhl|ups|fedex|amazon|microsoft/i,m:"Suplanta entidad financiera o empresa conocida",p:22},
  {r:/http:\/\/|bit\.ly|tinyurl\.com/i,m:"Enlace sin HTTPS o acortado",p:20},
  {r:/su cuenta (ha sido|será|está) (bloqueada?|suspendida?|cancelada?)/i,m:"Amenaza de suspensión de cuenta",p:28},
  {r:/no respondas? a este (email|correo)|noreply|no-reply/i,m:"Email de no respuesta (sin remitente real)",p:10},
  {r:/adjunto|attachment|archivo adjunto|descarga el siguiente|ejecuta el archivo/i,m:"Solicita abrir adjunto (posible malware)",p:30},
  {r:/actualiza tu (información|datos|tarjeta|método de pago)/i,m:"Solicita actualizar datos de pago o personales",p:25},
];
const PHISH_DOMAINS=["secure-login-apple.com","appleid-verify.net","paypal-secure.net","amazon-login-verify.com","icloud-locked.net","apple-payment-failed.com","paypa1.com","amaz0n.com","g00gle.com","instagram-verify-account.com","crypto-free-reward.com","your-device-has-virus.com","bank-secure-login.net","netflix-update-billing.com","microsoft-security-update.com","google-account-verify.net","facebook-login-secure.net","binance-verify-account.com","coinbase-secure-login.net"];
const PORTS=[
  {port:21,proto:"TCP",svc:"FTP",risk:"ALTO",st:"filtrado",desc:"Transferencia de archivos sin cifrar — usar SFTP (puerto 22)"},
  {port:22,proto:"TCP",svc:"SSH",risk:"MEDIO",st:"cerrado",desc:"Acceso remoto cifrado — deshabilitar si no se usa"},
  {port:23,proto:"TCP",svc:"Telnet",risk:"CRÍTICO",st:"cerrado",desc:"Acceso remoto sin cifrar — protocolo completamente obsoleto"},
  {port:25,proto:"TCP",svc:"SMTP",risk:"MEDIO",st:"filtrado",desc:"Envío de correo electrónico — puede usarse para spam"},
  {port:53,proto:"UDP",svc:"DNS",risk:"BAJO",st:"abierto",desc:"Resolución de nombres de dominio — usar DNS cifrado (DoH/DoT)"},
  {port:80,proto:"TCP",svc:"HTTP",risk:"MEDIO",st:"abierto",desc:"Web sin cifrar — nunca introduzcas datos personales"},
  {port:443,proto:"TCP",svc:"HTTPS",risk:"BAJO",st:"abierto",desc:"Web cifrada con TLS ✓"},
  {port:445,proto:"TCP",svc:"SMB / Samba",risk:"CRÍTICO",st:"cerrado",desc:"Compartición de archivos Windows — objetivo principal de ransomware (WannaCry, NotPetya)"},
  {port:1433,proto:"TCP",svc:"MS SQL Server",risk:"ALTO",st:"cerrado",desc:"Base de datos Microsoft SQL — nunca exponer públicamente"},
  {port:3306,proto:"TCP",svc:"MySQL",risk:"ALTO",st:"cerrado",desc:"Base de datos MySQL — nunca exponer sin autenticación"},
  {port:3389,proto:"TCP",svc:"RDP",risk:"CRÍTICO",st:"cerrado",desc:"Escritorio remoto Windows — uno de los puertos más atacados del mundo"},
  {port:4444,proto:"TCP",svc:"Metasploit",risk:"CRÍTICO",st:"cerrado",desc:"Puerto por defecto de frameworks de exploit — indicador de actividad maliciosa"},
  {port:5555,proto:"TCP",svc:"ADB Android",risk:"ALTO",st:"cerrado",desc:"Android Debug Bridge — desactivar en Opciones de desarrollador cuando no se use"},
  {port:6379,proto:"TCP",svc:"Redis",risk:"CRÍTICO",st:"cerrado",desc:"Base de datos en memoria — frecuentemente expuesta sin autenticación"},
  {port:8080,proto:"TCP",svc:"HTTP Proxy",risk:"MEDIO",st:"filtrado",desc:"Puerto alternativo para servidores web y proxies"},
  {port:9050,proto:"TCP",svc:"Tor SOCKS",risk:"ALTO",st:"cerrado",desc:"Proxy de la red Tor — puede indicar tráfico anónimo"},
  {port:27017,proto:"TCP",svc:"MongoDB",risk:"CRÍTICO",st:"cerrado",desc:"Base de datos NoSQL — miles de instancias expuestas sin autenticación"},
  {port:31337,proto:"TCP",svc:"Back Orifice",risk:"CRÍTICO",st:"cerrado",desc:"Backdoor clásico documentado — indicador claro de infección"},
];

/* ─── UTILS ─────────────────────────────────────────── */
const sleep = ms => new Promise(r => setTimeout(r, ms));
const analyze = (txt, pats, thresh) => {
  const hits = []; let sc = 0;
  pats.forEach(p => { if (p.r.test(txt)) { hits.push(p.m); sc += p.p; } });
  sc = Math.min(sc, 100);
  return { hits, score:sc, level: sc >= thresh ? "danger" : sc > 0 ? "warn" : "ok" };
};

/* ─── ATOMS ─────────────────────────────────────────── */
function Spin({ sz=13, col=C.blue }) {
  return <span style={{ display:"inline-block", width:sz, height:sz, border:`2px solid ${col}25`, borderTopColor:col, borderRadius:"50%", animation:"_sp .6s linear infinite", verticalAlign:"middle", flexShrink:0 }} />;
}
function SevBadge({ s }) {
  const col = SEV[s] || "#888";
  return <span style={{ display:"inline-flex", alignItems:"center", gap:4, padding:"2px 9px", borderRadius:20, fontSize:9, fontWeight:700, fontFamily:C.mono, letterSpacing:".07em", color:col, background:`${col}18`, border:`1px solid ${col}38`, whiteSpace:"nowrap", flexShrink:0 }}>
    <span style={{ width:5, height:5, borderRadius:"50%", background:col, flexShrink:0 }} />{s}
  </span>;
}
function StatusPill({ type, text, blink }) {
  const m = { safe:{ bg:"rgba(34,197,94,.1)", c:C.green, b:"rgba(34,197,94,.25)" }, warn:{ bg:"rgba(245,158,11,.1)", c:C.amber, b:"rgba(245,158,11,.25)" }, danger:{ bg:"rgba(239,68,68,.1)", c:C.red, b:"rgba(239,68,68,.25)" }, scan:{ bg:"rgba(37,99,235,.1)", c:C.blue, b:"rgba(37,99,235,.25)" } };
  const s = m[type] || m.safe;
  return <div style={{ display:"flex", alignItems:"center", gap:6, padding:"5px 13px", borderRadius:20, fontSize:11, fontWeight:700, letterSpacing:".02em", background:s.bg, color:s.c, border:`1px solid ${s.b}` }}>
    <span style={{ width:7, height:7, borderRadius:"50%", background:s.c, animation: blink ? "_pl .8s infinite" : "none" }} />{text}
  </div>;
}
function ResultBox({ res }) {
  if (!res) return null;
  const ok = res.level === "ok", warn = res.level === "warn";
  const col = ok ? C.green : warn ? C.amber : C.red;
  const bg = ok ? "rgba(34,197,94,.05)" : warn ? "rgba(245,158,11,.05)" : "rgba(239,68,68,.06)";
  const brd = ok ? "rgba(34,197,94,.25)" : warn ? "rgba(245,158,11,.25)" : "rgba(239,68,68,.3)";
  const title = ok ? "✅ Sin indicadores detectados" : warn ? "⚠️ Indicadores leves detectados" : "🚨 Contenido altamente sospechoso";
  return <div style={{ marginTop:12, padding:14, borderRadius:11, background:bg, border:`1px solid ${brd}` }}>
    <div style={{ fontWeight:800, fontSize:14, marginBottom:res.hits.length ? 8 : 6, color:col }}>{title}</div>
    {res.hits.length > 0 && <div style={{ fontFamily:C.mono, fontSize:9, color:C.dim, letterSpacing:".08em", marginBottom:9 }}>INDICADORES ENCONTRADOS: {res.hits.length} · PUNTUACIÓN DE RIESGO: {res.score}/100</div>}
    {res.hits.map((h, i) => <div key={i} style={{ display:"flex", gap:7, marginBottom:5 }}><span style={{ color:col, flexShrink:0, fontSize:12 }}>⚠</span><span style={{ fontSize:12, color:C.mid }}>{h}</span></div>)}
    {res.level === "danger" && <div style={{ marginTop:10, paddingTop:10, borderTop:`1px solid ${brd}`, fontSize:12, color:C.mid, lineHeight:1.6 }}><strong style={{ color:C.text }}>Recomendación:</strong> No hagas clic en ningún enlace ni proporciones datos personales. Contacta directamente con la entidad por sus canales oficiales. Puedes reportar al INCIBE llamando al <strong style={{ color:C.text }}>017</strong>.</div>}
    {res.level === "ok" && <div style={{ fontSize:12, color:C.mid, lineHeight:1.6 }}>No se detectaron patrones típicos de phishing. Actúa siempre con precaución ante solicitudes de datos o enlaces en mensajes no esperados.</div>}
  </div>;
}
function ModCard({ check, res, running, onRun }) {
  const sc = res ? (res.st==="ok" ? C.green : res.st==="warn" ? C.amber : C.red) : C.dim;
  const brd = res ? (res.st==="ok" ? "rgba(34,197,94,.3)" : res.st==="warn" ? "rgba(245,158,11,.35)" : "rgba(239,68,68,.4)") : running ? "rgba(37,99,235,.45)" : "rgba(255,255,255,.07)";
  return <div onClick={onRun} style={{ background:C.s2, border:`1px solid ${brd}`, borderRadius:13, padding:14, cursor:"pointer", position:"relative", overflow:"hidden", transition:"border-color .2s, transform .12s", userSelect:"none" }} onMouseEnter={e=>e.currentTarget.style.transform="scale(1.01)"} onMouseLeave={e=>e.currentTarget.style.transform="scale(1)"}>
    <div style={{ fontSize:22, marginBottom:8, lineHeight:1 }}>{check.ic}</div>
    <div style={{ fontSize:12, fontWeight:700, letterSpacing:"-.01em", marginBottom:3 }}>{check.n}</div>
    <div style={{ fontSize:10, fontWeight:600, fontFamily:C.mono, color: running ? C.blue : sc, lineHeight:1.4 }}>
      {running ? <><Spin sz={10} /> Analizando…</> : res ? res.msg : "Toca para analizar"}
    </div>
    <div style={{ position:"absolute", bottom:0, left:0, right:0, height:2, background: running ? C.blue : res ? sc : "transparent", borderRadius:"0 0 13px 13px", transition:"background .3s" }} />
  </div>;
}
function PRow({ r, loading, open, onToggle }) {
  const { p, breach } = r;
  const hasB = !!breach;
  const sc = hasB ? (SEV[breach.s] || C.red) : C.green;
  return <div style={{ borderBottom:"1px solid rgba(255,255,255,.04)" }}>
    <div onClick={onToggle} style={{ display:"grid", gridTemplateColumns:"3px 38px 1fr auto 14px", gap:9, alignItems:"center", padding:"12px 14px", cursor:"pointer", userSelect:"none", transition:"background .12s" }} onMouseEnter={e=>e.currentTarget.style.background="rgba(255,255,255,.025)"} onMouseLeave={e=>e.currentTarget.style.background="transparent"}>
      <div style={{ height:26, borderRadius:2, background: loading ? "rgba(255,255,255,.05)" : hasB ? sc : `${C.green}44`, boxShadow: hasB && !loading ? `0 0 8px ${sc}44` : "none" }} />
      <div style={{ width:34, height:34, borderRadius:9, background:"rgba(255,255,255,.06)", border:"1px solid rgba(255,255,255,.09)", display:"flex", alignItems:"center", justifyContent:"center", fontSize:15, flexShrink:0 }}>{p.icon}</div>
      <div style={{ overflow:"hidden" }}>
        <div style={{ fontWeight:700, fontSize:13, letterSpacing:"-.01em", color: hasB ? C.text : C.dim, overflow:"hidden", textOverflow:"ellipsis", whiteSpace:"nowrap" }}>{p.name}</div>
        <div style={{ fontSize:9, color:C.dim, marginTop:1, fontFamily:C.mono }}>{p.desc}</div>
      </div>
      {loading ? <Spin sz={12} /> : hasB ? <SevBadge s={breach.s} /> :
        <span style={{ fontSize:9, fontWeight:700, color:C.green, fontFamily:C.mono, display:"flex", alignItems:"center", gap:4, flexShrink:0 }}>
          <span style={{ width:5, height:5, borderRadius:"50%", background:C.green, flexShrink:0 }} />OK
        </span>}
      {!loading && <span style={{ color:C.dim, fontSize:9, textAlign:"center", transform: open ? "rotate(180deg)" : "none", transition:"transform .2s" }}>▼</span>}
    </div>
    {open && !loading && (
      <div style={{ padding:"4px 14px 16px 65px", borderTop:"1px solid rgba(255,255,255,.04)", background:"rgba(0,0,0,.18)" }}>
        {breach && <div style={{ margin:"12px 0 13px", padding:14, borderRadius:10, background:`${sc}0b`, border:`1px solid ${sc}28` }}>
          <div style={{ display:"flex", justifyContent:"space-between", flexWrap:"wrap", gap:8, marginBottom:8 }}>
            <div>
              <div style={{ fontFamily:C.mono, fontSize:9, color:C.dim, letterSpacing:".08em", textTransform:"uppercase", marginBottom:3 }}>BRECHA DOCUMENTADA · {breach.n} · {breach.y}</div>
              <div style={{ fontSize:18, fontWeight:800, letterSpacing:"-.02em" }}>{breach.c} <span style={{ fontSize:12, fontWeight:400, color:C.mid }}>registros expuestos</span></div>
            </div>
            <SevBadge s={breach.s} />
          </div>
          <div style={{ fontSize:12, color:C.mid, lineHeight:1.65, marginBottom:10 }}>{breach.d}</div>
          <div style={{ fontSize:9, fontWeight:700, color:C.dim, textTransform:"uppercase", letterSpacing:".08em", marginBottom:6 }}>DATOS COMPROMETIDOS</div>
          <div style={{ display:"flex", flexWrap:"wrap", gap:4 }}>
            {breach.f.map(f => <span key={f} style={{ padding:"2px 8px", borderRadius:4, fontSize:9, background:"rgba(255,255,255,.06)", color:C.mid, border:"1px solid rgba(255,255,255,.1)", fontFamily:C.mono }}>{f}</span>)}
          </div>
        </div>}
        <div style={{ fontSize:9, fontWeight:700, color:C.dim, textTransform:"uppercase", letterSpacing:".1em", margin:"11px 0 8px" }}>PASOS PARA ASEGURAR TU CUENTA</div>
        {p.steps.map((s, i) => <div key={i} style={{ display:"flex", gap:9, alignItems:"flex-start", marginBottom:7 }}>
          <div style={{ width:19, height:19, borderRadius:"50%", background:"rgba(37,99,235,.14)", border:"1px solid rgba(37,99,235,.3)", color:C.blue, fontSize:9, display:"flex", alignItems:"center", justifyContent:"center", flexShrink:0, marginTop:2, fontWeight:700, fontFamily:C.mono }}>{i+1}</div>
          <div style={{ fontSize:12, color:C.mid, lineHeight:1.6 }}>{s}</div>
        </div>)}
        <div style={{ display:"flex", gap:7, flexWrap:"wrap", marginTop:12 }}>
          <a href={p.url} target="_blank" rel="noreferrer" style={{ padding:"7px 13px", borderRadius:8, fontSize:10, fontWeight:700, fontFamily:C.mono, color:C.blue, border:"1px solid rgba(37,99,235,.3)", background:"rgba(37,99,235,.1)", letterSpacing:".05em" }}>→ Ir a seguridad</a>
          {breach && <a href="https://haveibeenpwned.com" target="_blank" rel="noreferrer" style={{ padding:"7px 13px", borderRadius:8, fontSize:10, fontWeight:700, fontFamily:C.mono, color:C.red, border:"1px solid rgba(239,68,68,.3)", background:"rgba(239,68,68,.1)", letterSpacing:".05em" }}>→ Verificar en HIBP</a>}
        </div>
      </div>
    )}
  </div>;
}

/* ─── APP ────────────────────────────────────────────── */
function App() {
  const [tab, setTab] = useState("home");
  const [stType, setStType] = useState("safe");
  const [stTxt, setStTxt] = useState("PROTEGIDO");
  const [busy, setBusy] = useState(false);
  const [toast, setToast] = useState(null);
  const toastT = useRef(null);

  // Breach
  const [email, setEmail] = useState("");
  const [user, setUser] = useState("");
  const [bRes, setBRes] = useState(null);
  const [bLoad, setBLoad] = useState({});
  const [bFilt, setBFilt] = useState("all");
  const [catF, setCatF] = useState("all");
  const [openR, setOpenR] = useState({});
  const [bRunning, setBRunning] = useState(false);

  // AV
  const [avRes, setAvRes] = useState({});
  const [avRun, setAvRun] = useState({});
  const [avScore, setAvScore] = useState(null);
  const [avDone, setAvDone] = useState(false);

  // Web
  const [urlInp, setUrlInp] = useState("");
  const [urlRes, setUrlRes] = useState(null);
  const [smsInp, setSmsInp] = useState("");
  const [smsRes, setSmsRes] = useState(null);
  const [emlInp, setEmlInp] = useState("");
  const [emlRes, setEmlRes] = useState(null);

  const showToast = useCallback((msg, type="info") => {
    setToast({ msg, type });
    clearTimeout(toastT.current);
    toastT.current = setTimeout(() => setToast(null), 4500);
  }, []);

  const setSt = (txt, type) => { setStTxt(txt); setStType(type); };

  /* ── AV checks ── */
  const AV_CHECKS = [
    { id:"ios",    ic:"📱", n:"Versión del sistema",       fn: async () => { const ua = navigator.userAgent; const m = ua.match(/CPU iPhone OS (\d+)_/) || ua.match(/CPU OS (\d+)_/); if (m) { const v = parseInt(m[1]); if (v >= 18) return { st:"ok", msg:"SO actualizado ✓ iOS "+v }; if (v >= 17) return { st:"warn", msg:"iOS "+v+" — Considera actualizar" }; return { st:"danger", msg:"iOS "+v+" — Versión antigua, riesgo alto" }; } return { st:"ok", msg:"Sistema detectado ✓" }; } },
    { id:"wifi",   ic:"📶", n:"Seguridad de red",          fn: async () => { if (!navigator.onLine) return { st:"warn", msg:"Sin conexión a internet" }; const c = navigator.connection || navigator.mozConnection; if (c?.type === "cellular") return { st:"ok", msg:"Datos móviles ✓ Más seguro" }; return { st:"warn", msg:"Wi-Fi — Usa VPN si es pública" }; } },
    { id:"https",  ic:"🔒", n:"Protocolo de conexión",     fn: async () => (location.protocol === "https:" || location.protocol === "file:") ? { st:"ok", msg:"Conexión cifrada HTTPS ✓" } : { st:"danger", msg:"Sin HTTPS — conexión insegura" } },
    { id:"priv",   ic:"🍪", n:"Cookies y rastreadores",    fn: async () => { let st="ok", msg="Cookies de terceros bloqueadas ✓"; try { const f=document.createElement("iframe"); f.style.display="none"; f.src="about:blank"; document.body.appendChild(f); f.contentWindow.document.cookie="_t=1;SameSite=None;Secure"; document.body.removeChild(f); st="warn"; msg="Cookies de terceros activas"; } catch(e){} if (navigator.doNotTrack !== "1" && st === "ok") { st="warn"; msg="Do Not Track desactivado"; } return { st, msg }; } },
    { id:"breach", ic:"🔓", n:"Estado de filtraciones",   fn: async () => bRes ? (() => { const e = Object.values(bRes).filter(r => r.breach).length; return e > 0 ? { st:"danger", msg:`${e} brechas detectadas — Actúa` } : { st:"ok", msg:"Sin brechas detectadas ✓" }; })() : { st:"warn", msg:"Ejecuta el análisis de filtraciones" } },
    { id:"dns",    ic:"🌐", n:"DNS cifrado",               fn: async () => ({ st:"warn", msg:"Configura DNS cifrado en Ajustes" }) },
    { id:"perms",  ic:"🎛️", n:"Permisos del dispositivo", fn: async () => ({ st:"warn", msg:"Revisa Ajustes → Privacidad" }) },
    { id:"clip",   ic:"📋", n:"Higiene del portapapeles",  fn: async () => ({ st:"warn", msg:"Elimina datos sensibles copiados" }) },
    { id:"2fa",    ic:"🔑", n:"Estado del 2FA",            fn: async () => ({ st:"warn", msg:"Activa 2FA en todas las cuentas clave" }) },
    { id:"phish",  ic:"🎣", n:"Base antiphishing",         fn: async () => ({ st:"ok", msg:`${PHISH_DOMAINS.length} dominios maliciosos cargados ✓` }) },
  ];

  const runFullAV = async () => {
    setAvRes({}); setAvRun({}); setAvScore(null); setAvDone(false);
    setBusy(true); setSt("Escaneando dispositivo…", "scan");
    const nr = {};
    for (let i = 0; i < AV_CHECKS.length; i++) {
      const c = AV_CHECKS[i];
      setAvRun(p => ({ ...p, [c.id]:true }));
      await sleep(260 + Math.random() * 260);
      const r = await c.fn();
      nr[c.id] = r;
      setAvRes({ ...nr });
      setAvRun(p => { const n = { ...p }; delete n[c.id]; return n; });
    }
    const ok = Object.values(nr).filter(r => r.st === "ok").length;
    const warn = Object.values(nr).filter(r => r.st === "warn").length;
    const score = Math.round((ok + warn * 0.5) / AV_CHECKS.length * 100);
    setAvScore(score); setAvDone(true); setBusy(false);
    const t = score > 80 ? "safe" : score > 50 ? "warn" : "danger";
    setSt(score > 80 ? "PROTEGIDO" : score > 50 ? "REVISAR" : "ATENCIÓN", t);
    showToast(score > 80 ? "✅ Dispositivo bien protegido." : score > 50 ? "⚠️ Hay mejoras recomendadas." : "🚨 Se requieren acciones urgentes.", t);
  };

  const runOneAV = async (id) => {
    const c = AV_CHECKS.find(x => x.id === id); if (!c) return;
    setAvRun(p => ({ ...p, [id]:true }));
    await sleep(280 + Math.random() * 400);
    const r = await c.fn();
    setAvRes(p => ({ ...p, [id]:r }));
    setAvRun(p => { const n = { ...p }; delete n[id]; return n; });
    showToast(`${c.n}: ${r.msg}`, "info");
  };

  const startScan = async () => {
    if (!email.trim() && !user.trim()) { showToast("Introduce un email o nombre de usuario.", "warn"); return; }
    setBRes(null); setBLoad({}); setBFilt("all"); setCatF("all"); setOpenR({});
    setBRunning(true); setBusy(true); setSt("Analizando filtraciones…", "scan");
    const load = {}; PLATFORMS.forEach(p => { load[p.id] = true; }); setBLoad({ ...load });
    const partial = {};
    for (let i = 0; i < PLATFORMS.length; i++) {
      const p = PLATFORMS[i];
      await sleep(6 + Math.random() * 18);
      partial[p.id] = { p, breach: BREACHES[p.id] || null };
      delete load[p.id]; setBLoad({ ...load }); setBRes({ ...partial });
    }
    setBRunning(false); setBusy(false);
    const exp = Object.values(partial).filter(r => r.breach).length;
    setSt(exp > 0 ? `${exp} RIESGOS` : "PROTEGIDO", exp > 0 ? "danger" : "safe");
    showToast(exp > 0 ? `${exp} plataformas con brechas detectadas.` : "Sin brechas en la base de datos.", exp > 0 ? "warn" : "ok");
  };

  const checkURL = () => {
    const raw = urlInp.trim().toLowerCase(); if (!raw) { showToast("Introduce una URL o dominio.", "warn"); return; }
    const dom = raw.replace(/^https?:\/\//, "").replace(/\/.*$/, "").replace(/^www\./, "");
    const iss = [];
    if (PHISH_DOMAINS.find(d => dom.includes(d) || d === dom)) iss.push("Dominio en lista de amenazas conocidas");
    if (!raw.startsWith("https")) iss.push("No usa HTTPS — la conexión no está cifrada");
    ["apple","google","paypal","amazon","microsoft","facebook","instagram","netflix","spotify","binance","coinbase"].forEach(b => {
      if (dom.includes(b) && !dom.match(new RegExp(`^${b}\\.(com|es|co\\.uk|net|org|io)$`))) iss.push(`Posible suplantación de "${b}"`);
    });
    if (dom.length > 55) iss.push("Dominio inusualmente largo — típico del phishing");
    if (dom.match(/\.(xyz|tk|ml|ga|cf|pw|gq|top|click|icu|live|vip)$/)) iss.push("Extensión de dominio de alto riesgo");
    if (dom.match(/-{2,}/)) iss.push("Múltiples guiones consecutivos — posible typosquatting");
    if (dom.match(/\d{3,}/)) iss.push("Secuencia numérica larga en el dominio");
    setUrlRes({ iss, https: raw.startsWith("https://") });
  };

  const all = bRes ? Object.values(bRes) : [];
  const exposed = all.filter(r => r.breach);
  const safe_p = all.filter(r => !r.breach);
  const brScore = all.length ? Math.round(safe_p.length / all.length * 100) : 0;
  const scCol = avScore === null ? C.dim : avScore > 80 ? C.green : avScore > 50 ? C.amber : C.red;
  const scLbl = avScore === null ? "---" : avScore > 80 ? "PROTEGIDO" : avScore > 50 ? "REVISAR" : "RIESGO";

  const getFiltered = () => {
    if (!bRes) return [];
    let base = bFilt === "exposed" ? all.filter(r => r.breach) : bFilt === "safe" ? all.filter(r => !r.breach) : all;
    if (catF !== "all") base = base.filter(r => r.p.cat === catF);
    return base;
  };

  const TABS = [
    {k:"home",l:"🏠 Inicio"},{k:"av",l:"🔬 Antivirus"},{k:"firewall",l:"🔥 Firewall"},
    {k:"breach",l:"🔓 Filtraciones"},{k:"web",l:"🌐 Web & URLs"},{k:"privacy",l:"👁 Privacidad"},
    {k:"tips",l:"📋 Guía"},{k:"about",l:"ℹ️ Info"},
  ];
  const CARD = { background:C.s1, border:"1px solid rgba(255,255,255,.07)", borderRadius:16, padding:18, marginBottom:14 };
  const ST = { fontSize:10, fontWeight:700, textTransform:"uppercase", letterSpacing:".1em", color:C.dim, marginBottom:10 };
  const INP = { width:"100%", background:"rgba(255,255,255,.05)", border:"1px solid rgba(255,255,255,.08)", borderRadius:10, padding:"11px 13px", color:C.text, fontSize:13, fontFamily:C.mono, outline:"none", transition:"border-color .2s" };
  const BTN = { display:"flex", alignItems:"center", justifyContent:"center", gap:8, padding:"13px 20px", borderRadius:12, fontSize:13, fontWeight:700, cursor:"pointer", width:"100%", border:"none", transition:"all .18s, transform .12s" };

  return (
    <div style={{ background:C.bg, minHeight:"100vh", color:C.text, fontFamily:"'SF Pro Display','Segoe UI',system-ui,sans-serif", fontSize:14, WebkitFontSmoothing:"antialiased" }}>
      <style>{`
        @keyframes _sp { to { transform: rotate(360deg); } }
        @keyframes _pl { 0%,100%{opacity:1} 50%{opacity:.2} }
        @keyframes _up { from{opacity:0;transform:translateY(10px)} to{opacity:1;transform:none} }
        @keyframes _shield { 0%,100%{filter:drop-shadow(0 4px 20px rgba(37,99,235,.45))} 50%{filter:drop-shadow(0 4px 30px rgba(37,99,235,.75))} }
        * { box-sizing: border-box; margin:0; padding:0; }
        ::-webkit-scrollbar { width:3px; height:3px; }
        ::-webkit-scrollbar-track { background:${C.bg}; }
        ::-webkit-scrollbar-thumb { background:rgba(37,99,235,.3); border-radius:3px; }
        a { color:inherit; text-decoration:none; }
        textarea { resize:none; }
        input::placeholder, textarea::placeholder { color:${C.dim}; }
        .mesh { position:fixed;inset:0;z-index:0;pointer-events:none; background:radial-gradient(ellipse 55% 40% at 8% 0%,rgba(37,99,235,.09) 0%,transparent 60%), radial-gradient(ellipse 45% 35% at 92% 100%,rgba(14,165,233,.06) 0%,transparent 55%); }
        .grid-bg { position:fixed;inset:0;z-index:0;pointer-events:none; background-image:linear-gradient(rgba(37,99,235,.022) 1px,transparent 1px),linear-gradient(90deg,rgba(37,99,235,.022) 1px,transparent 1px); background-size:50px 50px; mask-image:radial-gradient(ellipse 90% 90% at 50% 50%,black 0%,transparent 100%); -webkit-mask-image:radial-gradient(ellipse 90% 90% at 50% 50%,black 0%,transparent 100%); }
        .tc { animation: _up .3s ease; }
        .hovcell:hover { background: rgba(255,255,255,.03) !important; }
        .hovlink:hover { opacity:.8; }
        .hovmod { transition: transform .12s; }
        .hovmod:hover { transform: scale(1.015); }
        .hovmod:active { transform: scale(.96); }
      `}</style>
      <div className="mesh" /><div className="grid-bg" />

      {/* ── HEADER ── */}
      <div style={{ position:"sticky", top:0, zIndex:300, height:54, background:"rgba(7,12,24,.94)", backdropFilter:"blur(24px)", WebkitBackdropFilter:"blur(24px)", borderBottom:"1px solid rgba(37,99,235,.14)", display:"flex", alignItems:"center", justifyContent:"space-between", padding:"0 16px" }}>
        <div style={{ display:"flex", alignItems:"center", gap:10 }}>
          <div style={{ width:35, height:35, borderRadius:10, background:"linear-gradient(135deg,#2563eb,#1d4ed8)", display:"flex", alignItems:"center", justifyContent:"center", fontSize:18, boxShadow:"0 4px 16px rgba(37,99,235,.4)", animation:"_shield 3s ease-in-out infinite" }}>🛡</div>
          <div>
            <div style={{ fontSize:14, fontWeight:800, letterSpacing:"-.02em" }}>Guardian Shield</div>
            <div style={{ fontSize:8, fontFamily:C.mono, color:C.dim, letterSpacing:".08em", marginTop:1 }}>v10.0 · IGNACIO VERA · {PLATFORMS.length} PLATAFORMAS</div>
          </div>
        </div>
        <StatusPill type={stType} text={stTxt} blink={busy} />
      </div>

      {/* ── NAV ── */}
      <div style={{ position:"sticky", top:54, zIndex:200, background:"rgba(7,12,24,.9)", backdropFilter:"blur(16px)", WebkitBackdropFilter:"blur(16px)", borderBottom:"1px solid rgba(255,255,255,.06)", display:"flex", overflowX:"auto", scrollbarWidth:"none" }}>
        {TABS.map(t => (
          <button key={t.k} onClick={() => setTab(t.k)} style={{ flexShrink:0, padding:"11px 15px", background:"transparent", cursor:"pointer", border:"none", borderBottom:`2px solid ${tab===t.k ? C.blue : "transparent"}`, marginBottom:-1, fontSize:11, fontWeight:600, color: tab===t.k ? C.blue : C.dim, whiteSpace:"nowrap", letterSpacing:".01em", transition:"all .18s" }}>{t.l}</button>
        ))}
      </div>

      <div style={{ position:"relative", zIndex:10, maxWidth:840, margin:"0 auto", padding:"18px 14px 32px" }}>

        {/* ══════════════════════ INICIO ══════════════════════ */}
        {tab === "home" && <div className="tc">
          {/* Score Hero */}
          <div style={{ borderRadius:20, padding:"28px 22px", marginBottom:16, textAlign:"center", background:"linear-gradient(135deg,rgba(37,99,235,.13),rgba(14,165,233,.07))", border:"1px solid rgba(37,99,235,.22)", position:"relative", overflow:"hidden" }}>
            <div style={{ position:"absolute", top:-50, right:-50, width:180, height:180, borderRadius:"50%", background:"radial-gradient(circle,rgba(37,99,235,.08),transparent 70%)", pointerEvents:"none" }} />
            <div style={{ fontSize:54, marginBottom:6, animation:"_shield 3s ease-in-out infinite" }}>{avScore !== null && avScore > 80 ? "🛡" : avScore !== null ? "⚠️" : "🛡"}</div>
            <div style={{ fontSize:58, fontWeight:900, letterSpacing:"-.04em", lineHeight:1, color:scCol }}>{avScore !== null ? avScore : "--"}</div>
            <div style={{ fontSize:11, fontWeight:700, textTransform:"uppercase", letterSpacing:".12em", color:"rgba(241,245,249,.5)", marginTop:5, marginBottom:16 }}>{scLbl}</div>
            <div style={{ height:6, background:"rgba(255,255,255,.07)", borderRadius:6, overflow:"hidden", marginBottom:18 }}>
              <div style={{ height:"100%", borderRadius:6, width:`${avScore || 0}%`, background:`linear-gradient(90deg,${scCol},${scCol}aa)`, transition:"width 1.4s cubic-bezier(.4,0,.2,1)" }} />
            </div>
            <button onClick={() => setTab("av")} style={{ ...BTN, maxWidth:270, margin:"0 auto", background:"linear-gradient(135deg,#2563eb,#1d4ed8)", color:"#fff", border:"1px solid rgba(37,99,235,.5)", boxShadow:"0 4px 20px rgba(37,99,235,.3)", fontSize:13, padding:"12px 20px" }}>
              🔬 Ejecutar análisis completo
            </button>
          </div>

          {/* Módulos */}
          <div style={ST}>Módulos de seguridad</div>
          <div style={{ display:"grid", gridTemplateColumns:"repeat(3,1fr)", gap:9, marginBottom:16 }}>
            {[{ic:"🔬",n:"Antivirus",t:"av"},{ic:"🔥",n:"Firewall",t:"firewall"},{ic:"🔓",n:"Filtraciones",t:"breach"},{ic:"🌐",n:"Web & URLs",t:"web"},{ic:"👁",n:"Privacidad",t:"privacy"},{ic:"📋",n:"Guía",t:"tips"}].map(m => (
              <div key={m.t} onClick={() => setTab(m.t)} className="hovmod" style={{ background:C.s2, border:"1px solid rgba(255,255,255,.07)", borderRadius:13, padding:"14px 10px", textAlign:"center", cursor:"pointer" }}>
                <div style={{ fontSize:22, marginBottom:6 }}>{m.ic}</div>
                <div style={{ fontSize:11, fontWeight:700, letterSpacing:"-.01em" }}>{m.n}</div>
              </div>
            ))}
          </div>

          {/* Amenazas recientes */}
          <div style={ST}>Alertas de seguridad recientes</div>
          <div style={{ ...CARD, padding:0, overflow:"hidden" }}>
            {[
              {ic:"🎣",t:"Smishing bancario activo en España (2025)",d:"SMS suplantando entidades bancarias con enlace a formularios falsos solicitando credenciales de forma urgente.",c:"red"},
              {ic:"📧",t:"Campaña de phishing de Apple ID activa",d:"Emails falsos de soporte Apple notificando un pago fallido con enlace malicioso a sitio fraudulento.",c:"red"},
              {ic:"🔑",t:"Credential stuffing masivo en plataformas de streaming",d:"Uso automatizado de bases de datos filtradas para acceder a cuentas de Netflix, Spotify y Disney+.",c:"amber"},
              {ic:"🧅",t:"Bases de datos en circulación en dark web",d:"Datos de LinkedIn (2021) y Facebook (2021) siguen siendo activamente utilizados en ataques de ingeniería social.",c:"amber"},
              {ic:"📱",t:"Nuevas campañas de Smishing sobre paquetes DHL y Correos",d:"SMS fraudulentos avisando de un paquete retenido, solicitando pago de gastos o datos personales.",c:"amber"},
            ].map((item, i) => (
              <div key={i} style={{ padding:"12px 14px", borderBottom: i < 4 ? "1px solid rgba(255,255,255,.04)" : "none", display:"flex", gap:11, alignItems:"flex-start" }}>
                <span style={{ fontSize:18, flexShrink:0, marginTop:1 }}>{item.ic}</span>
                <div>
                  <div style={{ fontSize:12.5, fontWeight:700, color: item.c === "red" ? C.red : C.amber, marginBottom:3 }}>{item.t}</div>
                  <div style={{ fontSize:11.5, color:C.mid, lineHeight:1.5 }}>{item.d}</div>
                </div>
              </div>
            ))}
          </div>

          {/* Instalación */}
          <div style={ST}>Instalar Guardian Shield en tu dispositivo</div>
          <div style={CARD}>
            <div style={{ display:"grid", gridTemplateColumns:"1fr 1fr", gap:12, marginBottom:12 }}>
              {[
                {ic:"📱",t:"iPhone / iPad",steps:["1. Abre este archivo en Safari","2. Toca Compartir  (cuadrado con flecha ↑)","3. Desplázate y toca 'Añadir a pantalla de inicio'","4. Nombre: Guardian Shield → Toca Añadir"]},
                {ic:"🤖",t:"Android",steps:["1. Abre en Google Chrome","2. Toca el menú ⋮ → 'Instalar app'","3. Si no aparece: Añadir a pantalla de inicio","4. Toca Instalar y confirma"]},
              ].map(d => (
                <div key={d.t} style={{ background:"rgba(255,255,255,.04)", border:"1px solid rgba(255,255,255,.07)", borderRadius:12, padding:14 }}>
                  <div style={{ fontSize:26, marginBottom:8 }}>{d.ic}</div>
                  <div style={{ fontSize:13, fontWeight:800, letterSpacing:"-.01em", marginBottom:9 }}>{d.t}</div>
                  {d.steps.map((s, i) => <div key={i} style={{ fontSize:11.5, color:C.mid, lineHeight:1.75 }}>{s}</div>)}
                </div>
              ))}
            </div>
            <div style={{ padding:"10px 13px", background:"rgba(34,197,94,.05)", border:"1px solid rgba(34,197,94,.2)", borderRadius:9, fontSize:12, color:C.mid }}>
              ✅ <strong style={{ color:C.green }}>Aplicación PWA</strong> · Funciona sin conexión a internet · Gratuita · Sin instalación desde tienda de apps
            </div>
          </div>

          <div style={{ textAlign:"center", marginTop:14, paddingTop:14, borderTop:"1px solid rgba(255,255,255,.06)" }}>
            <span style={{ display:"inline-flex", alignItems:"center", gap:7, padding:"9px 18px", borderRadius:20, background:"rgba(37,99,235,.07)", border:"1px solid rgba(37,99,235,.15)", fontSize:11, fontWeight:600, color:C.mid }}>
              🛡 <strong style={{ color:C.text }}>Ignacio Vera</strong> · Guardian Shield v10.0 · 100% local · Sin publicidad · Sin envío de datos
            </span>
          </div>
        </div>}

        {/* ══════════════════════ ANTIVIRUS ══════════════════════ */}
        {tab === "av" && <div className="tc">
          <h2 style={{ fontSize:20, fontWeight:800, letterSpacing:"-.03em", marginBottom:4 }}>Análisis de Seguridad</h2>
          <p style={{ fontSize:13, color:C.mid, lineHeight:1.55, marginBottom:16 }}>Escáner completo del dispositivo: sistema operativo, red, privacidad, filtraciones y protección antiphishing.</p>

          <button onClick={runFullAV} disabled={busy} style={{ ...BTN, background: busy ? "rgba(37,99,235,.1)" : "linear-gradient(135deg,#2563eb,#1d4ed8)", color: busy ? C.mid : "#fff", border:"1px solid rgba(37,99,235,.4)", boxShadow: busy ? "none" : "0 4px 20px rgba(37,99,235,.28)", opacity: busy ? .65 : 1, marginBottom:14 }}>
            {busy ? <><Spin color="rgba(255,255,255,.7)" /> Escaneando dispositivo…</> : "🔬 Escaneo Completo de Seguridad"}
          </button>

          {avDone && avScore !== null && (
            <div style={{ ...CARD, background: avScore > 80 ? "rgba(34,197,94,.04)" : avScore > 50 ? "rgba(245,158,11,.04)" : "rgba(239,68,68,.05)", borderColor: avScore > 80 ? "rgba(34,197,94,.22)" : avScore > 50 ? "rgba(245,158,11,.22)" : "rgba(239,68,68,.28)", marginBottom:14 }}>
              <div style={{ display:"flex", alignItems:"center", gap:14, flexWrap:"wrap" }}>
                <div style={{ width:82, height:82, borderRadius:"50%", background:`${scCol}12`, border:`3px solid ${scCol}`, display:"flex", alignItems:"center", justifyContent:"center", flexShrink:0 }}>
                  <div style={{ textAlign:"center" }}><div style={{ fontSize:24, fontWeight:900, color:scCol, letterSpacing:"-.02em", lineHeight:1 }}>{avScore}</div><div style={{ fontSize:8, fontWeight:700, color:C.dim, textTransform:"uppercase", letterSpacing:".09em", marginTop:2 }}>SCORE</div></div>
                </div>
                <div>
                  <div style={{ fontSize:16, fontWeight:800, letterSpacing:"-.01em", color: avScore > 80 ? C.green : avScore > 50 ? C.amber : C.red, marginBottom:5 }}>{avScore > 80 ? "Dispositivo bien protegido" : avScore > 50 ? "Mejoras recomendadas" : "Se requieren acciones urgentes"}</div>
                  <div style={{ fontSize:12, color:C.mid, lineHeight:1.6 }}>
                    {Object.values(avRes).filter(r => r.st === "ok").length} módulos OK · {Object.values(avRes).filter(r => r.st === "warn").length} revisiones recomendadas · {Object.values(avRes).filter(r => r.st === "danger").length} problemas detectados
                  </div>
                </div>
              </div>
            </div>
          )}

          <div style={ST}>Módulos — toca uno para analizar individualmente</div>
          <div style={{ display:"grid", gridTemplateColumns:"1fr 1fr", gap:10, marginBottom:18 }}>
            {AV_CHECKS.map(c => <ModCard key={c.id} check={c} res={avRes[c.id]} running={!!avRun[c.id]} onRun={() => runOneAV(c.id)} />)}
          </div>

          <div style={ST}>Detector de SMS Phishing (Smishing)</div>
          <div style={CARD}>
            <p style={{ fontSize:12.5, color:C.mid, lineHeight:1.55, marginBottom:12 }}>Pega el texto de un SMS sospechoso para detectar patrones de phishing, smishing y fraude.</p>
            <textarea value={smsInp} onChange={e => setSmsInp(e.target.value)} rows={3} placeholder="Pega aquí el SMS sospechoso…" style={{ ...INP, display:"block", marginBottom:10 }} />
            <button onClick={() => { const r = analyze(smsInp.toLowerCase(), SMS_PAT, 40); setSmsRes(r); showToast(r.level === "danger" ? "🚨 SMS sospechoso detectado." : r.level === "warn" ? "⚠️ Indicadores leves detectados." : "✅ Sin indicadores.", r.level); }} style={{ ...BTN, background:"linear-gradient(135deg,#2563eb,#1d4ed8)", color:"#fff", border:"none", fontSize:12, padding:"12px 16px" }}>🔍 Analizar SMS</button>
            <ResultBox res={smsRes} />
          </div>
        </div>}

        {/* ══════════════════════ FIREWALL ══════════════════════ */}
        {tab === "firewall" && <div className="tc">
          <h2 style={{ fontSize:20, fontWeight:800, marginBottom:4 }}>Firewall y Análisis de Red</h2>
          <p style={{ fontSize:13, color:C.mid, lineHeight:1.55, marginBottom:16 }}>Análisis de puertos de red, servicios activos y niveles de riesgo asociados a cada uno.</p>

          <div style={{ ...CARD, background:"rgba(34,197,94,.04)", borderColor:"rgba(34,197,94,.2)", display:"flex", alignItems:"flex-start", gap:14, marginBottom:14 }}>
            <span style={{ fontSize:30, flexShrink:0 }}>🔥</span>
            <div>
              <div style={{ fontSize:14, fontWeight:800, letterSpacing:"-.01em", marginBottom:4 }}>Firewall del dispositivo activo</div>
              <div style={{ fontSize:12, color:C.mid, lineHeight:1.6 }}>iOS y Android gestionan el firewall del sistema automáticamente. Cada app opera en un sandbox aislado y solo puede comunicarse por los puertos y protocolos que el sistema operativo autoriza explícitamente.</div>
            </div>
          </div>

          <div style={ST}>Tabla de puertos y riesgos conocidos</div>
          <div style={{ ...CARD, padding:0, overflow:"hidden", marginBottom:14 }}>
            <div style={{ overflowX:"auto" }}>
              <table style={{ width:"100%", borderCollapse:"collapse", fontSize:12 }}>
                <thead><tr style={{ borderBottom:"1px solid rgba(255,255,255,.08)" }}>
                  {["Puerto / Proto","Servicio","Estado","Riesgo"].map(h => <th key={h} style={{ textAlign:"left", padding:"9px 13px", fontSize:9, fontWeight:700, textTransform:"uppercase", letterSpacing:".1em", color:C.dim }}>{h}</th>)}
                </tr></thead>
                <tbody>
                  {PORTS.map(p => {
                    const rc = {BAJO:C.blue,MEDIO:C.amber,ALTO:"#f97316",CRÍTICO:C.red}[p.risk];
                    const sc2 = {abierto:C.amber,cerrado:C.green,filtrado:C.blue}[p.st];
                    return <tr key={p.port} className="hovcell" style={{ borderBottom:"1px solid rgba(255,255,255,.04)" }}>
                      <td style={{ padding:"10px 13px" }}><span style={{ fontFamily:C.mono, fontSize:11, fontWeight:700, color:C.mid }}>{p.port}/{p.proto}</span></td>
                      <td style={{ padding:"10px 13px" }}><div style={{ fontWeight:700, fontSize:12.5, letterSpacing:"-.01em" }}>{p.svc}</div><div style={{ fontSize:10, color:C.dim, marginTop:1.5, lineHeight:1.4 }}>{p.desc}</div></td>
                      <td style={{ padding:"10px 13px" }}><span style={{ display:"inline-flex", alignItems:"center", gap:4, padding:"2px 9px", borderRadius:20, fontSize:9, fontWeight:700, fontFamily:C.mono, color:sc2, background:`${sc2}18`, border:`1px solid ${sc2}38`, whiteSpace:"nowrap" }}>{p.st.toUpperCase()}</span></td>
                      <td style={{ padding:"10px 13px" }}><span style={{ fontSize:10, fontWeight:700, fontFamily:C.mono, color:rc }}>{p.risk}</span></td>
                    </tr>;
                  })}
                </tbody>
              </table>
            </div>
          </div>

          <div style={ST}>Buenas prácticas de seguridad de red</div>
          <div style={CARD}>
            {[
              {ic:"✅",t:"Usa siempre HTTPS",d:"Nunca introduzcas contraseñas ni datos bancarios en sitios HTTP. El tráfico puede ser interceptado en la misma red Wi-Fi."},
              {ic:"📶",t:"Desactiva Wi-Fi y Bluetooth cuando no los uses",d:"Reducen la superficie de ataque. Actívalos solo cuando los necesites para evitar conexiones no deseadas."},
              {ic:"🌐",t:"Configura DNS cifrado (DoH / DoT)",d:"Cifra tus consultas DNS para evitar que terceros monitoricen los sitios que visitas. Disponible en Ajustes → Red → DNS privado (Android) o app de Cloudflare (iOS)."},
              {ic:"🔐",t:"Activa VPN en redes Wi-Fi públicas",d:"En aeropuertos, hoteles o cafeterías, activa siempre una VPN para cifrar todo tu tráfico de red y protegerte de ataques man-in-the-middle."},
              {ic:"📱",t:"Desactiva ADB en Android cuando no lo uses",d:"Ajustes → Opciones de desarrollador → Depuración USB → OFF. Cuando ADB está activo permite acceso completo al dispositivo."},
              {ic:"🛡",t:"Controla el acceso a internet por app",d:"Android permite bloquear el acceso a internet de apps específicas desde Ajustes → Red → Tráfico de datos por app."},
              {ic:"🔄",t:"Mantén actualizado el firmware del router",d:"Los routers con firmware desactualizado son una vía de entrada frecuente. Revisa las actualizaciones en la web de tu operador."},
              {ic:"🚫",t:"Cierra puertos peligrosos en el router doméstico",d:"Accede al panel de tu router (generalmente 192.168.1.1) y asegúrate de que los puertos 3389 (RDP), 23 (Telnet) y 445 (SMB) están cerrados al exterior."},
            ].map((item, i) => (
              <div key={i} style={{ display:"flex", gap:11, alignItems:"flex-start", padding:"10px 0", borderBottom: i < 7 ? "1px solid rgba(255,255,255,.04)" : "none" }}>
                <span style={{ fontSize:17, flexShrink:0, marginTop:1 }}>{item.ic}</span>
                <div><div style={{ fontSize:13, fontWeight:700, letterSpacing:"-.01em", marginBottom:2 }}>{item.t}</div><div style={{ fontSize:11.5, color:C.mid, lineHeight:1.55 }}>{item.d}</div></div>
              </div>
            ))}
          </div>
        </div>}

        {/* ══════════════════════ FILTRACIONES ══════════════════════ */}
        {tab === "breach" && <div className="tc">
          <h2 style={{ fontSize:20, fontWeight:800, marginBottom:4 }}>Monitor de Filtraciones</h2>
          <p style={{ fontSize:13, color:C.mid, lineHeight:1.55, marginBottom:16 }}>Comprueba en <strong style={{ color:C.text }}>{PLATFORMS.length} plataformas</strong> si tus datos aparecen en brechas de seguridad públicamente documentadas.</p>

          <div style={CARD}>
            <div style={{ display:"grid", gridTemplateColumns:"1fr 1fr", gap:10, marginBottom:13 }}>
              {[{l:"CORREO ELECTRÓNICO",v:email,sv:setEmail,ph:"correo@dominio.com",t:"email"},{l:"NOMBRE DE USUARIO",v:user,sv:setUser,ph:"nombre_usuario",t:"text"}].map(f => (
                <div key={f.l}>
                  <div style={{ fontSize:9, fontWeight:700, color:C.dim, textTransform:"uppercase", letterSpacing:".12em", marginBottom:6 }}>{f.l}</div>
                  <input type={f.t} value={f.v} onChange={e => f.sv(e.target.value)} onKeyDown={e => e.key === "Enter" && startScan()} placeholder={f.ph} style={INP} onFocus={e => e.target.style.borderColor="rgba(37,99,235,.45)"} onBlur={e => e.target.style.borderColor="rgba(255,255,255,.08)"} />
                </div>
              ))}
            </div>
            <button onClick={startScan} disabled={bRunning} style={{ ...BTN, background: bRunning ? "rgba(37,99,235,.1)" : "linear-gradient(135deg,#2563eb,#1d4ed8)", color: bRunning ? C.mid : "#fff", border:"1px solid rgba(37,99,235,.4)", fontSize:12, opacity: bRunning ? .65 : 1 }}>
              {bRunning ? <><Spin color="rgba(255,255,255,.7)" /> Analizando {PLATFORMS.length} plataformas…</> : `🔍 Analizar ${PLATFORMS.length} plataformas`}
            </button>
          </div>

          {!bRes && !bRunning && (
            <div style={{ textAlign:"center", padding:"28px 12px" }}>
              <div style={{ fontSize:36, marginBottom:12 }}>🔓</div>
              <div style={{ fontSize:10, color:C.dim, lineHeight:2.3, letterSpacing:".03em" }}>
                {["🎮 PlayStation · Xbox · Steam · Epic Games · Nintendo · Riot Games · Battle.net · Twitch · Roblox",
                  "👥 Google · Facebook / Meta · Instagram · TikTok · LinkedIn · Discord · Reddit · Snapchat",
                  "💬 Gmail · Yahoo Mail · Outlook · ProtonMail · Telegram · WhatsApp · Signal",
                  "🎬 Netflix · Spotify · Amazon Prime · Disney+ · Max / HBO",
                  "💳 PayPal · Revolut · Wise · Binance · Coinbase · Stripe",
                  "💼 Slack · Notion · GitHub · GitLab · Figma · Zoom · Dropbox",
                  "🛒 eBay · Wallapop · Vinted · Booking.com · Airbnb · ChatGPT · Adobe CC · Canva · Patreon",
                ].map((l, i) => <div key={i}>{l}</div>)}
              </div>
            </div>
          )}

          {bRes && (() => {
            const bsc = brScore > 75 ? C.green : brScore > 45 ? C.amber : C.red;
            const filtered = getFiltered();
            return <>
              <div style={CARD}>
                <div style={{ display:"flex", alignItems:"center", gap:16, flexWrap:"wrap" }}>
                  <div style={{ width:88, height:88, borderRadius:"50%", background:`${bsc}10`, border:`3px solid ${bsc}`, display:"flex", alignItems:"center", justifyContent:"center", flexShrink:0 }}>
                    <div style={{ textAlign:"center" }}><div style={{ fontSize:24, fontWeight:900, color:bsc, letterSpacing:"-.02em", lineHeight:1 }}>{brScore}</div><div style={{ fontSize:8, fontWeight:700, color:C.dim, textTransform:"uppercase", letterSpacing:".08em", marginTop:2 }}>SCORE</div></div>
                  </div>
                  <div style={{ flex:1, minWidth:160 }}>
                    <div style={{ fontSize:17, fontWeight:800, letterSpacing:"-.01em", color: exposed.length > 0 ? C.text : C.green, marginBottom:5 }}>{exposed.length > 0 ? `${exposed.length} plataforma${exposed.length === 1 ? "" : "s"} con brechas` : "Sin brechas conocidas"}</div>
                    <p style={{ fontSize:12, color:C.mid, marginBottom:12, lineHeight:1.6 }}>{exposed.length > 0 ? "Toca cada plataforma para ver los pasos de acción inmediata." : "No se encontraron coincidencias en la base de datos de brechas documentadas."}</p>
                    <div style={{ display:"flex", gap:8 }}>
                      {[{n:exposed.length,l:"Con brecha",c:exposed.length?C.red:C.green},{n:safe_p.length,l:"Sin brecha",c:C.green},{n:all.length,l:"Analizadas",c:C.blue}].map(k => (
                        <div key={k.l} style={{ flex:1, textAlign:"center", background:"rgba(255,255,255,.04)", border:"1px solid rgba(255,255,255,.07)", borderRadius:10, padding:"9px 6px" }}>
                          <div style={{ fontSize:22, fontWeight:900, color:k.c, letterSpacing:"-.02em", lineHeight:1 }}>{k.n}</div>
                          <div style={{ fontSize:8, fontWeight:700, color:C.dim, marginTop:3, textTransform:"uppercase", letterSpacing:".09em" }}>{k.l}</div>
                        </div>
                      ))}
                    </div>
                  </div>
                </div>
              </div>

              {email && <div style={{ background:"rgba(37,99,235,.07)", border:"1px solid rgba(37,99,235,.18)", borderRadius:10, padding:"11px 13px", marginBottom:12 }}>
                <div style={{ fontSize:11, fontWeight:600, color:C.mid, marginBottom:7 }}>Verificación en tiempo real para <strong style={{ color:C.text }}>{email}</strong></div>
                <div style={{ display:"flex", flexWrap:"wrap", gap:8 }}>
                  {[{l:"Have I Been Pwned →",u:`https://haveibeenpwned.com/account/${encodeURIComponent(email)}`},{l:"Firefox Monitor →",u:"https://monitor.mozilla.org/"},{l:"DeHashed →",u:"https://www.dehashed.com/"},{l:"Google Dark Web →",u:"https://myaccount.google.com/"}].map(lk => (
                    <a key={lk.l} href={lk.u} target="_blank" rel="noreferrer" className="hovlink" style={{ fontSize:10.5, fontWeight:700, color:C.blue, borderBottom:"1px solid rgba(37,99,235,.3)", paddingBottom:1 }}>{lk.l}</a>
                  ))}
                </div>
              </div>}

              {/* Filtros */}
              <div style={{ overflowX:"auto", marginBottom:11, scrollbarWidth:"none" }}>
                <div style={{ display:"flex", gap:5, minWidth:"max-content", paddingBottom:2 }}>
                  <div style={{ display:"flex", gap:2, background:"rgba(255,255,255,.04)", borderRadius:8, padding:3, border:"1px solid rgba(255,255,255,.07)" }}>
                    {[{k:"all",l:`Todas (${all.length})`},{k:"exposed",l:`⚑ Brecha (${exposed.length})`},{k:"safe",l:`✓ OK (${safe_p.length})`}].map(f => (
                      <button key={f.k} onClick={() => { setBFilt(f.k); setOpenR({}); }} style={{ padding:"6px 11px", borderRadius:6, fontSize:11, fontWeight:600, border:"none", cursor:"pointer", background: bFilt===f.k ? "rgba(37,99,235,.2)" : "transparent", color: bFilt===f.k ? C.blue : C.dim, transition:"all .14s" }}>{f.l}</button>
                    ))}
                  </div>
                  {[{k:"all",l:"◈ Todos"}, ...Object.entries(CATS).map(([k,v]) => ({k, l:`${v.i} ${v.l}`}))].map(f => (
                    <button key={f.k} onClick={() => { setCatF(f.k); setOpenR({}); }} style={{ padding:"5px 10px", borderRadius:6, fontSize:10, fontWeight:600, border:`1px solid ${catF===f.k ? "rgba(139,92,246,.4)" : "rgba(255,255,255,.07)"}`, cursor:"pointer", background: catF===f.k ? "rgba(139,92,246,.18)" : "rgba(255,255,255,.04)", color: catF===f.k ? "#c4b5fd" : C.dim, whiteSpace:"nowrap", transition:"all .14s" }}>{f.l}</button>
                  ))}
                </div>
              </div>

              {/* Tabla */}
              <div style={{ background:"rgba(255,255,255,.02)", border:"1px solid rgba(255,255,255,.07)", borderRadius:14, overflow:"hidden" }}>
                <div style={{ display:"grid", gridTemplateColumns:"3px 38px 1fr auto 14px", gap:9, padding:"9px 14px", background:"rgba(255,255,255,.04)", borderBottom:"1px solid rgba(255,255,255,.07)" }}>
                  {["","","PLATAFORMA","ESTADO",""].map((h,i) => <span key={i} style={{ fontSize:8.5, fontWeight:700, textTransform:"uppercase", letterSpacing:".14em", color:C.dim }}>{h}</span>)}
                </div>

                {(bFilt==="all"||bFilt==="exposed") && catF==="all" && exposed.length > 0 && <>
                  <div style={{ padding:"7px 14px", background:"rgba(239,68,68,.05)", borderBottom:"1px solid rgba(255,255,255,.04)" }}>
                    <div style={{ fontSize:9, fontWeight:700, textTransform:"uppercase", letterSpacing:".12em", color:C.red, display:"flex", alignItems:"center", gap:6 }}>
                      <span style={{ width:5, height:5, borderRadius:"50%", background:C.red, flexShrink:0 }} />ATENCIÓN REQUERIDA · {exposed.length} PLATAFORMAS CON BRECHAS
                    </div>
                  </div>
                  {exposed.map(r => <PRow key={r.p.id} r={r} loading={!!bLoad[r.p.id]} open={!!openR[r.p.id]} onToggle={() => setOpenR(p => ({ ...p, [r.p.id]:!p[r.p.id] }))} />)}
                </>}

                {catF === "all"
                  ? Object.entries(CATS).map(([cat, meta]) => {
                      const items = filtered.filter(r => r.p.cat === cat && !r.breach);
                      if (!items.length) return null;
                      return <div key={cat}>
                        <div style={{ padding:"7px 14px", background:"rgba(255,255,255,.02)", borderBottom:"1px solid rgba(255,255,255,.04)", borderTop:"1px solid rgba(255,255,255,.04)" }}>
                          <div style={{ fontSize:9, fontWeight:700, textTransform:"uppercase", letterSpacing:".12em", color:C.dim }}>{meta.i} {meta.l}</div>
                        </div>
                        {items.map(r => <PRow key={r.p.id} r={r} loading={!!bLoad[r.p.id]} open={!!openR[r.p.id]} onToggle={() => setOpenR(p => ({ ...p, [r.p.id]:!p[r.p.id] }))} />)}
                      </div>;
                    })
                  : filtered.map(r => <PRow key={r.p.id} r={r} loading={!!bLoad[r.p.id]} open={!!openR[r.p.id]} onToggle={() => setOpenR(p => ({ ...p, [r.p.id]:!p[r.p.id] }))} />)
                }
              </div>
            </>;
          })()}
        </div>}

        {/* ══════════════════════ WEB & URLs ══════════════════════ */}
        {tab === "web" && <div className="tc">
          <h2 style={{ fontSize:20, fontWeight:800, marginBottom:4 }}>Protección Web</h2>
          <p style={{ fontSize:13, color:C.mid, lineHeight:1.55, marginBottom:16 }}>Verificador de URLs, detector de phishing por email y SMS, y recursos de análisis de seguridad web.</p>

          {[
            { title:"Verificador de URLs y dominios", sub:"Analiza cualquier URL o dominio antes de abrirlo para detectar phishing, suplantación de identidad y conexiones inseguras.", content: <>
              <div style={{ display:"flex", gap:8, marginBottom:8 }}>
                <input value={urlInp} onChange={e => setUrlInp(e.target.value)} onKeyDown={e => e.key==="Enter" && checkURL()} type="url" placeholder="https://ejemplo.com o dominio.com" style={{ ...INP, flex:1 }} onFocus={e=>e.target.style.borderColor="rgba(37,99,235,.45)"} onBlur={e=>e.target.style.borderColor="rgba(255,255,255,.08)"} />
                <button onClick={checkURL} style={{ padding:"11px 16px", borderRadius:9, fontSize:12, fontWeight:700, color:C.blue, border:"1px solid rgba(37,99,235,.3)", background:"rgba(37,99,235,.1)", cursor:"pointer", whiteSpace:"nowrap" }}>Verificar</button>
              </div>
              {urlRes && <div style={{ padding:14, borderRadius:11, ...(urlRes.iss.length ? { background:"rgba(239,68,68,.06)", border:"1px solid rgba(239,68,68,.28)" } : { background:"rgba(34,197,94,.05)", border:"1px solid rgba(34,197,94,.24)" }) }}>
                <div style={{ fontWeight:800, fontSize:14, marginBottom: urlRes.iss.length ? 8 : 6, color: urlRes.iss.length ? C.red : C.green }}>{urlRes.iss.length ? "🚨 Riesgo detectado" : "✅ Sin riesgos en la base de datos"}</div>
                {urlRes.iss.map((iss, i) => <div key={i} style={{ display:"flex", gap:7, marginBottom:5 }}><span style={{ color:C.red, flexShrink:0 }}>⚠</span><span style={{ fontSize:12.5, color:C.mid }}>{iss}</span></div>)}
                <div style={{ marginTop:8, fontSize:12, color:C.dim, lineHeight:1.55 }}>{urlRes.iss.length ? "No abras este enlace. Para verificación adicional con múltiples motores, usa los recursos externos de esta sección." : (urlRes.https ? "Conexión HTTPS ✓. " : "Nota: sin HTTPS — no introduzcas datos personales. ") + "Para mayor certeza, verifica también en Google Safe Browsing o VirusTotal."}</div>
              </div>}
            </> },
            { title:"Detector de phishing en emails", sub:"Pega el texto completo de un email sospechoso para analizar patrones de phishing, urgencia falsa y solicitudes de datos.", content: <>
              <textarea value={emlInp} onChange={e => setEmlInp(e.target.value)} rows={3} placeholder="Pega aquí el texto del email sospechoso…" style={{ ...INP, display:"block", marginBottom:10 }} />
              <button onClick={() => { const r = analyze(emlInp.toLowerCase(), EMAIL_PAT, 35); setEmlRes(r); showToast(r.level==="danger" ? "🚨 Email con indicadores de phishing." : r.level==="warn" ? "⚠️ Indicadores leves." : "✅ Sin indicadores.", r.level); }} style={{ ...BTN, background:"linear-gradient(135deg,#2563eb,#1d4ed8)", color:"#fff", border:"none", fontSize:12, padding:"12px 16px" }}>🔍 Analizar email</button>
              <ResultBox res={emlRes} />
            </> },
            { title:"Detector de SMS Phishing (Smishing)", sub:"Pega el texto de un SMS sospechoso para identificar señales de smishing, estafas de entrega y fraudes gubernamentales.", content: <>
              <textarea value={smsInp} onChange={e => setSmsInp(e.target.value)} rows={3} placeholder="Pega aquí el SMS sospechoso…" style={{ ...INP, display:"block", marginBottom:10 }} />
              <button onClick={() => { const r = analyze(smsInp.toLowerCase(), SMS_PAT, 40); setSmsRes(r); showToast(r.level==="danger" ? "🚨 SMS sospechoso detectado." : r.level==="warn" ? "⚠️ Indicadores leves." : "✅ Sin indicadores.", r.level); }} style={{ ...BTN, background:"linear-gradient(135deg,#2563eb,#1d4ed8)", color:"#fff", border:"none", fontSize:12, padding:"12px 16px" }}>🔍 Analizar SMS</button>
              <ResultBox res={smsRes} />
            </> },
          ].map(sec => (
            <div key={sec.title}>
              <div style={ST}>{sec.title}</div>
              <div style={CARD}><p style={{ fontSize:12.5, color:C.mid, marginBottom:12, lineHeight:1.55 }}>{sec.sub}</p>{sec.content}</div>
            </div>
          ))}

          <div style={ST}>Recursos externos de verificación</div>
          <div style={{ ...CARD, padding:0, overflow:"hidden" }}>
            {[
              {n:"Google Safe Browsing",d:"Comprueba si una URL está categorizada como maliciosa, phishing o malware en tiempo real",u:"https://transparencyreport.google.com/safe-browsing/search",ic:"🔵"},
              {n:"VirusTotal",d:"Escanea URLs, archivos y dominios con más de 70 motores de análisis de seguridad simultáneamente",u:"https://www.virustotal.com",ic:"🔴"},
              {n:"PhishTank",d:"Base de datos colaborativa de URLs de phishing verificadas por la comunidad de seguridad",u:"https://www.phishtank.com",ic:"🟠"},
              {n:"URLVoid",d:"Reputación de dominio y análisis de amenazas con múltiples fuentes de inteligencia de amenazas",u:"https://www.urlvoid.com",ic:"🟢"},
              {n:"Cisco Talos Intelligence",d:"Reputación de IP y dominio, análisis de amenazas y threat intelligence de nivel profesional",u:"https://talosintelligence.com",ic:"🔷"},
            ].map((item, i) => (
              <a key={i} href={item.u} target="_blank" rel="noreferrer" className="hovcell hovlink" style={{ display:"flex", alignItems:"center", gap:12, padding:"12px 14px", borderBottom: i<4 ? "1px solid rgba(255,255,255,.04)" : "none", textDecoration:"none", transition:"background .12s", background:"transparent" }}>
                <span style={{ fontSize:19, flexShrink:0 }}>{item.ic}</span>
                <div style={{ flex:1 }}><div style={{ fontSize:13, fontWeight:700, letterSpacing:"-.01em" }}>{item.n}</div><div style={{ fontSize:11.5, color:C.mid, marginTop:1 }}>{item.d}</div></div>
                <span style={{ color:C.dim, fontSize:13 }}>→</span>
              </a>
            ))}
          </div>
        </div>}

        {/* ══════════════════════ PRIVACIDAD ══════════════════════ */}
        {tab === "privacy" && <div className="tc">
          <h2 style={{ fontSize:20, fontWeight:800, marginBottom:4 }}>Centro de Privacidad</h2>
          <p style={{ fontSize:13, color:C.mid, lineHeight:1.55, marginBottom:16 }}>Guías de privacidad específicas para iOS y Android. Pasos concretos para cada ajuste.</p>

          {[
            { title:"Guía completa iOS — Privacidad y permisos", items:[
              {ic:"📷",t:"Cámara y Micrófono",d:"Ajustes → Privacidad y seguridad → Cámara / Micrófono. Revoca el acceso a apps que no lo necesiten. Nadie debería acceder a tu cámara en segundo plano."},
              {ic:"📍",t:"Localización",d:"Ajustes → Privacidad → Servicios de localización. Configura 'Al usar la app' para cada una. Deniega la localización precisa a apps que no la requieren activamente."},
              {ic:"📋",t:"Acceso al portapapeles",d:"iOS 16+ te notifica cuando una app accede a tu portapapeles. Revisa el Panel de privacidad periódicamente para detectar accesos no autorizados."},
              {ic:"👁",t:"Panel de privacidad de apps",d:"Ajustes → Privacidad y seguridad → Informe de privacidad de apps. Muestra con detalle qué apps accedieron a sensores del dispositivo y cuándo."},
              {ic:"🔐",t:"Protección Avanzada de Datos",d:"Apple ID → iCloud → Protección Avanzada de Datos. Actívala para cifrar E2E todos tus datos en iCloud, incluyendo fotos, notas y copias de seguridad."},
              {ic:"📧",t:"Ocultar mi email (iCloud+)",d:"Apple ID → iCloud → Ocultar mi email. Genera alias de email desechables para registros en servicios externos sin exponer tu dirección real."},
              {ic:"🌐",t:"Privacidad en Safari",d:"Ajustes → Safari → Privacidad: activa 'Evitar seguimiento cruzado', 'Bloquear todas las cookies de terceros' y 'Ocultar dirección IP de rastreadores'."},
              {ic:"🍎",t:"App Store — Revisar antes de instalar",d:"Consulta siempre la sección 'Privacidad de la app' antes de descargar. Cada app debe declarar exactamente qué datos recopila y con qué propósito."},
              {ic:"🔒",t:"Face ID / Touch ID — Seguridad adicional",d:"Ajustes → Face ID y código → Activa el borrado del iPhone tras 10 intentos fallidos. Limita qué apps pueden usar Face ID."},
              {ic:"📱",t:"Modo de restricción USB",d:"Ajustes → Face ID y código → Acceso USB: activa 'Desactivar si está bloqueado'. Previene el acceso físico a datos cuando el dispositivo está bloqueado."},
            ]},
            { title:"Guía completa Android — Privacidad y permisos", items:[
              {ic:"🎛️",t:"Gestor de permisos",d:"Ajustes → Privacidad → Gestor de permisos. Revoca Cámara, Micrófono y Localización para apps que no los necesiten. Aplica el principio de mínimo privilegio."},
              {ic:"👁",t:"Panel de privacidad (Android 12+)",d:"Ajustes → Privacidad → Panel de privacidad. Visualiza qué apps accedieron a Cámara, Micrófono o Localización en las últimas 24 horas."},
              {ic:"🛡",t:"Administradores del dispositivo",d:"Ajustes → Seguridad → Administradores del dispositivo. Solo debe aparecer 'Encontrar mi dispositivo'. Revoca cualquier otra entrada que no reconozcas."},
              {ic:"🐛",t:"Depuración USB — mantener desactivada",d:"Ajustes → Opciones de desarrollador → Depuración USB → OFF. Cuando está activa, cualquier ordenador conectado puede tener acceso completo al dispositivo."},
              {ic:"📱",t:"Instalación de fuentes desconocidas",d:"Desactiva completamente la instalación de apps de fuentes desconocidas. Instala únicamente desde Google Play Store, que analiza las apps antes de publicarlas."},
              {ic:"🌐",t:"DNS privado cifrado",d:"Ajustes → Red e internet → DNS privado. Introduce 'dns.cloudflare.com' o '1dot1dot1dot1.cloudflare-dns.com' para activar DNS cifrado a nivel de sistema completo."},
              {ic:"🔒",t:"Cifrado del almacenamiento",d:"Ajustes → Seguridad → Cifrado del teléfono. Activa el cifrado completo del almacenamiento interno. En Android moderno suele estar activo por defecto."},
              {ic:"📡",t:"Bluetooth y NFC — desactivar cuando no se usen",d:"Desactiva Bluetooth y NFC en el panel de notificaciones cuando no los uses activamente. Reducen la superficie de ataque del dispositivo."},
              {ic:"🔔",t:"Permisos de notificaciones",d:"Ajustes → Notificaciones → Revoca el permiso de notificaciones a apps que no necesitan mostrarte alertas. Reduce el riesgo de phishing a través de notificaciones falsas."},
              {ic:"👤",t:"Perfiles de trabajo separados",d:"Si usas el dispositivo para trabajo, considera usar un perfil de trabajo separado en Android. Aísla completamente las apps y datos corporativos de los personales."},
            ]},
          ].map(section => (
            <div key={section.title}>
              <div style={ST}>{section.title}</div>
              <div style={{ ...CARD, padding:0, overflow:"hidden", marginBottom:16 }}>
                {section.items.map((item, i) => (
                  <div key={i} style={{ display:"flex", gap:12, alignItems:"flex-start", padding:"12px 14px", borderBottom: i < section.items.length-1 ? "1px solid rgba(255,255,255,.04)" : "none" }}>
                    <span style={{ fontSize:18, flexShrink:0, marginTop:1 }}>{item.ic}</span>
                    <div><div style={{ fontSize:13, fontWeight:700, letterSpacing:"-.01em", marginBottom:2.5 }}>{item.t}</div><div style={{ fontSize:11.5, color:C.mid, lineHeight:1.55 }}>{item.d}</div></div>
                  </div>
                ))}
              </div>
            </div>
          ))}
        </div>}

        {/* ══════════════════════ GUÍA ══════════════════════ */}
        {tab === "tips" && <div className="tc">
          <h2 style={{ fontSize:20, fontWeight:800, marginBottom:4 }}>Guía de Seguridad</h2>
          <p style={{ fontSize:13, color:C.mid, lineHeight:1.55, marginBottom:16 }}>Plan de acción priorizado para proteger tu identidad digital. Empieza por arriba.</p>

          {[
            {p:"URGENTE",c:C.red,i:"🔑",t:"Contraseñas comprometidas",steps:["Cambia la contraseña de cualquier plataforma con brecha detectada de forma inmediata, sin esperar.","Usa contraseñas únicas y aleatorias de mínimo 16 caracteres — una completamente diferente por cada sitio y servicio.","Instala un gestor de contraseñas (Bitwarden es gratuito y de código abierto) para generarlas y almacenarlas de forma segura.","Comprueba tus contraseñas actuales en haveibeenpwned.com/Passwords para detectar cuáles están comprometidas.","Activa las alertas automáticas de contraseñas comprometidas en tu gestor de contraseñas."],links:[{l:"Verificar contraseñas",u:"https://haveibeenpwned.com/Passwords"}]},
            {p:"MUY ALTO",c:C.amber,i:"📱",t:"Autenticación en 2 pasos (2FA)",steps:["Activa 2FA en TODAS las cuentas críticas: email principal, banca, criptomonedas y redes sociales.","Usa una app TOTP (Aegis para Android, Raivo para iOS). NUNCA configures SMS como segundo factor de autenticación.","Los SMS son vulnerables a SIM-swap: un atacante puede convencer a tu operador de transferir tu número a otro dispositivo.","Guarda los códigos de recuperación impresos en un lugar físico seguro, no en el propio dispositivo.","Para cuentas muy críticas (cripto, email principal), considera una llave de seguridad física FIDO2."],links:[]},
            {p:"ALTO",c:"#f97316",i:"👁",t:"Monitorización continua",steps:["Regístrate en haveibeenpwned.com para recibir alertas automáticas por email cuando aparezca en nuevas brechas.","Configura Google Alerts con tu nombre completo y email entre comillas para detectar cualquier mención pública.","Activa notificaciones de inicio de sesión en Google, Apple, Facebook, LinkedIn y en tu entidad bancaria.","Revisa mensualmente el historial de accesos en tus 5-10 cuentas más importantes.","Activa el Informe de Dark Web de Google desde tu cuenta personal — es gratuito y analiza en tiempo real."],links:[{l:"HIBP Alertas",u:"https://haveibeenpwned.com"},{l:"Google Alerts",u:"https://www.google.com/alerts"}]},
            {p:"IMPORTANTE",c:C.purple,i:"🕵️",t:"Privacidad y huella digital",steps:["Busca tu nombre completo y email entre comillas en Google para auditar qué información tuya es accesible públicamente.","Revisa y restringe la configuración de privacidad de todos tus perfiles en redes sociales: quién puede ver qué.","Usa alias de email (SimpleLogin, AnonAddy) para registros en servicios secundarios o de menor confianza.","Activa VPN cuando uses redes Wi-Fi públicas en hoteles, aeropuertos, cafeterías o transportes.","Solicita la eliminación de tus datos a brokers de información (Spokeo, Whitepages, BeenVerified, Pipl, etc.)."],links:[]},
            {p:"AVANZADO",c:C.blue,i:"🛡",t:"Configuración avanzada del sistema",steps:["Activa la Protección Avanzada en tu email principal. Tu correo es la llave maestra de toda tu identidad digital.","Activa cifrado de disco completo: BitLocker en Windows, FileVault en Mac, están disponibles de forma nativa.","Configura DNS cifrado (DoH/DoT) en el navegador y el dispositivo: Cloudflare 1.1.1.1 o NextDNS.","En banca y criptomonedas: 2FA con app, alerta por cada transacción y congelar tarjeta cuando no se use.","Revoca el acceso de apps de terceros obsoletas en cada plataforma — hazlo al menos una vez cada trimestre."],links:[]},
            {p:"FIREWALL",c:C.cyan,i:"🔥",t:"Protección de red y firewall",steps:["En Android: controla el tráfico de red por app desde Ajustes → Red → Tráfico de datos por aplicación.","Configura DNS privado en Android: Ajustes → Red e internet → DNS privado → dns.cloudflare.com.","En iOS: instala la app oficial 1.1.1.1 de Cloudflare para DNS cifrado en todo el sistema.","Desactiva Wi-Fi y Bluetooth cuando no los uses activamente para reducir la superficie de ataque.","Actualiza el firmware de tu router doméstico regularmente y cambia las contraseñas por defecto."],links:[]},
            {p:"iOS",c:C.cyan,i:"🍎",t:"Seguridad específica de iPhone / iPad",steps:["Ajustes → Privacidad: revisa Cámara, Micrófono y Localización — concede acceso solo a las apps que realmente lo necesiten.","Apple ID → 2FA obligatorio. Sin 2FA activo, toda tu cuenta Apple puede ser comprometida de forma remota.","Activa 'Ocultar mi email' con iCloud+ para usar alias desechables en cualquier registro en servicios externos.","Safari → Privacidad: activa 'Evitar seguimiento cruzado', bloquear cookies de terceros y ocultar dirección IP.","Face ID → activa borrado tras 10 intentos fallidos y limita el acceso USB cuando el dispositivo esté bloqueado."],links:[]},
            {p:"ANDROID",c:C.green,i:"🤖",t:"Seguridad específica de Android",steps:["Ajustes → Privacidad → Panel de privacidad: revisa qué apps accedieron a Cámara, Micro y Localización recientemente.","Ajustes → Seguridad → Administradores del dispositivo: solo debe aparecer 'Encontrar mi dispositivo' de Google.","Depuración USB: Ajustes → Opciones de desarrollador → Depuración USB → OFF cuando no la uses activamente.","Instala apps SOLO desde Google Play. Desactiva completamente la instalación de fuentes desconocidas en Ajustes → Seguridad.","Ajustes → Red e internet → DNS privado → dns.cloudflare.com para cifrar todas las consultas DNS del sistema."],links:[]},
          ].map(sec => {
            const colorMap = {[C.red]:"239,68,68",[C.amber]:"245,158,11",[C.purple]:"139,92,246",[C.blue]:"37,99,235",[C.cyan]:"14,165,233",[C.green]:"34,197,94","#f97316":"249,115,22"};
            const rgb = colorMap[sec.c] || "37,99,235";
            return <div key={sec.t} style={{ background:C.s1, border:"1px solid rgba(255,255,255,.07)", borderLeft:`3px solid ${sec.c}`, borderRadius:"0 14px 14px 0", padding:16, marginBottom:10 }}>
              <div style={{ display:"inline-flex", alignItems:"center", gap:5, padding:"3px 10px", borderRadius:20, fontSize:9.5, fontWeight:700, letterSpacing:".05em", color:sec.c, background:`rgba(${rgb},.1)`, border:`1px solid rgba(${rgb},.28)`, marginBottom:8 }}>{sec.i} {sec.p}</div>
              <div style={{ fontSize:15, fontWeight:800, letterSpacing:"-.02em", marginBottom:12 }}>{sec.t}</div>
              <div style={{ display:"flex", flexDirection:"column", gap:7, marginBottom: sec.links.length ? 12 : 0 }}>
                {sec.steps.map((s, i) => <div key={i} style={{ display:"flex", gap:9, alignItems:"flex-start" }}>
                  <div style={{ width:19, height:19, borderRadius:"50%", background:`rgba(${rgb},.12)`, border:`1px solid rgba(${rgb},.3)`, color:sec.c, fontSize:9, display:"flex", alignItems:"center", justifyContent:"center", flexShrink:0, marginTop:2, fontWeight:700, fontFamily:C.mono }}>{i+1}</div>
                  <div style={{ fontSize:12, color:C.mid, lineHeight:1.6 }}>{s}</div>
                </div>)}
              </div>
              {sec.links.length > 0 && <>
                <div style={{ height:1, background:"rgba(255,255,255,.07)", margin:"11px 0" }} />
                <div style={{ display:"flex", gap:7, flexWrap:"wrap" }}>
                  {sec.links.map(l => <a key={l.l} href={l.u} target="_blank" rel="noreferrer" style={{ padding:"6px 12px", borderRadius:8, fontSize:10, fontWeight:700, fontFamily:C.mono, color:C.blue, border:"1px solid rgba(37,99,235,.3)", background:"rgba(37,99,235,.1)", letterSpacing:".05em" }}>{l.l} →</a>)}
                </div>
              </>}
            </div>;
          })}
        </div>}

        {/* ══════════════════════ INFO ══════════════════════ */}
        {tab === "about" && <div className="tc">
          <div style={{ textAlign:"center", marginBottom:26 }}>
            <div style={{ width:74, height:74, borderRadius:18, background:"linear-gradient(135deg,#2563eb,#1d4ed8)", display:"flex", alignItems:"center", justifyContent:"center", fontSize:36, margin:"0 auto 14px", boxShadow:"0 8px 28px rgba(37,99,235,.4)" }}>🛡</div>
            <h1 style={{ fontSize:23, fontWeight:900, letterSpacing:"-.03em", marginBottom:4 }}>Guardian Shield</h1>
            <div style={{ fontFamily:C.mono, fontSize:11, color:C.dim, letterSpacing:".06em", marginBottom:4 }}>Seguridad Personal · Versión 10.0 · 2025</div>
            <div style={{ fontSize:13, fontWeight:700, color:C.blue }}>Desarrollado por <strong style={{ color:C.text }}>Ignacio Vera</strong></div>
          </div>

          {[
            {q:"¿Qué es Guardian Shield?",a:`Suite de seguridad personal completa para iPhone y Android. Incluye: escáner antivirus del sistema operativo (${AV_CHECKS.length} módulos), análisis de firewall con ${PORTS.length} puertos documentados, monitor de filtraciones en ${PLATFORMS.length} plataformas, detector de phishing por SMS y email con ${SMS_PAT.length + EMAIL_PAT.length} patrones, verificador de URLs, centro de privacidad con guías para iOS y Android, y guía de seguridad priorizada en 8 niveles.`},
            {q:"¿Mis datos son seguros y privados?",a:"Sí, completamente. Toda la funcionalidad se ejecuta de forma 100% local en tu dispositivo. Ningún dato sale de tu dispositivo: ni el email que introduces, ni el texto de mensajes analizados, ni las URLs verificadas, ni ningún otro dato. Sin servidores externos, sin almacenamiento en la nube, sin telemetría, sin cookies de seguimiento."},
            {q:"¿Por qué los smartphones también pueden estar en riesgo?",a:"iOS y Android tienen arquitecturas seguras frente al malware tradicional gracias al sandboxing. Pero los ataques modernos no atacan el sistema operativo: atacan a las personas. Phishing por email y SMS (smishing), redes Wi-Fi públicas inseguras, versiones del sistema sin actualizar, reutilización de contraseñas y filtraciones de datos en plataformas que usas son amenazas reales y documentadas en 2025."},
            {q:"¿Qué hago si encuentro brechas en mis cuentas?",a:"Actúa inmediatamente: 1) Cambia la contraseña de esa plataforma ahora mismo. 2) Activa 2FA con una app TOTP (nunca SMS). 3) Revisa el historial de accesos y cierra todas las sesiones desconocidas. 4) Si usabas esa contraseña en otros sitios, cámbiala también ahí. 5) Instala un gestor de contraseñas para tener contraseñas únicas y aleatorias en cada servicio."},
            {q:"¿Cómo instalar como app nativa en iPhone?",a:"1. Abre este archivo en Safari (es importante: usa Safari, no Chrome ni otro navegador). 2. Toca el botón Compartir (el cuadrado con flecha hacia arriba en la barra inferior). 3. Desplázate en las opciones y toca 'Añadir a pantalla de inicio'. 4. Asígnale el nombre 'Guardian Shield' y toca Añadir. Aparecerá como app nativa con icono propio y funciona completamente sin conexión a internet."},
            {q:"¿Cómo instalar como app nativa en Android?",a:"1. Abre este archivo en Google Chrome. 2. Toca el menú de tres puntos (⋮) en la esquina superior derecha. 3. Toca 'Instalar app' si aparece la opción, o 'Añadir a pantalla de inicio'. 4. Confirma tocando Instalar. Aparecerá en tu pantalla de inicio como app nativa con icono propio y funciona sin conexión a internet."},
            {q:"¿Con qué frecuencia debo ejecutar el análisis?",a:"Se recomienda: un análisis completo mensualmente, un análisis de filtraciones cada vez que cambias contraseñas importantes o cuando una plataforma que usas anuncia una brecha, y usar el detector de SMS/email siempre que recibas un mensaje sospechoso. Para monitorización continua y automática, regístrate en haveibeenpwned.com para alertas por email."},
          ].map((item, i) => (
            <div key={i} style={{ background:C.s2, border:"1px solid rgba(255,255,255,.07)", borderRadius:12, padding:15, marginBottom:9 }}>
              <div style={{ fontSize:14, fontWeight:700, letterSpacing:"-.01em", color:C.blue, marginBottom:7 }}>{item.q}</div>
              <div style={{ fontSize:12.5, color:C.mid, lineHeight:1.7 }}>{item.a}</div>
            </div>
          ))}

          <div style={{ background:"rgba(37,99,235,.06)", border:"1px solid rgba(37,99,235,.2)", borderRadius:13, padding:16, marginTop:14 }}>
            <div style={{ fontSize:14, fontWeight:700, color:C.blue, marginBottom:12 }}>Plataformas analizadas ({PLATFORMS.length})</div>
            <div style={{ display:"flex", flexWrap:"wrap", gap:5 }}>
              {PLATFORMS.map(p => {
                const hasB = !!BREACHES[p.id];
                return <span key={p.id} style={{ padding:"3px 8px", borderRadius:4, fontSize:9, fontWeight:600, fontFamily:C.mono, color: hasB ? "#fca5a5" : "#475569", background: hasB ? "rgba(239,68,68,.1)" : "rgba(255,255,255,.04)", border:`1px solid ${hasB ? "rgba(239,68,68,.25)" : "rgba(255,255,255,.07)"}` }}>{p.icon} {p.name}</span>;
              })}
            </div>
            <div style={{ fontSize:10, color:C.dim, marginTop:10, fontWeight:500 }}>
              <span style={{ color:"#fca5a5" }}>■</span> Con brecha documentada &nbsp;&nbsp;
              <span style={{ color:"#475569" }}>■</span> Sin brecha en base de datos
            </div>
          </div>

          <div style={{ textAlign:"center", marginTop:24, paddingTop:16, borderTop:"1px solid rgba(255,255,255,.07)" }}>
            <span style={{ display:"inline-flex", alignItems:"center", gap:7, padding:"10px 20px", borderRadius:20, background:"rgba(37,99,235,.07)", border:"1px solid rgba(37,99,235,.15)", fontSize:11, fontWeight:600, color:C.mid }}>
              🛡 <strong style={{ color:C.text }}>Ignacio Vera</strong> · Guardian Shield v10.0 · Sin envío de datos · Sin publicidad · Sin rastreo
            </span>
          </div>
        </div>}

      </div>

      {/* ── TOAST ── */}
      {toast && (
        <div style={{ position:"fixed", bottom:18, left:"50%", transform:"translateX(-50%)", background:"rgba(7,12,24,.97)", padding:"10px 18px", borderRadius:10, fontSize:12, fontWeight:600, zIndex:999, whiteSpace:"nowrap", boxShadow:"0 8px 32px rgba(0,0,0,.6)", animation:"_up .28s ease", border:`1px solid ${toast.type==="ok"?"rgba(34,197,94,.35)":toast.type==="warn"?"rgba(245,158,11,.35)":toast.type==="danger"?"rgba(239,68,68,.35)":"rgba(37,99,235,.3)"}`, color: toast.type==="ok"?C.green:toast.type==="warn"?C.amber:toast.type==="danger"?C.red:"rgba(147,197,253,1)" }}>
          {toast.msg}
        </div>
      )}
    </div>
  );
}


ReactDOM.createRoot(document.getElementById('root')).render(<App />);
  </script>
</body>
</html>
