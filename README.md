# ⚡ STREET.LAB - Streetwear E-Commerce

Um ecossistema completo de e-commerce focado na cultura streetwear, desenvolvido com uma arquitetura moderna e visual minimalista/dark. O projeto engloba desde a experiência de navegação e checkout do cliente até um painel administrativo completo para controle de estoque, criação de cupons e análise de métricas financeiras.

## 🚀 Tecnologias Utilizadas

### Frontend
*   **React.js**: Biblioteca para construção da interface baseada em componentes.
*   **Tailwind CSS**: Framework utilitário para estilização rápida com foco na estética urbana.
*   **Vite**: Ferramenta de build ultra-rápida para o ambiente de desenvolvimento.

### Backend
*   **Node.js & Express**: Ambiente de execução e framework para construção da API REST.
*   **Cors**: Middleware para permitir a comunicação segura entre o Frontend e o Backend.

### Infraestrutura
*   **Docker & Docker Compose**: Empacotamento da aplicação em ambientes isolados para Frontend e Backend.
*   **Kubernetes**: Estrutura pronta para escalabilidade do ambiente em produção.

---

## 🛠️ Arquitetura e Explicação do Código

O projeto está dividido em duas partes principais que se comunicam através de requisições HTTP (API REST):

### 1. Backend (`/backend`)
O servidor centraliza todas as regras de negócio da loja e simula um banco de dados persistente em memória (arrays), expondo os seguintes endpoints:

*   **`GET /api/loja/produtos` e `/api/loja/cupom-vigente`**: Fornecem ao cliente os produtos disponíveis e os dados do cupom promocional configurado.
*   **`POST /api/loja/checkout`**: Recebe os dados obrigatórios do comprador (Nome, CPF, CEP, Telefone, E-mail) e valida o pedido.
*   **`POST /api/adm/estoque` e `/api/adm/categorias`**: Permitem ao administrador cadastrar novas peças de roupa e criar divisões no catálogo (como *Inverno*, *Moletons*, *Calças*).
*   **`GET /api/adm/dashboard`**: Processa o histórico de pedidos e calcula em tempo real o faturamento acumulado por dia, semana e mês.

### 2. Frontend (`/frontend`)
A interface foi projetada usando o conceito de *Single Page Application* (SPA), onde o estado global gerencia se o usuário está visualizando a **Loja** ou o **Painel ADM**.

*   **Componentização**: Formulários, cards de produtos e tabelas foram estruturados de forma limpa.
*   **Estilização Streetwear**: Utiliza a paleta de cores `neutral-950` para o fundo escuro, contrastando com tipografia em caixa alta e detalhes em `yellow-500`, gerando o aspecto visual marcante de marcas urbanas.
*   **Responsividade**: Totalmente adaptado para navegação e gerenciamento via dispositivos móveis.

---

## 📦 Como Executar o Projeto

Certifique-se de ter o **Docker Desktop** instalado na sua máquina. Na raiz do projeto, execute o comando:

```bash
docker-compose up --build
