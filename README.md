1. Foi desenvolvido um projeto com pipeline simples utilizando Continuous Integration e a ferramenta GitHub Actions.

2. O objetivo do pipeline criado é executar uma mensagem de texto, mostrando que o código foi executado com sucesso.

3. Estrutura do projeto: .github/workflows/ci.yml, README.md

4. Explicação do WorkFlow

    O ci.yml é o arquivo central da pipeline.
  
    name: Define o nome do workflow.
  
    on: [push] - Define o gatilho que é disparado quando alguém envia um "push" para o repositório.
  
    jobs: Define as tarefas que serão executadas.
  
        first-job: É o identificador único do trabalho que será executado.
  
        runs-on: ubuntu-latest - Define que seu job (tarefa) será executado em uma máquina virtual Linux, mantida pelo GitHub, usando a versão mais recente e estável do Ubuntu.
  
    steps - Representa a sequência de ações dentro do job.
  
        name: Print message - Define um nome personalizado para cada execução de fluxo de trabalho.
  
        run: echo "Pipeline executado com sucesso!" - O comando que exibe uma mensagem no console, confirmando que o pipeline chegou até o fim.

5. Fluxo do Pipeline

    Push no GitHub: O usuário envia alterações para o repositório.
  
    Execução do pipeline: O GitHub detecta o arquivo em .github/workflows/ e inicia o first-job.
  
    Execução do comando: A máquina virtual Ubuntu executa o comando echo.
  
    Exibição do resultado: A mensagem de sucesso é registrada nos logs do GitHub Actions.

6. Quando a pipeline termina de ser executada, o GitHub Actions fornece um log detalhado. Se rodar o arquivo sem erros, um ícone de "check" aparecerá ao lado do commit. Caso ocorra algum erro no script ou na configuração, um ícone de erro indicará que a integração falhou, permitindo assim, uma correção rápida.
