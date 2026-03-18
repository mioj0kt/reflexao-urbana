# 👁️ Reflexão Urbana

> *Um experimento de intervenção urbana, tecnologia e filosofia minimalista.*

<p align="center">
  <img src="cartaz.jpg" width="400">
</p>

## 🏙️ Sobre o Projeto

O **Reflexão Urbana** é uma instalação digital pensada para interagir com os transeuntes da cidade. Através de cartazes físicos espalhados pelo ambiente urbano com um QR Code, as pessoas são convidadas a pausar a correria do dia a dia e escanear o código.

Ao acessar, o usuário recebe instantaneamente uma frase filosófica, curta e profunda, gerada por Inteligência Artificial. A cada *refresh* da página, uma nova reflexão aparece. Sem botões, sem distrações. Apenas o vazio e uma mensagem.

## ⚙️ Como Funciona (Por Baixo dos Panos)

Para garantir que a pessoa na rua não desista de ler a frase por lentidão na internet 3G/4G, o sistema foi desenhado com uma arquitetura de **Estoque Local**:

1. **Carregamento Zero-Delay:** A página usa o `localStorage` do navegador para guardar frases previamente geradas. Assim que o QR Code é escaneado, a frase aparece instantaneamente.
2. **Abastecimento Fantasma:** Enquanto o usuário lê a reflexão, o JavaScript faz uma requisição silenciosa no fundo (em background) para a API da Groq (Llama 3), buscando novas frases e guardando no estoque para o próximo acesso.
3. **Tanque de Reserva (Offline):** Se a internet do usuário cair ou a API falhar, o sistema assume automaticamente, exibindo frases de um banco de dados fixo no próprio código (Modo Offline).

## 🛠️ Tecnologias Utilizadas

* **Frontend:** HTML5, CSS3, JavaScript Vanilla (Puro).
* **Inteligência Artificial:** [Groq API](https://groq.com/) rodando o modelo `llama-3.1-8b-instant`.
* **Hospedagem:** GitHub Pages.

## 🚀 Como Rodar Localmente

Se você quiser clonar e testar o oráculo na sua máquina:

1. Clone o repositório:
   ```bash
   git clone https://github.com/mioj0kt/reflexao-urbana.git
