<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Bioquímica - 20 Perguntas (Atualizado)</title>
    <style>
        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background: #f6f8fa;
            color: #222;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 820px;
            margin: auto;
            background: #fff;
            box-shadow: 0 2px 14px rgba(0,0,0,0.08);
            border-radius: 10px;
            padding: 30px 24px 24px 24px;
            margin-top: 36px;
        }
        h1 {
            text-align: center;
            color: #117a8b;
        }
        .start-btn, .nav-btn, .finish-btn, .restart-btn {
            background: #117a8b;
            color: #fff;
            border: none;
            padding: 12px 24px;
            border-radius: 7px;
            font-size: 1.05rem;
            margin: 16px auto;
            display: block;
            cursor: pointer;
            box-shadow: 0 2px 4px rgba(0,0,0,0.06);
            transition: background 0.2s;
        }
        .start-btn:hover, .nav-btn:hover, .finish-btn:hover, .restart-btn:hover { background: #0e606b; }
        .question-count {
            text-align: right;
            font-size: 0.98rem;
            color: #555;
            margin-bottom: 10px;
        }
        .question-text {
            font-size: 1.18rem;
            margin-bottom: 18px;
            color: #1b4f72;
        }
        .options label {
            display: block;
            background: #f4f6f9;
            padding: 12px 14px;
            margin-bottom: 10px;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.2s;
        }
        .options input[type=radio] {
            margin-right: 14px;
        }
        .options label.selected {
            background: #e9f7ef;
            border-left: 4px solid #117a8b;
        }
        .feedback {
            margin-top: 14px;
            font-weight: bold;
            border-radius: 6px;
            padding: 12px;
            display: none;
        }
        .correct { background: #e9f7ef; color: #155724; border: 1px solid #c3e6cb; }
        .incorrect { background: #fdecea; color: #7a1f1f; border: 1px solid #f5c6cb; }
        .note { color: #555; font-size: 0.96rem; text-align: center; margin-bottom: 22px;}
        .result {
            text-align: center;
            margin-top: 40px;
        }
        .score {
            font-size: 1.35rem;
            font-weight: bold;
            margin-bottom: 16px;
            color: #117a8b;
        }
        .explain-small { font-size:0.95rem; color:#333; }
        @media (max-width: 600px) {
            .container { padding: 12px 6px; }
            h1 { font-size: 1.2rem; }
        }
    </style>
</head>
<body>
    <div class="container" id="main-container">
        <h1>Questionário de Bioquímica – Nível Intermediário (com Casos Clínicos)</h1>
        <div class="note">20 perguntas atualizadas com justificativas para a resposta correta.</div>
        <button class="start-btn" id="start-btn">Iniciar Quiz</button>
    </div>

    <script>
        // Perguntas do quiz (substituídas conforme solicitado pelo usuário),
        // cada 'explanation' começa com "✅ Correto!" para que o sistema mostre justificativa.
        const questions = [
            {
                text: "1) A água é essencial em quase todas as reações bioquímicas. Sobre suas propriedades, assinale a alternativa correta:",
                options: [
                    {text: "A) A água é uma molécula apolar e por isso dissolve bem lipídios.", value: "a"},
                    {text: "B) As ligações de hidrogênio entre moléculas de água são fracas, mas conferem alta coesão e ponto de ebulição elevado.", value: "b"},
                    {text: "C) A densidade da água aumenta ao congelar, pois as moléculas se aproximam.", value: "c"},
                    {text: "D) A água não participa de reações químicas, apenas serve como solvente.", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! Embora as ligações de hidrogênio sejam mais fracas que ligações covalentes, em conjunto conferem grande coesão, alta tensão superficial e ponto de ebulição relativamente elevado para uma molécula de pequeno peso."
            },
            {
                text: "2) (Caso clínico) Durante uma internação, um paciente apresenta acidose metabólica (pH sanguíneo de 7,10). O corpo tenta compensar essa alteração por meio de:",
                options: [
                    {text: "A) Aumento da frequência respiratória para eliminar CO₂", value: "a"},
                    {text: "B) Redução da ventilação pulmonar para reter CO₂", value: "b"},
                    {text: "C) Aumento da secreção de H⁺ pelos pulmões", value: "c"},
                    {text: "D) Diminuição da produção de bicarbonato pelos rins", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Na acidose metabólica os quimiorreceptores estimulam hiperventilação (respiração mais rápida/profunda) para eliminar CO₂, reduzindo H₂CO₃ e ajudando a elevar o pH (compensação respiratória)."
            },
            {
                text: "3) O corpo humano mantém o pH do sangue entre 7,35 e 7,45. O sistema tampão responsável por isso é o:",
                options: [
                    {text: "A) Tampão fosfato", value: "a"},
                    {text: "B) Tampão bicarbonato", value: "b"},
                    {text: "C) Tampão histidina-proteína", value: "c"},
                    {text: "D) Tampão amônia", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! O sistema bicarbonato (H₂CO₃ / HCO₃⁻) é o principal tampão do sangue e do meio extracelular, regulando rapidamente o pH."
            },
            {
                text: "4) (Caso clínico) Um paciente com DPOC apresenta retenção de CO₂. Isso causa:",
                options: [
                    {text: "A) Aumento do pH (alcalose respiratória)", value: "a"},
                    {text: "B) Diminuição do pH (acidose respiratória)", value: "b"},
                    {text: "C) Nenhuma alteração do pH", value: "c"},
                    {text: "D) Redução dos íons H⁺ no sangue", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! Retenção de CO₂ aumenta a formação de H₂CO₃ e, por consequência, H⁺ no sangue, diminuindo o pH → acidose respiratória."
            },
            {
                text: "5) Os carboidratos são importantes fontes de energia. Qual alternativa descreve corretamente um polissacarídeo e sua função?",
                options: [
                    {text: "A) Amido – reserva energética nos animais", value: "a"},
                    {text: "B) Glicogênio – reserva energética nos músculos e fígado", value: "b"},
                    {text: "C) Celulose – armazenamento de energia em plantas", value: "c"},
                    {text: "D) Quitina – fonte imediata de glicose no sangue", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! Glicogênio é o polissacarídeo de reserva em animais (fígado e músculo). Amido é reserva vegetal; celulose é estrutural; quitina é estrutural em artrópodes."
            },
            {
                text: "6) (Caso clínico) Uma amostra de urina de um paciente diabético apresentou glicose positiva. Esse achado indica que:",
                options: [
                    {text: "A) O fígado está produzindo pouca glicose.", value: "a"},
                    {text: "B) A glicose ultrapassou o limiar renal devido à hiperglicemia.", value: "b"},
                    {text: "C) A glicose está sendo degradada nos túbulos renais.", value: "c"},
                    {text: "D) O pâncreas aumentou a liberação de insulina.", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! Quando a glicemia supera o limiar renal (≈180 mg/dL, valor aproximado), os transportadores renais ficam saturados e a glicose aparece na urina (glicosúria)."
            },
            {
                text: "7) As proteínas são formadas pela união de aminoácidos. Durante a formação de uma ligação peptídica ocorre:",
                options: [
                    {text: "A) Adição de uma molécula de água", value: "a"},
                    {text: "B) Liberação de uma molécula de água", value: "b"},
                    {text: "C) Abertura da cadeia lateral (R)", value: "c"},
                    {text: "D) Quebra de um grupo amino", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! A ligação peptídica forma‑se por reação de condensação (síntese por desidratação) entre o grupo carboxila e o grupo amina, liberando H₂O."
            },
            {
                text: "8) Qual dos aminoácidos abaixo não apresenta carbono quiral?",
                options: [
                    {text: "A) Alanina", value: "a"},
                    {text: "B) Serina", value: "b"},
                    {text: "C) Glicina", value: "c"},
                    {text: "D) Valina", value: "d"}
                ],
                correct: "c",
                explanation: "✅ Correto! Glicina tem dois hidrogênios ligados ao carbono α, tornando‑o achiral. Outros aminoácidos têm quatro substituintes diferentes no Cα."
            },
            {
                text: "9) Sobre a estrutura das proteínas, marque a opção correta:",
                options: [
                    {text: "A) A estrutura primária é a sequência linear de aminoácidos.", value: "a"},
                    {text: "B) A estrutura secundária depende apenas das cadeias laterais (R).", value: "b"},
                    {text: "C) A estrutura terciária não influencia a função da proteína.", value: "c"},
                    {text: "D) Todas as proteínas possuem estrutura quaternária.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Estrutura primária = sequência de aminoácidos. Estruturas superiores (secundária/terciária/quaternária) resultam do enovelamento e interações diversas."
            },
            {
                text: "10) (Caso clínico) Um paciente ingeriu clara de ovo crua em excesso e apresentou sintomas de deficiência de biotina (vitamina B7). Isso ocorreu porque a avidina, proteína presente na clara, ao ser desnaturada pelo calor da cocção:",
                options: [
                    {text: "A) Perde sua estrutura e não se liga mais à biotina.", value: "a"},
                    {text: "B) Aumenta sua afinidade pela biotina.", value: "b"},
                    {text: "C) Passa a quebrar a biotina, reduzindo sua absorção.", value: "c"},
                    {text: "D) Torna-se tóxica ao fígado.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Avidina nas claras cruas liga fortemente à biotina e impede sua absorção. Ao cozinhar, a avidina é desnaturada e perde a capacidade de ligação, por isso claras cozidas não causam deficiência."
            },
            {
                text: "11) As enzimas catalisam reações químicas porque:",
                options: [
                    {text: "A) Diminuem a energia de ativação da reação.", value: "a"},
                    {text: "B) Aumentam a energia total liberada.", value: "b"},
                    {text: "C) São consumidas durante a reação.", value: "c"},
                    {text: "D) Alteram o equilíbrio químico da reação.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Enzimas aceleram reações reduzindo a energia de ativação; não são consumidas e não alteram o equilíbrio final, apenas a velocidade."
            },
            {
                text: "12) O valor de Km (constante de Michaelis) indica:",
                options: [
                    {text: "A) A concentração de substrato em que a velocidade é máxima.", value: "a"},
                    {text: "B) A afinidade da enzima pelo substrato — quanto menor o Km, maior a afinidade.", value: "b"},
                    {text: "C) A quantidade total de enzima presente.", value: "c"},
                    {text: "D) A energia de ativação da reação.", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! Km é a concentração de substrato à qual a velocidade é metade de Vmax. Km baixo significa que a enzima alcança metade da Vmax com pouca concentração de substrato → alta afinidade."
            },
            {
                text: "13) (Caso clínico) Um paciente hipertenso faz uso de inibidores da ECA. Esse medicamento atua:",
                options: [
                    {text: "A) Inibindo a enzima que converte angiotensina I em angiotensina II, reduzindo a pressão arterial.", value: "a"},
                    {text: "B) Aumentando a atividade da renina, elevando a pressão arterial.", value: "b"},
                    {text: "C) Acelerando a conversão de angiotensina II em angiotensina I.", value: "c"},
                    {text: "D) Estimulando a vasoconstrição direta pelos rins.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! IECAs inibem a ECA, diminuindo a formação de angiotensina II (um potente vasoconstritor) e, assim, reduzindo a pressão arterial."
            },
            {
                text: "14) Os lipídios são fundamentais para a estrutura celular. Qual lipídio é o principal componente das membranas biológicas?",
                options: [
                    {text: "A) Triacilgliceróis", value: "a"},
                    {text: "B) Fosfolipídios", value: "b"},
                    {text: "C) Ceras", value: "c"},
                    {text: "D) Colesterol livre", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! Fosfolipídios formam a bicamada lipídica das membranas. Colesterol também está presente modulando fluidez, mas o componente estrutural principal são os fosfolipídios."
            },
            {
                text: "15) Os ácidos graxos insaturados possuem duplas ligações em sua cadeia. Essa característica:",
                options: [
                    {text: "A) Diminui o ponto de fusão e aumenta a fluidez das membranas.", value: "a"},
                    {text: "B) Aumenta o ponto de fusão e reduz a fluidez.", value: "b"},
                    {text: "C) Não interfere nas propriedades físicas.", value: "c"},
                    {text: "D) Torna o ácido graxo sólido à temperatura ambiente.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Duplas ligações (especialmente cis) criam dobras que impedem o empacotamento, reduzindo o ponto de fusão e aumentando a fluidez da bicamada."
            },
            {
                text: "16) (Caso clínico) Um paciente com dieta extremamente pobre em gorduras apresentou dificuldade na absorção de vitaminas A, D, E e K. A explicação correta é:",
                options: [
                    {text: "A) Essas vitaminas são lipossolúveis e dependem de lipídios para serem absorvidas.", value: "a"},
                    {text: "B) O excesso de proteína impede a absorção intestinal.", value: "b"},
                    {text: "C) As vitaminas hidrossolúveis neutralizam as lipossolúveis.", value: "c"},
                    {text: "D) A bile não influencia na digestão de vitaminas.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Vitaminas A, D, E e K são lipossolúveis; a absorção intestinal depende de lipídios e da formação de micelas mediadas pela bile."
            },
            {
                text: "17) As vitaminas lipossolúveis dependem da absorção de gorduras no intestino. Qual delas é essencial para a absorção de cálcio e formação óssea?",
                options: [
                    {text: "A) Vitamina A", value: "a"},
                    {text: "B) Vitamina D", value: "b"},
                    {text: "C) Vitamina E", value: "c"},
                    {text: "D) Vitamina K", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! A vitamina D regula a absorção intestinal de cálcio e é crucial para o metabolismo ósseo e mineralização."
            },
            {
                text: "18) Sobre os eicosanoides, derivados de ácidos graxos poli-insaturados, é correto afirmar:",
                options: [
                    {text: "A) Têm ação hormonal local e participam de processos inflamatórios.", value: "a"},
                    {text: "B) São carboidratos que formam parte da parede celular.", value: "b"},
                    {text: "C) São proteínas que transportam oxigênio.", value: "c"},
                    {text: "D) Não possuem relevância fisiológica.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Eicosanoides (prostaglandinas, tromboxanos, leucotrienos) são mediadores locais derivados de ácidos graxos e participam de inflamação, agregação plaquetária e outras respostas."
            },
            {
                text: "19) (Caso clínico) Uma análise genética de um paciente revelou mutação nos esfingolipídios da membrana. Isso pode causar:",
                options: [
                    {text: "A) Alterações no reconhecimento celular e nos tipos sanguíneos.", value: "a"},
                    {text: "B) Diminuição da respiração celular nas mitocôndrias.", value: "b"},
                    {text: "C) Aumento da permeabilidade nuclear.", value: "c"},
                    {text: "D) Redução da síntese de proteínas ribossomais.", value: "d"}
                ],
                correct: "a",
                explanation: "✅ Correto! Esfingolipídios e glicoesfingolipídios participam de reconhecimento celular e antígenos de superfície; mutações podem alterar sinalização e reconhecimento (ex.: algumas doenças lisossomais)."
            },
            {
                text: "20) O glicogênio é o principal polissacarídeo de reserva animal. Ele é armazenado principalmente:",
                options: [
                    {text: "A) Nos rins e nos pulmões", value: "a"},
                    {text: "B) No fígado e nos músculos", value: "b"},
                    {text: "C) No coração e no sangue", value: "c"},
                    {text: "D) Nos neurônios e na pele", value: "d"}
                ],
                correct: "b",
                explanation: "✅ Correto! Glicogênio é armazenado principalmente no fígado (para regular glicemia) e nos músculos (reserva energética para atividade)."
            }
        ];

        // Estado do quiz
        let current = 0;
        let userAnswers = [];
        let feedbackStates = [];
        let score = 0;

        const container = document.getElementById('main-container');
        const startBtn = document.getElementById('start-btn');

        startBtn.onclick = () => { startQuiz(); };

        function startQuiz() {
            current = 0;
            userAnswers = Array(questions.length).fill(null);
            feedbackStates = Array(questions.length).fill(false);
            score = 0;
            showQuestion();
        }

        function showQuestion() {
            const q = questions[current];
            let html = `
                <div class="question-count">Pergunta ${current+1} de ${questions.length}</div>
                <div class="question-text">${q.text}</div>
                <form id="question-form">
                    <div class="options">
                        ${q.options.map((opt, i) => `
                            <label class="${userAnswers[current] === opt.value ? 'selected' : ''}">
                                <input type="radio" name="option" value="${opt.value}" ${userAnswers[current] === opt.value ? 'checked' : ''}>
                                ${opt.text}
                            </label>
                        `).join('')}
                    </div>
                    ${!feedbackStates[current] ? `<button type="button" class="nav-btn" id="check-btn">Verificar Resposta</button>` : ''}
                </form>
                <div class="feedback" id="feedback"></div>
                <div style="margin-top:18px;">
                    ${current > 0 ? '<button class="nav-btn" id="prev-btn">&larr; Anterior</button>' : ''}
                    ${current < questions.length-1 ? `<button class="nav-btn" id="next-btn" style="display:${feedbackStates[current] ? 'inline-block' : 'none'};">Próxima &rarr;</button>` : ''}
                    ${current === questions.length-1 && feedbackStates[current] ? '<button class="finish-btn" id="finish-btn">Ver Resultado</button>' : ''}
                </div>
            `;
            container.innerHTML = html;

            if (!feedbackStates[current]) {
                document.getElementById('check-btn').onclick = () => checkAnswer();
            }
            if (current > 0) document.getElementById('prev-btn').onclick = () => prevQuestion();
            if (current < questions.length-1) document.getElementById('next-btn').onclick = () => nextQuestion();
            if (current === questions.length-1 && feedbackStates[current]) document.getElementById('finish-btn').onclick = () => showResult();

            // Se já respondeu, mostra feedback
            if (feedbackStates[current]) showFeedback();
        }

        function checkAnswer() {
            const radios = document.getElementsByName('option');
            let selected = null;
            for (const r of radios) {
                if (r.checked) selected = r.value;
            }
            const feedback = document.getElementById('feedback');
            if (!selected) {
                feedback.textContent = "Por favor, selecione uma opção!";
                feedback.className = "feedback incorrect";
                feedback.style.display = "block";
                return;
            }
            userAnswers[current] = selected;
            feedbackStates[current] = true;
            if (!feedback.dataset.scored) {
                if (selected === questions[current].correct) score++;
                feedback.dataset.scored = "1";
            }
            showQuestion(); // Re-renderiza a pergunta, removendo botão de verificar e mostrando botão próxima
        }

        function showFeedback() {
            const feedback = document.getElementById('feedback');
            const q = questions[current];
            if (userAnswers[current] === q.correct) {
                feedback.innerHTML = q.explanation;
                feedback.className = "feedback correct";
            } else {
                let wrongText = q.explanation.replace('✅ Correto! ', '');
                feedback.innerHTML = `❌ Incorreto. ${wrongText}`;
                feedback.className = "feedback incorrect";
            }
            feedback.style.display = "block";
        }

        function nextQuestion() {
            current++;
            showQuestion();
        }
        function prevQuestion() {
            current--;
            showQuestion();
        }

        function showResult() {
            let html = `
                <div class="result">
                    <div class="score">Você acertou ${score} de ${questions.length} perguntas.</div>
                    <div style="margin:24px 0">
                        <button class="restart-btn" onclick="window.location.reload()">Refazer Quiz</button>
                    </div>
                    <div>
                        <h3>Gabarito e justificativas:</h3>
                        <ul style="text-align:left;">
                            ${questions.map((q, i) => {
                                let user = userAnswers[i];
                                let isCorrect = user === q.correct;
                                let correctText = q.options.find(opt => opt.value === q.correct).text;
                                return `<li style="margin-bottom:10px;">
                                        <strong>P${i+1}:</strong> ${q.text}<br>
                                        <em>Resposta correta: ${correctText}</em><br>
                                        <span class="explain-small">${q.explanation.replace('✅ Correto! ','')}</span>
                                        ${isCorrect ? ' <span style="color:#117a8b; font-weight:bold">✔️ Você acertou</span>' : ' <span style="color:#7a1f1f; font-weight:bold">❌ Você errou</span>'}
                                    </li>`;
                            }).join('')}
                        </ul>
                    </div>
                </div>
            `;
            container.innerHTML = html;
        }
    </script>
</body>
</html>
