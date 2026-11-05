# Requisitos do Sistema — RedirecionaAI

## 1. Requisitos funcionais

Os requisitos funcionais descrevem as operações e funcionalidades que o sistema deverá disponibilizar aos estudantes.

| ID | Requisito |
|---|---|
| RF01 | O sistema deverá permitir o cadastro de estudantes. |
| RF02 | O sistema deverá permitir que estudantes cadastrados realizem login e logout. |
| RF03 | O sistema deverá disponibilizar um campo para digitar ou colar o texto da redação. |
| RF04 | O sistema deverá encaminhar redações válidas ao serviço responsável pela avaliação automatizada. |
| RF05 | O sistema deverá apresentar pontuações estimadas para as cinco competências do ENEM, desde que o modelo tenha sido validado para todas elas. |
| RF06 | O sistema deverá calcular e apresentar a pontuação total estimada da redação. |
| RF07 | O sistema deverá apresentar sugestões predefinidas de melhoria com base nos resultados da avaliação. |
| RF08 | O sistema deverá armazenar as redações e suas respectivas avaliações vinculadas ao estudante. |
| RF09 | O sistema deverá permitir que o estudante consulte seu histórico de redações e avaliações. |
| RF10 | O sistema deverá apresentar indicadores básicos de desempenho do estudante. |
| RF11 | O sistema deverá validar o texto enviado e informar quando estiver vazio ou não possuir conteúdo suficiente para avaliação. |

## 2. Requisitos não funcionais

Os requisitos não funcionais estabelecem características de qualidade, segurança e tecnologias que deverão ser consideradas durante o desenvolvimento.

| ID | Requisito |
|---|---|
| RNF01 | O sistema deverá proteger os dados dos estudantes por meio de autenticação e controle de acesso. |
| RNF02 | A interface deverá ser responsiva, permitindo utilização em computadores e dispositivos móveis. |
| RNF03 | Os resultados das avaliações deverão ser apresentados de maneira clara e organizada. |
| RNF04 | A aplicação web deverá ser desenvolvida utilizando Ruby on Rails, enquanto o componente de Machine Learning deverá utilizar Python. |
| RNF05 | O banco de dados da primeira versão deverá utilizar SQLite. |
| RNF06 | Cada estudante deverá possuir acesso exclusivo às próprias redações, avaliações e informações de histórico. |
| RNF07 | O modelo de Machine Learning deverá ser avaliado utilizando dados separados daqueles utilizados durante o treinamento, com métricas apropriadas para cada uma das cinco competências. |

## 3. Critérios de aceitação

Os critérios de aceitação definem as condições necessárias para considerar as funcionalidades implementadas corretamente.

### 3.1. Cadastro e autenticação

- O cadastro deverá funcionar quando os dados obrigatórios forem válidos.
- O sistema deverá apresentar mensagens compreensíveis quando houver informações inválidas.
- O login deverá permitir acesso com credenciais válidas.
- Credenciais incorretas deverão impedir o acesso.

### 3.2. Envio de redação

- O estudante deverá conseguir digitar ou colar o texto no campo de redação.
- O sistema deverá rejeitar textos vazios.
- O sistema deverá informar quando o texto for insuficiente para avaliação.
- Apenas redações que passarem pela validação deverão ser encaminhadas ao serviço de avaliação.

### 3.3. Avaliação automatizada

- A aplicação Rails deverá conseguir encaminhar o texto ao serviço Python.
- O sistema somente deverá apresentar resultados quando receber uma resposta válida.
- O modelo deverá fornecer estimativas para as cinco competências, desde que tenha sido validado para todas elas.
- A pontuação total deverá corresponder à soma das pontuações estimadas das competências.
- As sugestões de melhoria deverão ser selecionadas conforme os resultados obtidos.

### 3.4. Histórico e acompanhamento

- As redações e avaliações deverão ser armazenadas e vinculadas ao estudante responsável.
- O estudante deverá conseguir consultar suas avaliações anteriores.
- Os indicadores básicos deverão utilizar os dados de desempenho disponíveis no histórico.

### 3.5. Segurança e tratamento de erros

- Um estudante não poderá consultar ou modificar os dados de outro.
- Falhas de comunicação com o serviço de avaliação deverão ser comunicadas.
- O sistema deverá realizar tentativas automáticas limitadas e permitir nova tentativa manual quando necessário.
- Resultados inválidos ou incompletos não deverão ser apresentados como avaliações concluídas.

## 4. Definition of Done (DoD)

Uma funcionalidade será considerada concluída quando atender às seguintes condições:

- [ ] Código da funcionalidade implementado.
- [ ] Requisitos relacionados atendidos.
- [ ] Testes correspondentes executados e aprovados.
- [ ] Erros identificados durante os testes corrigidos.
- [ ] Integração com os componentes necessários funcionando.
- [ ] Documentação técnica atualizada.
- [ ] Código versionado no GitHub.
- [ ] Funcionalidade revisada e validada.

### Definition of Done específica para Machine Learning

Além das condições gerais, o componente de avaliação deverá atender aos seguintes pontos:

- [ ] Base de dados analisada e com permissão de uso adequada.
- [ ] Dados preparados para o treinamento.
- [ ] Modelo avaliado com dados que não participaram do treinamento.
- [ ] Métricas de desempenho calculadas para cada competência.
- [ ] Resultados dos testes documentados.
- [ ] Limitações conhecidas do modelo registradas.

---

## 5. Observações

Os requisitos poderão ser refinados durante o desenvolvimento, desde que as alterações sejam documentadas e mantenham coerência com o escopo definido para a primeira versão.

A escolha do algoritmo de Machine Learning será realizada após a análise da base de dados, considerando a qualidade dos resultados e a viabilidade de implementação.