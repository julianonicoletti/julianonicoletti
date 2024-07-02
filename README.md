
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Text in Box</title>
    <style>
        /* Estilos para a caixa azul */
        .box {
            background-color: #f0f8ff; /* Cor de fundo azul claro */
            padding: 30px; /* Espaçamento interno da caixa */
            border: 1px solid #a6cae1; /* Borda da caixa */
            border-radius: 10px; /* Borda arredondada */
            width: 80%; /* Largura da caixa */
            margin: 20px auto; /* Centralizar a caixa horizontalmente com margem */
            text-align: center; /* Centralizar o texto dentro da caixa */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Sombra suave */
            font-family: "Roboto", sans-serif;
            font-weight: 500;
            font-style: normal; /* Fonte do texto */
        }

        /* Estilos para o efeito de digitação */
        .typing {
            font-size: 1.5em; /* Tamanho da fonte */
            font-weight: bold; /* Negrito */
            color: #333; /* Cor do texto */
            overflow: hidden; /* Evita que o texto apareça antes da animação */
            white-space: nowrap; /* Garante que o texto não quebre linha */
            margin: 0 auto;
            letter-spacing: .1em; /* Espaçamento entre caracteres */
            animation: typing 3.5s steps(40, end), blink-caret .75s step-end infinite;
            transform: scale(1); /* Efeito de escala inicial */
            transition: transform 0.5s ease-out; /* Transição suave de escala */
        }

        /* Animação de digitação */
        @keyframes typing {
            from {
                width: 0;
            }
            to {
                width: 100%;
            }
        }

        /* Animação do cursor de digitação */
        @keyframes blink-caret {
            from, to {
                border-color: transparent;
            }
            50% {
                border-color: orange;
            }
        }
    </style>
</head>
<body>
    <div class="box">
        <h1 id="greeting" style="color: #333;">Bom dia!</h1>
        <p id="text" class="typing"></p>
    </div>

    <script>
        // Função para obter o período do dia
        function getGreeting() {
            var hour = new Date().getHours();
            var greeting = "Bom dia!";

            if (hour >= 12 && hour < 18) {
                greeting = "Boa tarde!";
            } else if (hour >= 18 || hour < 6) {
                greeting = "Boa noite!";
            }

            return greeting;
        }

        // Função para animar texto com troca automática
        function animateText() {
            var phrases = [
                "Olá, meu nome é Juliano Batistela Nicoletti",
                "Este é o meu Portfólio de Ciência de Dados"
            ];
            var index = 0;
            var textElement = document.getElementById('text');
            var greetingElement = document.getElementById('greeting');

            greetingElement.textContent = getGreeting(); // Define a saudação baseada no horário

            function typeWriter() {
                var text = phrases[index];
                var charIndex = 0;
                var typingInterval = setInterval(function() {
                    if (charIndex < text.length) {
                        textElement.textContent += text.charAt(charIndex);
                        charIndex++;
                    } else {
                        clearInterval(typingInterval);
                        setTimeout(function() {
                            eraseText();
                        }, 2500); // Aguarda 4 segundos antes de apagar o texto
                    }
                }, 70); // Velocidade de digitação (100 milissegundos)

                function eraseText() {
                    var eraseInterval = setInterval(function() {
                        if (textElement.textContent.length > 0) {
                            textElement.textContent = textElement.textContent.slice(0, -1);
                        } else {
                            clearInterval(eraseInterval);
                            index = (index + 1) % phrases.length;
                            setTimeout(function() {
                                typeWriter();
                            }, 500); // Aguarda 0.5 segundos antes de começar a próxima frase
                        }
                    }, 25); // Velocidade de apagar texto (50 milissegundos)
                }
            }

            typeWriter();
        }

        // Inicia a animação após um atraso de 1 segundo (1000 milissegundos)
        setTimeout(function() {
            animateText();
        }, 1000);
    </script>
</body>
</html>


## 🔍 Sobre mim

- Estudo Engenharia de Software na Unifil, Londrina - PR.
- Estudo Ciência de Dados e Análise de dados.
- Atualmente faço estágio no setor de Análise de Dados da Universidade Estadual de Londrina, criando aplicativos na plataforma Qlik para tomada de decisões pelos diversos setores.
- Tenho outra graduação na área de Farmacia-Bioquímica onde atuei por mais de 12 anos.

---

## 🖥️ Tech Skills

- Estudei Java e Python.
- Tenho vários projetos concluídos onde utlizado bibliotecas do Python para análise e criação de modelos de predição (Pandas, Scikit-learn, Jupyter Notebook, Matplotlib)
- Tenho conhecimentos sólidos de SQL e DataWarehouse.

