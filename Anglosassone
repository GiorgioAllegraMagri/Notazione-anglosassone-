<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Scale Flashcards 🎵</title>
    <style>
        :root { --primary: #2563eb; --secondary: #64748b; }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; display: flex; flex-direction: column; align-items: center; justify-content: center; min-height: 100vh; margin: 0; background-color: #f8fafc; }
        
        .container { width: 90%; max-width: 400px; perspective: 1000px; }
        
        /* Animazione Flashcard */
        .flashcard { width: 100%; height: 250px; position: relative; transform-style: preserve-3d; transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1); cursor: pointer; }
        .flashcard.flipped { transform: rotateY(180deg); }
        
        .face { position: absolute; width: 100%; height: 100%; backface-visibility: hidden; display: flex; flex-direction: column; align-items: center; justify-content: center; border-radius: 20px; box-shadow: 0 10px 25px rgba(0,0,0,0.1); padding: 20px; box-sizing: border-box; text-align: center; border: 4px solid white; }
        
        .front { background: white; color: var(--primary); }
        .back { background: var(--primary); color: white; transform: rotateY(180deg); }
        
        .note-name { font-size: 3rem; font-weight: bold; margin: 0; }
        .ita-name { font-size: 1.2rem; color: var(--secondary); margin-bottom: 10px; }
        .alterations { font-size: 2rem; font-weight: bold; }
        
        .controls { margin-top: 30px; display: flex; gap: 15px; }
        button { padding: 12px 25px; border: none; border-radius: 10px; background: white; color: var(--primary); font-weight: bold; cursor: pointer; box-shadow: 0 4px 6px rgba(0,0,0,0.05); transition: 0.2s; border: 1px solid #e2e8f0; }
        button:hover { background: #f1f5f9; transform: translateY(-2px); }
        .instruction { margin-top: 20px; color: #94a3b8; font-size: 0.9rem; }
    </style>
</head>
<body>

    <div class="container">
        <div class="flashcard" id="card" onclick="this.classList.toggle('flipped')">
            <div class="face front">
                <p class="ita-name" id="ita-front"></p>
                <p class="note-name" id="eng-front"></p>
                <p style="font-size: 0.8rem; color: #94a3b8;">Clicca per girare</p>
            </div>
            <div class="face back">
                <p style="font-size: 0.9rem; opacity: 0.8;">Alterazioni:</p>
                <p class="alterations" id="ans-back"></p>
            </div>
        </div>
    </div>

    <div class="controls">
        <button onclick="prevCard()">⬅️ Indietro</button>
        <button onclick="nextCard()">Prossima ➡️</button>
    </div>

    <p class="instruction">Tocca la carta per vedere la soluzione</p>

    <script>
        const scales = [
            { eng: "C Major", ita: "Do Maggiore", alt: "Nessuna" },
            { eng: "G Major", ita: "Sol Maggiore", alt: "F#" },
            { eng: "D Major", ita: "Re Maggiore", alt: "F#, C#" },
            { eng: "A Major", ita: "La Maggiore", alt: "F#, C#, G#" },
            { eng: "E Major", ita: "Mi Maggiore", alt: "F#, C#, G#, D#" },
            { eng: "B Major", ita: "Si Maggiore", alt: "F#, C#, G#, D#, A#" },
            { eng: "F# Major", ita: "Fa# Maggiore", alt: "F#, C#, G#, D#, A#, E#" },
            { eng: "F Major", ita: "Fa Maggiore", alt: "Bb" },
            { eng: "Bb Major", ita: "Sib Maggiore", alt: "Bb, Eb" },
            { eng: "Eb Major", ita: "Mib Maggiore", alt: "Bb, Eb, Ab" },
            { eng: "Ab Major", ita: "Lab Maggiore", alt: "Bb, Eb, Ab, Db" },
            { eng: "Db Major", ita: "Reb Maggiore", alt: "Bb, Eb, Ab, Db, Gb" }
        ];

        let currentIndex = 0;
        const card = document.getElementById('card');

        function updateCard() {
            card.classList.remove('flipped');
            setTimeout(() => {
                document.getElementById('eng-front').innerText = scales[currentIndex].eng;
                document.getElementById('ita-front').innerText = scales[currentIndex].ita;
                document.getElementById('ans-back').innerText = scales[currentIndex].alt;
            }, 150);
        }

        function nextCard() {
            currentIndex = (currentIndex + 1) % scales.length;
            updateCard();
        }

        function prevCard() {
            currentIndex = (currentIndex - 1 + scales.length) % scales.length;
            updateCard();
        }

        // Inizializza la prima carta
        updateCard();
    </script>
</body>
</html>
