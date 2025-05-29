
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Rotinas Diárias - Segunda a Sexta</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap');

  :root {
    --primary-color: #6a11cb;
    --secondary-color: #2575fc;
    --bg-gradient: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
    --text-color: #fff;
    --card-bg: rgba(255 255 255 / 0.1);
    --shadow: 0 8px 24px rgba(101, 41, 255, 0.3);
  }

  * {
    box-sizing: border-box;
  }

  body {
    margin:0; padding:0;
    font-family: 'Poppins', sans-serif;
    background: var(--bg-gradient);
    color: var(--text-color);
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  header {
    padding: 2rem 1rem 1rem;
    text-align: center;
  }

  header h1 {
    margin: 0;
    font-weight: 600;
    font-size: 2.8rem;
    letter-spacing: 0.05em;
    text-shadow: 0 0 8px rgba(255 255 255 / 0.7);
  }

  nav {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin: 1rem 0 2rem;
  }

  nav button {
    background: var(--card-bg);
    border: none;
    border-radius: 12px;
    padding: 0.6rem 1.4rem;
    font-weight: 600;
    font-size: 1rem;
    color: var(--text-color);
    cursor: pointer;
    box-shadow: var(--shadow);
    transition: background 0.3s ease, transform 0.2s ease;
    position: relative;
    overflow: hidden;
  }

  nav button:hover {
    background: var(--secondary-color);
    transform: translateY(-3px);
  }

  nav button.active {
    background: var(--secondary-color);
    box-shadow: 0 10px 30px rgba(37, 117, 252, 0.7);
    transform: translateY(-3px);
  }

  main {
    width: 90%;
    max-width: 520px;
    background: var(--card-bg);
    border-radius: 20px;
    padding: 2rem 2.5rem;
    box-shadow: var(--shadow);
    backdrop-filter: blur(10px);
  }

  main h2 {
    margin-top: 0;
    font-weight: 600;
    font-size: 2rem;
    text-align: center;
    color: #e0e0ff;
    text-shadow: 0 0 4px rgba(255 255 255 / 0.5);
  }

  ul.task-list {
    list-style: none;
    padding-left: 0;
    margin-top: 1.5rem;
  }

  ul.task-list li {
    background: rgba(0 0 0 / 0.3);
    margin-bottom: 0.9rem;
    padding: 0.9rem 1.2rem;
    border-radius: 12px;
    font-weight: 500;
    font-size: 1.1rem;
    display: flex;
    align-items: center;
    gap: 1rem;
    color: #cfd8ff;
    box-shadow: inset 1px 1px 4px rgba(255 255 255 / 0.15);
    position: relative;
    transition: background 0.3s ease;
  }
  ul.task-list li::before {
    content: "✔";
    color: #88ff88;
    font-weight: 700;
    font-size: 1.3rem;
    display: inline-block;
  }
  ul.task-list li:hover {
    background: rgba(37 117 252 / 0.7);
    color: white;
    cursor: default;
  }

  footer {
    margin: 3rem 0 1rem;
    font-size: 0.9rem;
    color: #d0d0f0aa;
    user-select: none;
  }

  /* animate fade for task list */
  .fade {
    animation: fadeIn 0.6s ease forwards;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(15px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>
</head>
<body>
  <header>
    <h1>Rotinas Diárias</h1>
    <p>Segunda a Sexta - Seu guia para produtividade</p>
  </header>
  <nav aria-label="Dias da Semana">
    <button type="button" data-day="Segunda" class="active" aria-current="true">Segunda</button>
    <button type="button" data-day="Terça">Terça</button>
    <button type="button" data-day="Quarta">Quarta</button>
    <button type="button" data-day="Quinta">Quinta</button>
    <button type="button" data-day="Sexta">Sexta</button>
  </nav>
  <main>
    <h2 id="day-title">Segunda</h2>
    <ul class="task-list" id="task-list" aria-live="polite" aria-atomic="true">
      <!-- Tasks inserted here -->
    </ul>
  </main>
  <footer>
    &copy; 2024 Rotinas Diárias
  </footer>

<script>
  const routines = {
    Segunda: [
      "Revisar e responder e-mails urgentes",
      "Planejar o cronograma semanal",
      "Reunião de equipe às 9h",
      "Criação de wireframes para novo projeto",
      "Atualizar portfólio de design",
      "Feedback sobre materiais entregues",
      "Organizar arquivos e referências"
    ],
    Terça: [
      "Pesquisa de tendências e inspiração visual",
      "Desenvolver layouts para campanha digital",
      "Reunião com o cliente às 14h",
      "Testes de usabilidade e ajuste de protótipos",
      "Revisão e refinamento dos ativos gráficos",
      "Estudo de novas ferramentas de design",
      "Organização do mood board"
    ],
    Quarta: [
      "Criar conteúdos para redes sociais",
      "Sessão de brainstorming com equipe de marketing",
      "Ajustes nas ilustrações do site",
      "Revisão dos feedbacks recebidos",
      "Atualização do manual de identidade visual",
      "Preparar apresentação para cliente",
      "Backup dos arquivos importantes"
    ],
    Quinta: [
      "Desenvolver animações e interações simples",
      "Reunião de alinhamento com desenvolvedores",
      "Analisar métricas de engajamento",
      "Aprimoramento de peças gráficas",
      "Pesquisar novas fontes e paletas de cores",
      "Experimentos com tipografia criativa",
      "Organizar agenda da semana seguinte"
    ],
    Sexta: [
      "Revisar tarefas concluídas da semana",
      "Finalizar entregas pendentes",
      "Sessão de feedback com o time",
      "Planejar ações de melhoria",
      "Atualizar blog com dicas de design",
      "Organizar área de trabalho física e digital",
      "Preparar relatório semanal"
    ]
  };

  // Select elements
  const navButtons = document.querySelectorAll('nav button');
  const taskList = document.getElementById('task-list');
  const dayTitle = document.getElementById('day-title');

  function renderTasks(day) {
    dayTitle.textContent = day;
    // Clear current tasks
    taskList.innerHTML = '';
    // Add fade effect
    taskList.classList.remove('fade');
    void taskList.offsetWidth;
    taskList.classList.add('fade');

    routines[day].forEach(task => {
      const li = document.createElement('li');
      li.textContent = task;
      taskList.appendChild(li);
    });
  }

  navButtons.forEach(button => {
    button.addEventListener('click', () => {
      // Remove active from all
      navButtons.forEach(btn => {
        btn.classList.remove('active');
        btn.removeAttribute('aria-current');
      });
      // Set clicked active
      button.classList.add('active');
      button.setAttribute('aria-current', 'true');
      renderTasks(button.dataset.day);
    });
  });

  // Initial load
  renderTasks('Segunda');
</script>
</body>
</html>

