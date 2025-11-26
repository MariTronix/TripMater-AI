# ✈️ TripMaster AI

> **Um Planejador de Viagens Autônomo baseado em Sistema Multiagente (Microsoft AutoGen).**

![Status](https://img.shields.io/badge/Status-Concluído-success)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![AI Framework](https://img.shields.io/badge/Framework-Microsoft_AutoGen-purple)

## 📖 Sobre o Projeto

A **TripMaster AI** não é apenas um chatbot de viagens. É um sistema orquestrado onde 10 agentes de Inteligência Artificial especializados (com personalidades e funções distintas) colaboram para planejar, validar e apresentar um roteiro de viagem completo a partir de um único pedido em linguagem natural.

Diferente de IAs genéricas, o sistema possui **freios e contrapesos**: um agente financeiro "audita" as sugestões do agente de lazer, garantindo que o sonho da viagem caiba no bolso do usuário.

**TRELLO:** https://trello.com/b/HDum3pjR/projeto-tripmater

---

## 🤖 O Time de Agentes

O sistema utiliza a arquitetura `RoundRobinGroupChat` onde cada agente contribui sequencialmente:

1.  **🕵️ Agente de Perfil (O Psicólogo):** Identifica o "DNA da Viagem" (Negócios, Aventura, Eventos ou Lazer) e define as restrições técnicas.
2.  **🌍 Agente de Destino (O Geógrafo):** Valida a viabilidade geográfica e climática (sazonalidade), evitando furacões ou monções.
3.  **✈️ Agente de Transporte (O Logístico):** Define rotas eficientes (Aéreo/Terrestre) e transporte de equipamentos específicos.
4.  **🏨 Agente de Hospedagem (O Concierge):** Sugere acomodações com *guardrails* rígidos: ele fornece opções, mas não decide o custo final.
5.  **💰 Agente Financeiro (O Auditor - MVP):** Aplica o **"Cálculo de Sobrevivência"**. Se o valor diário restante para alimentação for insuficiente, ele VETA a viagem.
6.  **🍽️ Agente de Experiências (O Insider Local):** Curador de cultura e gastronomia. Foge das armadilhas pega-turista e sugere "planos B" para dias de chuva.
7.  **🗓️ Agente de Itinerário (O Arquiteto):** Usa lógica de "Tetris" para encaixar lazer nos horários vagos entre reuniões ou voos.
8.  **🎫 Agente de Eventos Globais (O Hype Maker):** Monitora shows e campeonatos esportivos coincidentes com a data.
9.  **🛡️ Agente de Risco (O Segurança):** Analisa vistos, vacinas e riscos físicos.
10. **📢 Agente de Apresentação (A Editora):** Compila tudo em uma proposta comercial estruturada e adapta o tom de voz ao cliente.

---

## ⚙️ Funcionalidades e Diferenciais

* **Validação Financeira Real:** O sistema recusa roteiros financeiramente inviáveis (ex: Disney com orçamento baixo).
* **Adaptação de Persona:** O tom da resposta muda de "Formal/Executivo" para "Vibrante/Aventureiro" dependendo do perfil detectado.
* **Guardrails de Prompt:** Regras rígidas impedem que agentes alucinem ou tomem decisões fora de sua competência (ex: Agente de Hotel tentando decidir o destino).

---

## 🚀 Como Executar

### Pré-requisitos
* Python 3.10+
* Chave de API da OpenAI ou Google Gemini (configurado via `OpenAIChatCompletionClient`).

### Instalação

1.  Clone o repositório:
    ```bash
    git clone [https://github.com/MariTronix/TripMater-AI.git](https://github.com/MariTronix/TripMater-AI.git)
    cd TripMater-AI
    ```

2.  Instale as dependências:
    ```bash
    pip install pyautogen
    ```

3.  Configure sua API Key (no código ou variáveis de ambiente):
    ```python
    # Exemplo de configuração no arquivo principal
    "config": {
        "model": "gemini-2.0-flash",
        "api_key": [SUA_CHAVE_AQUI]"
      }
    ```

4.  Iniciar o Servidor:
    ```bash
    autogenstudio ui --port 8081
    ```

    ou
    
    ```bash
    python -m autogenstudio.cli ui --port 8081
    ```
    
    
6.  Acessar:
    ```bash
    http://localhost:8081
    ```
---

## 🧪 Cenários de Teste (Exemplos)

Para validar o sistema, utilizamos inputs de estresse:

* **Cenário Sucesso (Equilibrado):** *"Viagem romântica para Lisboa, 7 dias, foco em história e vinhos. Orçamento R$ 30k."* -> **Aprovado e Roteirizado.**
* **Cenário Falha (Financeiro):** *"Paris em Junho com R$ 8.000 para duas pessoas."* -> **Vetado pelo Agente Financeiro (Alerta de Inviabilidade).**

---

## 🔮 Melhorias Futuras

* **Arquitetura Dinâmica:** Migrar de `RoundRobin` para `SelectorGroupChat` para economizar tokens, ativando o Agente de Eventos apenas quando necessário.
* **Inputs Estruturados:** Implementar formulário inicial para garantir dados base (Destino/Budget/Data).
* **Integração de API:** Conectar com Skyscanner/Booking para preços em tempo real.

---

## ## 🤝 Colaboradores

  Este projeto é o resultado do trabalho e da dedicação de uma equipe incrível. Conheça quem fez o **TripMaster** acontecer:

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/MariTronix">
        <img src="https://github.com/MariTronix.png" width="100px;" alt="Foto de Mariana Mendes no GitHub"/>
        <br />
        <sub><b>Mariana Mendes</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/luanrichardsz">
        <img src="http://github.com/luanrichardsz.png" width="100px;" alt="Foto de Luan Richard no GitHub"/>
        <br />
        <sub><b>Luan Richard</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/KauaOliveira17">
        <img src="https://github.com/KauaOliveira17.png" width="100px;" alt="Foto de Kauã Felipe no GitHub"/>
        <br />
        <sub><b>Kauã Felipe</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/Emmanuel1421">
        <img src="https://github.com/Emmanuel1421.png" width="100px;" alt="Foto de Emmanuel Guerra no GitHub"/>
        <br />
        <sub><b>Emmanuel Guerra</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/Souz4Ingrid">
        <img src="https://github.com/Souz4Ingrid.png" width="100px;" alt="Foto de Indrig Souza no GitHub"/>
        <br />
        <sub><b>Indrig Souza</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/rhodrigo081">
        <img src="https://github.com/rhodrigo081.png" width="100px;" alt="Foto de Rhodrigo Rodrigues no GitHub"/>
        <br />
        <sub><b>Rhodrigo Rodrigues</b></sub>
      </a>
    </td>
  </tr>
</table>

---
*Projeto desenvolvido para fins acadêmicos e de portfólio em Agentes Autônomos.*
