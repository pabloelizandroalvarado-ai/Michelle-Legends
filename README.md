<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Michelle Legends</title>

<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
    }

    body {
        min-height: 100vh;
        background: linear-gradient(135deg, #111827, #1e3a5f);
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow-x: hidden;
    }

    .game {
        width: 100%;
        max-width: 500px;
        min-height: 100vh;
        padding: 25px 18px;
        position: relative;
    }

    .screen {
        display: none;
        animation: fadeIn .35s ease;
    }

    .screen.active {
        display: block;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(10px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    /* MENÚ */

    .menu {
        text-align: center;
        padding-top: 45px;
    }

    .ball {
        font-size: 75px;
        animation: float 2s infinite ease-in-out;
        margin-bottom: 10px;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-10px); }
    }

    h1 {
        font-size: 42px;
        letter-spacing: 2px;
        text-shadow: 0 0 15px rgba(255,255,255,.3);
    }

    .subtitle {
        margin-top: 10px;
        margin-bottom: 35px;
        color: #dbeafe;
        font-size: 16px;
    }

    .menu-buttons {
        display: flex;
        flex-direction: column;
        gap: 13px;
    }

    button {
        border: none;
        border-radius: 14px;
        padding: 16px;
        font-size: 17px;
        font-weight: bold;
        cursor: pointer;
        color: white;
        background: rgba(255,255,255,.12);
        border: 1px solid rgba(255,255,255,.2);
        transition: .2s;
    }

    button:hover {
        transform: scale(1.03);
        background: rgba(255,255,255,.2);
    }

    .start {
        background: rgba(255,255,255,.22);
    }

    .locked {
        opacity: .5;
        cursor: not-allowed;
    }

    .locked:hover {
        transform: none;
    }

    /* PANTALLAS */

    .top {
        display: flex;
        align-items: center;
        gap: 12px;
        margin-bottom: 25px;
    }

    .back {
        width: 48px;
        padding: 11px;
        font-size: 20px;
    }

    .top h2 {
        font-size: 27px;
    }

    .card {
        background: rgba(255,255,255,.1);
        border: 1px solid rgba(255,255,255,.16);
        border-radius: 18px;
        padding: 18px;
        margin-bottom: 12px;
    }

    /* CLASIFICACIÓN */

    .ranking-card {
        display: flex;
        align-items: center;
        gap: 14px;
        cursor: pointer;
    }

    .position {
        width: 42px;
        font-size: 23px;
        font-weight: bold;
        text-align: center;
    }

    .avatar-small {
        width: 48px;
        height: 48px;
        border-radius: 50%;
        background: linear-gradient(135deg, #64748b, #cbd5e1);
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 22px;
        flex-shrink: 0;
    }

    .player-info {
        flex: 1;
    }

    .player-info h3 {
        font-size: 17px;
    }

    .player-info p {
        color: #cbd5e1;
        font-size: 13px;
        margin-top: 3px;
    }

    .points {
        font-weight: bold;
        font-size: 17px;
    }

    /* PERFIL */

    .profile {
        text-align: center;
    }

    .avatar-large {
        width: 130px;
        height: 130px;
        border-radius: 50%;
        margin: 10px auto 15px;
        background: linear-gradient(135deg, #64748b, #cbd5e1);
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 55px;
        border: 4px solid rgba(255,255,255,.35);
    }

    .profile h2 {
        font-size: 30px;
    }

    .profile .rank {
        margin: 7px 0 20px;
        color: #cbd5e1;
    }

    .stat {
        display: flex;
        justify-content: space-between;
        padding: 12px 0;
        border-bottom: 1px solid rgba(255,255,255,.1);
        text-align: left;
    }

    .stat:last-child {
        border-bottom: none;
    }

    .quote {
        margin-top: 15px;
        font-style: italic;
        color: #e0f2fe;
        line-height: 1.5;
    }

    .achievement {
        margin-top: 15px;
        padding: 13px;
        border-radius: 12px;
        background: rgba(255,255,255,.08);
    }

    .achievement-title {
        font-size: 13px;
        color: #cbd5e1;
        margin-bottom: 5px;
    }

    /* RESPONSIVE */

    @media (max-width: 380px) {
        h1 {
            font-size: 34px;
        }

        .top h2 {
            font-size: 23px;
        }
    }
</style>
</head>

<body>

<div class="game">

    <!-- MENÚ PRINCIPAL -->
    <section id="menu" class="screen active menu">

        <div class="ball">🏐</div>

        <h1>MICHELLE LEGENDS</h1>

        <p class="subtitle">
            “Un desafío creado especialmente para ti.”
        </p>

        <div class="menu-buttons">

            <button class="start" onclick="showScreen('coming')">
                ▶️ COMENZAR
            </button>

            <button onclick="showScreen('coming')">
                📜 REGLAS
            </button>

            <button onclick="showScreen('coming')">
                📊 ESTADÍSTICAS
            </button>

            <button onclick="showScreen('ranking')">
                🏆 CLASIFICACIÓN
            </button>

            <button onclick="showScreen('coming')">
                👥 CRÉDITOS
            </button>

            <button class="locked" disabled>
                🔒 ???
            </button>

        </div>

    </section>


    <!-- CLASIFICACIÓN -->
    <section id="ranking" class="screen">

        <div class="top">
            <button class="back" onclick="showScreen('menu')">←</button>
            <h2>🏆 Clasificación</h2>
        </div>

        <div id="rankingList"></div>

    </section>


    <!-- PERFIL -->
    <section id="profile" class="screen">

        <div class="top">
            <button class="back" onclick="showScreen('ranking')">←</button>
            <h2>Perfil</h2>
        </div>

        <div id="profileContent"></div>

    </section>


    <!-- PANTALLAS TEMPORALES -->
    <section id="coming" class="screen">

        <div class="top">
            <button class="back" onclick="showScreen('menu')">←</button>
            <h2>🚧 Próximamente</h2>
        </div>

        <div class="card" style="text-align:center;">
            <div style="font-size:60px;">🏐</div>

            <h2 style="margin:15px 0;">
                Esta sección todavía está en desarrollo.
            </h2>

            <p style="color:#cbd5e1; line-height:1.5;">
                Poco a poco iremos desbloqueando todo
                Michelle Legends.
            </p>
        </div>

    </section>

</div>


<script>

const players = [

    {
        position: "🥇",
        name: "Vth",
        points: 92,
        rank: "👑 Leyenda",
        positionName: "Rascarse los huevos",
        games: 3,
        level: 5,
        phrase: "Pinche chino, no me vuelvas a invitar a esto.",
        achievement: "Dormirse mientras contestaba",
        avatar: "😴"
    },

    {
        position: "🥈",
        name: "Kenia",
        points: 70,
        rank: "💎 Diamante",
        positionName: "Banca titular",
        games: 15,
        level: 7,
        phrase: "Chamaco miado, pon preguntas más fáciles.",
        achievement: "Aferrarse a ganar ❤️",
        avatar: "😤"
    },

    {
        position: "🥉",
        name: "Lizandro",
        points: 60,
        rank: "💎 Diamante",
        positionName: "Perro domesticado de Michelle",
        games: 1,
        level: -13,
        phrase: "Lo hice mientras cagaba.",
        achievement: "Pásenme el papel porfavor",
        avatar: "🐶"
    },

    {
        position: "4️⃣",
        name: "ChatGPT",
        points: 100,
        rank: "🥇 Oro",
        positionName: "Programador",
        games: 1,
        level: 1,
        phrase: "No me contó la trampa Lizandro",
        achievement: "Tramposo cachado",
        avatar: "🤖"
    },

    {
        position: "5️⃣",
        name: "La otra",
        points: 0,
        rank: "🥉 Bronce",
        positionName: "La otra",
        games: 0,
        level: 0,
        phrase: "No hay otra aferrada",
        achievement: "La única eres tú, Mich",
        avatar: "❓"
    }

];


function showScreen(screenId) {

    document.querySelectorAll(".screen").forEach(screen => {
        screen.classList.remove("active");
    });

    document.getElementById(screenId).classList.add("active");

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}


function loadRanking() {

    const list = document.getElementById("rankingList");

    list.innerHTML = "";

    players.forEach((player, index) => {

        const card = document.createElement("div");

        card.className = "card ranking-card";

        card.onclick = () => openProfile(index);

        card.innerHTML = `
            <div class="position">${player.position}</div>

            <div class="avatar-small">
                ${player.avatar}
            </div>

            <div class="player-info">
                <h3>${player.name}</h3>
                <p>${player.rank}</p>
            </div>

            <div class="points">
                ${player.points} ⭐
            </div>
        `;

        list.appendChild(card);

    });

}


function openProfile(index) {

    const player = players[index];

    const profile = document.getElementById("profileContent");

    profile.innerHTML = `

        <div class="profile">

            <div class="avatar-large">
                ${player.avatar}
            </div>

            <h2>${player.name}</h2>

            <div class="rank">
                ${player.rank}
            </div>

            <div class="card">

                <div class="stat">
                    <span>🏆 Puntos</span>
                    <strong>${player.points}</strong>
                </div>

                <div class="stat">
                    <span>🏐 Posición</span>
                    <strong>${player.positionName}</strong>
                </div>

                <div class="stat">
                    <span>🎮 Partidas jugadas</span>
                    <strong>${player.games}</strong>
                </div>

                <div class="stat">
                    <span>⭐ Nivel</span>
                    <strong>${player.level}</strong>
                </div>

            </div>

            <div class="card quote">
                💬 “${player.phrase}”
            </div>

            <div class="achievement">

                <div class="achievement-title">
                    🏅 LOGRO ESPECIAL
                </div>

                <strong>${player.achievement}</strong>

            </div>

        </div>

    `;

    showScreen("profile");

}


loadRanking();

</script>

</body>
</html>
