# 📲 Automação de Cobrança via WhatsApp

## 📖 Sobre o projeto

Este projeto automatiza o envio de mensagens de cobrança através do *WhatsApp Web*, utilizando uma planilha Excel como base de clientes.
O sistema identifica automaticamente quais clientes possuem status *pendente*, gera mensagens personalizadas, realiza o envio e atualiza a planilha conforme o resultado da operação.
Além disso, foram implementados intervalos aleatórios e pausas programadas para tornar o fluxo de envio mais natural.
---
## ✨ Funcionalidades

* 📄 Leitura automática de planilhas Excel (`.xlsm`)
* 📲 Envio de mensagens pelo WhatsApp Web
* 💬 Mensagens personalizadas com múltiplos templates
* 🎲 Escolha aleatória do texto enviado
* ⏱️ Intervalos aleatórios entre mensagens
* ☕ Pausas programadas após determinado número de envios
* 🔍 Identificação de números sem WhatsApp
* 📝 Atualização automática do status dos clientes
* 📊 Geração da planilha final atualizada
---
## 🛠 Tecnologias

| Tecnologia | Utilização                         |
| ---------- | ---------------------------------- |
| Python     | Linguagem principal                |
| Pandas     | Leitura e manipulação de planilhas |
| PyWhatKit  | Envio de mensagens pelo WhatsApp   |
| PyAutoGUI  | Reconhecimento de imagem           |
| OpenPyXL   | Manipulação de arquivos Excel      |
---
## 📂 Estrutura do projeto

```text automacao-cobranca/
│
├── cobranca.py
├── clientes_base.xlsm
├── numero_invalido.png
│
├── mes_cobranca/
│   └── clientes_30_junho.xlsx
│
└── README.md
```
---
## 📋 Estrutura da planilha

A aba *cobranca* deve conter as seguintes colunas:
| Campo    | Obrigatório |
| -------- | :---------: |
| nome     |      ✅      |
| telefone |      ✅      |
| valor    |      ✅      |
| data     |      ✅      |
| status   |      ✅      |

Exemplo:

| nome | telefone      | valor  | data       | status   |
| ---- | ------------- | ------ | ---------- | -------- |
| João | 5591999999999 | 250,00 | 30/06/2025 | pendente |
---
## ⚙️ Configuração

No início do código podem ser alterados os parâmetros de envio:

```python
MAX_ENVIOS_POR_EXECUCAO = 40

PAUSA_A_CADA = 15

PAUSA_LONGA_MIN = 180
PAUSA_LONGA_MAX = 300

INTERVALO_MIN = 25
INTERVALO_MAX = 50
```

Essas configurações controlam:

* quantidade máxima de mensagens por execução;
* tempo entre mensagens;
* pausas periódicas;
* limite de segurança para evitar muitos envios consecutivos.
---
## 📊 Fluxo do processo

```text
Ler planilha
      │
      ▼
Selecionar clientes pendentes
      │
      ▼
Gerar mensagem personalizada
      │
      ▼
Abrir WhatsApp Web
      │
      ▼
Enviar mensagem
      │
      ▼
Verificar número inválido
      │
      ▼
Atualizar status
      │
      ▼
Salvar nova planilha
```
---
## 📌 Status utilizados

| Status       | Descrição                          |
| ------------ | ---------------------------------- |
| pendente     | Cliente ainda não recebeu mensagem |
| enviado      | Mensagem enviada com sucesso       |
| erro         | Erro durante o envio               |
| sem_whatsapp | Número não encontrado no WhatsApp  |
---
## 🚀 Como executar
### 1. Clone o projeto
```bash
git clone https://github.com/SEU-USUARIO/automacao-cobranca.git
```
### 2. Entre na pasta
```bash
cd automacao-cobranca
```
### 3. Instale as dependências
```bash
pip install pandas pywhatkit pyautogui openpyxl
```
### 4. Execute
```bash
python cobranca.py
```
---
## 📷 Demonstração
Você pode adicionar um GIF mostrando o envio automático.
Exemplo:
```markdown
![Demonstração](assets/demo.gif)
```
ou
```markdown
<p align="center">
<img src="assets/demo.gif" width="900">
</p>
```
---
## 🚧 Melhorias futuras

* Interface gráfica
* Dashboard de acompanhamento
* Logs de execução
* Integração com banco de dados
* Arquivo `.env` para configurações
* Agendamento automático de execuções
* Envio de boletos em PDF
* Integração com API oficial do WhatsApp
---
## ⚠️ Aviso

Este projeto foi desenvolvido para automatizar processos internos de cobrança.
Ao utilizá-lo, certifique-se de cumprir as políticas do WhatsApp e a legislação aplicável, incluindo regras de privacidade e proteção de dados.
---

## 👨‍💻 Autor

joabson_von.otowicz

Desenvolvido com ❤️ em Python para automação de processos administrativos.
---
⭐ Se este projeto foi útil para você, considere deixar uma estrela no repositório!

