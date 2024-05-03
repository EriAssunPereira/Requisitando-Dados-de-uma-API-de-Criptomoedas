# Requisitando-Dados-de-uma-API-de-Criptomoedas

Aprendendo a interagir com uma API de Criptomoedas usando JavaScript para exibir informações em uma página web. Vamos dividir isso em módulos para manter o código organizado e modular.

### Descrição do Projeto:
O projeto consiste em criar uma aplicação web que faz requisições a uma API de Criptomoedas para obter dados em tempo real, como preços, volumes de negociação e mudanças percentuais. Essas informações serão exibidas em uma interface web responsiva, permitindo que os usuários vejam as atualizações das criptomoedas de seu interesse.

### Módulos:
1. **Configuração da API (API Setup):**
   - Criação de uma conta na plataforma da API de Criptomoedas.
   - Obtenção de uma chave de API para autenticação nas requisições.

2. **Requisição de Dados (Data Request):**
   - Uso da Fetch API para fazer chamadas GET à API de Criptomoedas.
   - Tratamento da resposta da API e extração dos dados necessários.

3. **Interface do Usuário (User Interface):**
   - Desenvolvimento de uma página web com HTML e CSS.
   - Implementação de um design responsivo que se adapta a diferentes tamanhos de tela.

4. **Exibição de Dados (Data Display):**
   - Uso de JavaScript para manipular o DOM e exibir os dados da API na página web.
   - Atualização dinâmica da interface com as informações mais recentes.

5. **Gestão de Erros (Error Handling):**
   - Implementação de tratamento de erros para lidar com problemas na requisição ou na resposta da API.

### Exemplo Prático:
Aqui está um exemplo básico de como você pode começar a estruturar seu código em módulos:

```javascript
// apiConfig.js
export const apiKey = 'SUA_CHAVE_DE_API';

// dataRequest.js
export async function obterDadosCripto(url) {
  try {
    const resposta = await fetch(url, {
      headers: {
        'X-CMC_PRO_API_KEY': apiKey
      }
    });
    const dados = await resposta.json();
    return dados;
  } catch (erro) {
    console.error('Erro ao fazer a requisição:', erro);
  }
}

// userInterface.js
// Funções relacionadas à construção da interface do usuário

// dataDisplay.js
export function exibirDados(dados) {
  // Código para exibir os dados na página
}

// errorHandling.js
// Funções relacionadas ao tratamento de erros
```

Para usar esses módulos, você importará as funções necessárias nos arquivos onde elas serão utilizadas, mantendo a organização e a separação de responsabilidades.

Requisitar dados de uma API de Criptomoedas é um processo que envolve várias etapas, desde a configuração inicial até a exibição dos dados em uma interface. Aqui está um resumo detalhado do processo:

### 1. Escolha da API de Criptomoedas:
Primeiro, você precisa escolher uma API de Criptomoedas para usar. Existem várias opções disponíveis, como CoinMarketCap, CoinGecko, entre outras. Cada uma oferece diferentes conjuntos de dados e funcionalidades.

### 2. Registro e Obtenção de uma Chave API:
Para acessar a maioria das APIs de Criptomoedas, você precisará se registrar e obter uma chave API. Esta chave é usada para autenticar suas requisições e geralmente é passada no cabeçalho da requisição.

### 3. Entendimento da Documentação da API:
Antes de começar a codificar, é crucial entender a documentação da API. Isso inclui os endpoints disponíveis, os parâmetros que você pode enviar e o formato dos dados de resposta.

### 4. Realização de Requisições HTTP:
Usando JavaScript, você pode fazer requisições HTTP para a API usando a Fetch API ou bibliotecas como Axios. As requisições são feitas para endpoints específicos para obter os dados desejados.

### 5. Tratamento da Resposta:
Após fazer uma requisição, você receberá uma resposta que precisa ser tratada. Isso geralmente envolve converter a resposta de JSON para um objeto JavaScript que você pode usar.

### 6. Exibição dos Dados:
Os dados obtidos podem ser exibidos em uma página web. Você usará o DOM para criar elementos HTML dinamicamente e exibir os dados de forma legível.

### 7. Atualização e Sincronização de Dados:
Para manter os dados atualizados, você pode implementar um mecanismo para atualizar os dados periodicamente ou quando o usuário realizar alguma ação.

### 8. Tratamento de Erros:
É importante implementar um bom tratamento de erros para lidar com problemas como falhas na rede, respostas de erro da API, ou dados inválidos.

### 9. Segurança:
Garanta que sua chave API esteja segura e não exposta ao público. Além disso, implemente medidas para proteger sua aplicação contra ataques comuns, como injeção de SQL e Cross-Site Scripting (XSS).

### 10. Testes:
Teste sua aplicação para garantir que ela lida corretamente com as requisições e respostas da API, e que os dados são exibidos corretamente.

### Exemplo de Código:
Aqui está um exemplo simplificado de como você pode fazer uma requisição para uma API de Criptomoedas e exibir os dados:

```javascript
const apiKey = 'SUA_CHAVE_API';
const url = 'https://api.criptomoedas.com/v1/cotacoes';

async function obterCotacoes() {
  try {
    const resposta = await fetch(url, {
      headers: {
        'Authorization': `Bearer ${apiKey}`
      }
    });
    const dados = await resposta.json();
    exibirCotacoes(dados);
  } catch (erro) {
    console.error('Erro ao requisitar dados da API:', erro);
  }
}

function exibirCotacoes(dados) {
  dados.forEach(cripto => {
    console.log(`Nome: ${cripto.nome}, Preço: ${cripto.preco}`);
  });
}

obterCotacoes();
```

Este código é apenas um ponto de partida. Você precisará adaptá-lo conforme as especificações da API que você escolher usar. Lembre-se de que a manipulação de APIs é uma habilidade valiosa no desenvolvimento web e pode ser aplicada em muitos outros tipos de projetos⁴⁵.

https://github.com/bahcasac/DigitalOne