<div style="text-align: center;">
    <img src="images.jpg" alt="alt text" height="45" style="margin-bottom: 10px; margin-right: 5px">
    <img src="java_image.png" alt="alt text" height="45" style="margin-bottom: 10px;">
    <img src="Pandas_logo.svg.png" alt="alt text" height="55" style="margin-bottom: 10px; margin-right: 5px">
    <img src="scikitlearn.png" alt="alt text" height="55" style="margin-bottom: 10px; margin-right: 8px">
    <img src="883px-Jupyter_logo.svg.png" alt="alt text" height="55" style="margin-bottom: 10px; margin-right: 0px">
    <img src="azure-sql-database6354.jpg" alt="alt text" height="60" style="margin-bottom: 10px; margin-right: 5px">
    <img src="Qlik_Logo.svg.png" alt="alt text" height="45" style="margin-bottom: 10px; margin-right: 5px">
</div>

---

## 📑Projetos

### 📈 [Previsão de faturamento de uma rede de Farmácias](https://github.com/julianonicoletti/rossmann_prediction_deploy)

Com dados públicos fornecido por uma rede de farmácias da Europa, fiz uma análise exploratória seguido pela construção de um modelo de predição de faturamento para as próximas 12 semanas de cada uma das 1015 filiais. A solução foi entregue e pode ser acessada via Bot do Telegram.

<div style="text-align: center;">
    <img src="image.png" alt="alt text" height="150" style="margin: 0 10px 10px 10px;">
    <img src="image-1.png" alt="alt text" height="150" style="margin: 0 10px 10px 10px;">
    <img src="image-2.png" alt="alt text" height="160" style="margin: 0 10px 10px 10px;">
    <img src="image-3.png" alt="alt text" height="170" style="margin: 0 10px 10px 10px;">
</div>

[Veja o projeto no GitHub](https://github.com/julianonicoletti/rossmann_prediction_deploy)
___

### 📊 [Dashboard interativo de um serviço de busca de restaurantes usando Streamlit](https://github.com/julianonicoletti/dashboard_zomato)

Com dados públicos fiz uma análise de um serviço de busca de restaurantes presente em vários países. Foi elaborado um dashboard usando o framework Streamlit do Python. Analisamos o resultados dos restaurantes, a distribuição entre os países, e KPIs sobre performance e ranking dos melhores por votação dos clientes.
<div style="text-align: center;">
    <img src="image-4.png" alt="alt text" height="140" style="margin: 0 10px 10px 10px;">
    <img src="image-5.png" alt="alt text" height="140" style="margin: 0 10px 10px 10px;">
    <img src="image-6.png" alt="alt text" height="140" style="margin: 0 10px 10px 10px;">

</div>

[Veja o projeto no GitHub](https://github.com/julianonicoletti/dashboard_zomato)

___

### ❤️ [Modelo de previsão de eventos cardiovasculares](https://github.com/julianonicoletti/cardio_predict_model)

Fiz uma análise de um dataset com dados de saúde de 70 mil pacientes com informações como pressão arterial, idade, peso, atividade física, fumante e níveis de glicemia entre outros. Após a análise dos dados foi treinado e testado um modelo que, com base nesses dados fornecidos pelo usuário, ele consegue prever as chances de desenvolver um problema cardíaco. A solução foi hospedada no Streamlit Cloud e disponível para qualquer pessoa utilizar.
<div style="text-align: center;">
    <img src="image-7.png" alt="alt text" height="165" style="margin: 0 10px 10px 10px;">
    <img src="image-8.png" alt="alt text" height="165" style="margin: 0 10px 10px 10px;">
    <img src="image-9.png" alt="alt text" height="175" style="margin: 0 10px 10px 10px;">
</div>

[Veja o projeto no GitHub](https://github.com/julianonicoletti/cardio_predict_model)

---

## 🛠 Habilidades

Adoro estudar e aprender coisas novas, sempre fui muito curioso. Tenho ótima comunicação interpessoal, gosto de trabalhar em equipe e aprender ensinando.

---
## Interessante

⚡️ Fatos engraçados, lá vem história:
Tive meu primeiro contato com computadores lá pelos anos 90 quando meu pai comprou um 486DX2 para "digitalizar" seu estoque de produtos de Livraria e Papelaria (Livraria Kometa em Cianorte no Paraná). Peguei uma apostila de MS-DOS de um amigo e aprendi praticamente tudo sozinho. Ele comprou um software de controle de estoque e fiquei mais de 45 dias das minhas férias cadastrando os quase 1200 produtos da loja. Sempre gostei da área, montei meu primeiro computador em 2000, um Athlon (K7), mas por escolhas fiz faculdade de Farmácia. Aprendi e exerci muita coisa nesses quase 15 anos. Agora, em 2023 resolvi voltar a minha primeira paixão, já experiente como pessoa, mas ainda iniciante na área de programação..

---
## Contato

<a href="https://www.linkedin.com/in/juliano-nicoletti-06549359/">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" align="center" height="60"width="70">
<a href="https://www.facebook.com/juliano.nicoletti">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/facebook/facebook-original.svg" align="center" height="60"width="70">
    <a href="https://medium.com/@julianonicoletti_82306">
    <img src="https://upload.wikimedia.org/wikipedia/commons/e/ec/Medium_logo_Monogram.svg" align="center" height="60"width="70">
</div>
</a>
