# Python | Como instalar um script Python no Windows Services

Estudo sobre como instalar um script Python no Windows Services, ou seja, um agendador de tarefas (job scheduler) em Python que roda em segundo plano no sistema operacional.

## Sobre o projeto

Um **Windows Service** é um programa que roda em segundo plano no Windows, sem interface visível, podendo iniciar automaticamente junto com o sistema. Esse estudo mostra o passo a passo para transformar um script Python — no caso, um agendador de tarefas feito com a biblioteca `schedule` — em um serviço do Windows, usando o **NSSM (Non-Sucking Service Manager)**.

## Tecnologias utilizadas

- **Python** — linguagem do script principal
- **schedule** — biblioteca para agendamento de tarefas em Python
- **virtualenv** — ambiente virtual para isolar as dependências do projeto
- **NSSM** — ferramenta para transformar o script em serviço do Windows
- **PowerShell / DOS (modo administrador)** — execução dos comandos de instalação do serviço

## 1. Preparando o ambiente

### 1.1 Estrutura do projeto no Visual Studio Code

[![Estrutura Projeto](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/Estrutura_Projeto.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/Estrutura_Projeto.GIF)

### 1.2 Instalando bibliotecas

No exemplo abaixo foi instalada a biblioteca `schedule` pelo próprio terminal do Visual Studio Code.

[![Biblioteca Schedule](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/02_Biblioteca_Schedule.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/02_Biblioteca_Schedule.GIF)

### 1.3 Importando as bibliotecas

[![Importando Bibliotecas](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/03_ImportandoBibliotecas.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/03_ImportandoBibliotecas.GIF)

## 2. Construindo o script

### 2.1 Definindo funções

[![Definindo Funções](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/04_Definindo_Funcoes.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/04_Definindo_Funcoes.GIF)

### 2.2 Montando os schedulers

[![Montando Schedulers](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/05_Schedulando.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/05_Schedulando.GIF)

### 2.3 Determinando a condição de execução

[![Condição de Execução](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/06_Determina_Cond_Exec.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/06_Determina_Cond_Exec.GIF)

### 2.4 Execução automática de atividades

[![Execução de Jobs](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/08_Executando_Jobs.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/08_Executando_Jobs.GIF)

> Para interromper uma execução, utilizar `Ctrl + C`.

### 2.5 Criando o ambiente virtualenv

[![Criando VirtualEnv](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/07_Criando_VirtualEnv.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/07_Criando_VirtualEnv.GIF)

## 3. Publicando o script como serviço do Windows

### 3.1 Ativando o JobScheduler1

[![Ativar JobScheduler](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/09_Ativar_JobScheduler.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/09_Ativar_JobScheduler.GIF)

### 3.2 JobScheduler1 ativado

[![JobScheduler Ativado](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/10_Job_Ativado.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/10_Job_Ativado.GIF)

Para ativação do JobScheduler1, foi necessário executar o script abaixo no PowerShell.

[![Comando Shell](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/11_Comando_Shell.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/11_Comando_Shell.GIF)

### 3.3 Baixando o NSSM

[![Download NSSM](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/12_Download_NSSM.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/12_Download_NSSM.GIF)

**Sobre o NSSM:** o `NSSM.exe` refere-se ao *Non-Sucking Service Manager*, uma ferramenta de código aberto para Windows usada para criar e gerenciar serviços do Windows. Um serviço no Windows é um programa ou processo executado em segundo plano, geralmente sem interface de usuário visível, que pode ser configurado para iniciar automaticamente quando o sistema é iniciado.

O NSSM permite converter um aplicativo ou script em um serviço do Windows, o que é útil em várias situações — por exemplo, para executar uma tarefa em segundo plano, como um servidor web, um serviço de banco de dados ou qualquer outro aplicativo que precise rodar como serviço.

### 3.4 Instalando o serviço

Em seguida, executar o DOS como **administrador** e realizar a instalação do serviço.

[![Instalação do Serviço](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/13_Instalacao_Servi%C3%A7o.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/13_Instalacao_Servi%C3%A7o.GIF)

## 4. Verificação

### 4.1 Acessar Serviços e verificar o serviço JobScheduler1

[![Serviço JobScheduler](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/14_Servico_Job_Scheduler.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/14_Servico_Job_Scheduler.GIF)

### 4.2 Iniciar o serviço

[![Iniciar Serviço](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/15_Iniciar_Servico.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/15_Iniciar_Servico.GIF)

[![Serviço em Execução](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/16_Servico_EmExecucao.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/16_Servico_EmExecucao.GIF)

### 4.3 Logs do serviço

<!--
ATENÇÃO: a imagem original desta seção usava um link temporário do GitHub
(private-user-images...) que já expirou e não carrega mais. Suba o print dos
logs para a pasta /img do repositório (ex: img/17_Logs_Servico.GIF) e troque
o link abaixo pelo caminho definitivo, seguindo o mesmo padrão das imagens acima.
-->

[![Logs do Serviço](https://github.com/joycequoos/Python_Windows_Services/raw/main/img/17_Logs_Servico.GIF)](https://github.com/joycequoos/Python_Windows_Services/blob/main/img/17_Logs_Servico.GIF)
