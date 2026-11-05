# Especificação do Projeto — RedirecionaAI

## 1. Project Charter

### 1.1. Identificação do projeto

| Informação | Descrição |
|---|---|
| Nome | RedirecionaAI |
| Slogan | Sua redação no caminho da evolução. |
| Categoria | Aplicação web educacional |
| Público-alvo | Estudantes que se preparam para o ENEM |
| Objetivo principal | Auxiliar estudantes na avaliação e melhoria de suas redações |

### 1.2. Problema identificado

Estudantes que se preparam para o ENEM frequentemente enfrentam dificuldades para obter correções frequentes e feedbacks individualizados sobre suas redações.

A ausência desse acompanhamento pode dificultar a identificação de erros, a compreensão das competências avaliadas e o monitoramento da evolução da escrita.

### 1.3. Proposta de valor

O RedirecionaAI propõe uma plataforma web capaz de avaliar redações por meio de técnicas de Processamento de Linguagem Natural e um modelo próprio de Machine Learning supervisionado.

A aplicação deverá apresentar estimativas de desempenho nas cinco competências do ENEM, sugestões predefinidas de melhoria e um histórico que permita acompanhar a evolução do estudante.

### 1.4. Escopo da primeira versão

**Dentro do escopo:**

- Cadastro e autenticação de estudantes.
- Inserção de redações por meio de texto digitado ou colado.
- Avaliação automatizada utilizando um modelo próprio de Machine Learning.
- Estimativa de pontuação nas cinco competências do ENEM.
- Cálculo da pontuação total estimada.
- Apresentação de sugestões predefinidas de melhoria.
- Armazenamento das redações e avaliações.
- Consulta ao histórico de avaliações.
- Indicadores básicos de desempenho.

A avaliação das cinco competências depende da disponibilidade de uma base de dados adequada e da validação do modelo para cada competência.

**Fora do escopo:**

- Avaliação de provas ou exames diferentes do ENEM.
- Integração com APIs de modelos de linguagem generativa.
- Correção de redações manuscritas por fotografias.
- Correção realizada por professores dentro da plataforma.
- Geração automática de redações completas.
- Cursos, videoaulas e conteúdos educacionais extensos.
- Aplicativos nativos para dispositivos móveis.
- Assinaturas e funcionalidades de pagamento.
- Rankings e competições entre estudantes.

### 1.5. Restrições e dependências

O desenvolvimento do modelo depende da identificação de uma base de dados pública ou devidamente autorizada, com redações avaliadas e pontuações disponíveis por competência.

Antes do treinamento, será necessário analisar:

- Licença e permissão de uso dos dados.
- Quantidade e qualidade das redações.
- Diversidade dos textos.
- Disponibilidade das pontuações individuais das cinco competências.
- Consistência das avaliações presentes na base.

Caso a base inicial não seja suficiente, será necessário buscar outra fonte ou adaptar a preparação dos dados antes de implementar o modelo definitivo.

---

## 2. Histórias de usuário

As histórias de usuário descrevem as principais funcionalidades da plataforma a partir da perspectiva do estudante.

### US01 — Cadastro

Como estudante, quero criar uma conta na plataforma, para acessar as funcionalidades e manter meus dados e redações associados ao meu perfil.

### US02 — Login

Como estudante cadastrado, quero entrar na plataforma utilizando minhas credenciais, para acessar minhas redações, avaliações e histórico.

### US03 — Envio de redação

Como estudante, quero digitar ou colar uma redação para avaliação, para receber uma estimativa do meu desempenho nas cinco competências do ENEM.

### US04 — Consulta de avaliação

Como estudante, quero visualizar a pontuação estimada de cada competência e a nota total, para identificar meus pontos fortes e os aspectos que precisam melhorar.

### US05 — Orientações de melhoria

Como estudante, quero receber sugestões de melhoria com base nos resultados da avaliação, para saber quais aspectos da minha escrita preciso desenvolver.

### US06 — Acompanhamento de desempenho

Como estudante, quero consultar o histórico das minhas redações e avaliações, para acompanhar minha evolução ao longo do tempo.

---

## 3. Principal caso de uso

### UC01 — Avaliar redação

**Ator principal:** Estudante autenticado.

**Objetivo:** Avaliar uma redação e apresentar estimativas de desempenho nas competências do ENEM.

**Pré-condições:**

- O estudante deve possuir uma conta cadastrada.
- O estudante deve estar autenticado.
- O serviço de avaliação deve estar disponível.

### Fluxo principal

1. O estudante acessa a plataforma e realiza o login.
2. O sistema apresenta a opção de enviar uma redação.
3. O estudante digita ou cola o texto no campo disponibilizado.
4. O sistema valida o conteúdo inserido.
5. O sistema encaminha a redação ao serviço de avaliação desenvolvido em Python.
6. O serviço realiza o processamento textual utilizando técnicas de PLN.
7. O modelo de Machine Learning processa as características extraídas e retorna as pontuações estimadas.
8. O sistema recebe os resultados e calcula a pontuação total.
9. O sistema seleciona sugestões predefinidas de melhoria com base nos resultados.
10. A redação e sua avaliação são armazenadas no banco de dados.
11. O estudante visualiza os resultados e pode consultá-los posteriormente no histórico.

### Tratamento de erros

| Situação | Comportamento esperado |
|---|---|
| Texto vazio | O sistema solicita o preenchimento do campo. |
| Texto insuficiente | O sistema informa que a redação precisa de mais conteúdo. |
| Falha de comunicação com a API | O sistema realiza tentativas automáticas limitadas e, se necessário, permite uma nova tentativa manual. |
| Erro durante a avaliação | O sistema informa que não foi possível concluir o processamento e não apresenta uma pontuação inválida. |
| Falha ao salvar resultados | O sistema informa que os dados não foram armazenados e permite tentar novamente, evitando registros duplicados. |
| Usuário não autenticado | O sistema solicita que o estudante realize o login. |
| Acesso a dados de outro estudante | O sistema nega o acesso e impede a consulta ou alteração dos dados. |

---

## 4. Critérios de aceitação e Definition of Done

Os critérios de aceitação e a Definition of Done estão detalhados em [Requisitos do sistema](requisitos.md).

A arquitetura e as tecnologias utilizadas estão descritas em [Arquitetura do sistema](arquitetura.md).

---

## 5. Considerações finais

O RedirecionaAI busca utilizar recursos de Inteligência Artificial para tornar o acompanhamento da produção textual mais acessível aos estudantes.

A primeira versão prioriza as funcionalidades essenciais de avaliação, orientação e acompanhamento, mantendo um escopo compatível com a proposta acadêmica e com a complexidade técnica do desenvolvimento.

A implementação do modelo dependerá da análise e validação de uma base de dados adequada, garantindo que os resultados sejam apresentados como estimativas educacionais, e não como correções oficiais.