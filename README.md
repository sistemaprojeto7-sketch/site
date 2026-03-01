:root {
    --primary: #6c4cff;
    --secondary: #ff4cff; /* Rosa para o branding moderno */
    --dark: #0b0b14;
    --glass: rgba(255, 255, 255, 0.05);
}

body {
    margin: 0;
    font-family: 'Inter', sans-serif;
    background: var(--dark);
    color: #fff;
    line-height: 1.6;
    overflow-x: hidden;
    position: relative;
}

body::before {
    content: "";
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: radial-gradient(circle at 20% 30%, rgba(108, 76, 255, 0.2), transparent 40%),
                radial-gradient(circle at 80% 70%, rgba(255, 76, 173, 0.15), transparent 40%);
    z-index: -1;
    animation: aurora 15s infinite alternate ease-in-out;
}

@keyframes aurora {
    0% { transform: scale(1); filter: blur(20px); }
    100% { transform: scale(1.2); filter: blur(40px); }
}

.container { width: 90%; max-width: 1100px; margin: auto; }

/* NAV */
.nav { position: fixed; width: 100%; background: rgba(11, 11, 20, 0.8); backdrop-filter: blur(10px); z-index: 100; }
.nav-content { display: flex; justify-content: space-between; align-items: center; padding: 15px 0; }
.logo { font-weight: 800; font-size: 1.4rem; letter-spacing: 1px; }
.highlight { color: var(--primary); }
.nav-links a { margin-left: 20px; text-decoration: none; color: #fff; font-size: 0.9rem; font-weight: 600; }

.btn-nav { background: var(--primary); padding: 8px 18px; border-radius: 5px; }
.btn-alt { border: 1px solid var(--secondary); padding: 8px 18px; border-radius: 5px; color: var(--secondary) !important; }

/* HERO */
.hero { padding: 160px 0 100px; }
.hero-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 50px; align-items: center; }
.tag { background: var(--glass); padding: 6px 15px; border-radius: 50px; font-size: 0.75rem; font-weight: 800; color: var(--primary); }
.hero h1 { font-size: 3.5rem; line-height: 1.1; margin: 20px 0; }
.cta-main { background: var(--primary); padding: 18px 35px; border-radius: 8px; text-decoration: none; color: #fff; font-weight: 800; display: inline-block; margin-right: 15px; }
.cta-secondary { border: 1px solid #fff; padding: 18px 35px; border-radius: 8px; text-decoration: none; color: #fff; font-weight: 800; display: inline-block; }

/* HERO CARD */
.hero-card {
    position: relative;
    background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('logistica-bg.jpg');
    background-size: cover;
    padding: 40px;
    border-radius: 20px;
    border: 1px solid rgba(108, 76, 255, 0.3);
}
.central-title { color: var(--primary); text-align: center; margin-bottom: 30px; }
.distributed-list { list-style: none; padding: 0; display: flex; flex-direction: column; gap: 15px; }
.floating-item { background: var(--glass); padding: 15px; border-radius: 12px; display: flex; gap: 15px; align-items: center; border: 1px solid rgba(255,255,255,0.1); }
.floating-item span { font-size: 1.5rem; }

/* COMPARAÇÃO */
.method { padding: 100px 0; background: rgba(15, 15, 32, 0.5); }
.comparison-container { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; margin-top: 50px; }
.comparison-card { background: var(--glass); padding: 30px; border-radius: 20px; border: 1px solid rgba(255,255,255,0.05); }
.comparison-card.solution { border-color: var(--primary); box-shadow: 0 0 30px rgba(108, 76, 255, 0.1); }
.comparison-card ul { list-style: none; padding: 0; }
.comparison-card li { margin-bottom: 15px; display: flex; gap: 10px; }

/* FORMS */
.contact { padding: 100px 0; }
.contact-box { max-width: 600px; margin: auto; text-align: center; }
.main-form { background: var(--glass); padding: 40px; border-radius: 20px; text-align: left; }
.form-group { margin-bottom: 15px; }
.main-form input, .main-form textarea { width: 100%; padding: 15px; border-radius: 8px; border: 1px solid rgba(255,255,255,0.1); background: #fff; color: #333; box-sizing: border-box; }
.main-form button { width: 100%; padding: 20px; background: var(--primary); color: #fff; border: none; border-radius: 8px; font-weight: 800; cursor: pointer; }

/* UTILS */
.grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
.card { background: var(--glass); padding: 30px; border-radius: 15px; text-align: center; }
.icon-box { font-size: 2.5rem; margin-bottom: 15px; }
.section-title { font-size: 2.5rem; margin-bottom: 50px; text-align: center; }


/* Ajuste para as imagens dos cards não ficarem gigantes */
.card-img-container {
    width: 100%;
    height: 120px; /* Altura pequena e fixa */
    overflow: hidden;
    border-radius: 10px;
    margin-bottom: 15px;
    border: 1px solid rgba(108, 76, 255, 0.2);
}

.card-img-container img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Faz a imagem preencher o espaço sem distorcer */
    transition: transform 0.3s ease;
}

.card:hover .card-img-container img {
    transform: scale(1.1);
}

/* Reorganização do Hero (Texto Esquerda, Card Direita) */
.hero-grid {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr; /* Texto ganha mais espaço */
    gap: 40px;
    align-items: center;
}

/* Ajuste específico para Celular */
@media (max-width: 900px) {
    .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
    }

    .hero-text {
        order: 1; /* Texto primeiro */
    }

    .hero-card {
        order: 2; /* Card depois */
        min-height: 400px;
        margin-top: 30px;
    }

    .grid-3 {
        grid-template-columns: 1fr; /* Um card por linha no celular */
    }

    .card-img-container {
        height: 150px; /* Um pouco maior no celular para preencher a largura */
    }
}

/* --- RESPONSIVO --- */
@media (max-width: 900px) {
    .hero-grid, .grid-3, .comparison-container { grid-template-columns: 1fr; }
    .hero h1 { font-size: 2.5rem; }
}
