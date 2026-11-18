# SPOMASI: Meio Ambiente, Sustentabilidade e Informática
Material de estudo gerado a partir das Aulas 1 a 12 (Prof. Celso Gonsalez Saes, IFSP).

**Avaliação da disciplina (Aula 1):** Média Final = ((P1×0,8 + T1×0,8)/2) + MA×0,2. Quem tiver média final ≥ 4,0 e < 6,0 faz o IFA, desde que tenha frequência mínima de 75%.

---

# PARTE 1: RESUMO DO CONTEÚDO

## Aula 1: Introdução à IHC

**IHC (Interação Humano-Computador, em inglês HCI):** área que estuda o projeto, o desenvolvimento, a avaliação e o uso de sistemas computacionais interativos, com foco na relação entre pessoas e tecnologia. É multidisciplinar (Computação, Design, Psicologia, Ergonomia, Comunicação, Ciências cognitivas, Acessibilidade, Sociologia etc.).

- IHC não é "fazer uma tela bonita". Um app visualmente simples, com funções claras, confirmação antes de operações críticas e mensagens de erro compreensíveis, pode ter melhor IHC que um app sofisticado com menus escondidos.
- Exemplos de IHC bem resolvida: **Pix** (poucos passos, chaves simples como CPF/e-mail/celular, feedback imediato, botão visível na primeira tela) e **Spotify** (3 opções na barra inferior, rolagem infinita, miniplayer).
- **Usuário:** quem usa o sistema para atingir um objetivo. Usuários diferem em idade, experiência tecnológica, conhecimento do domínio, contexto, dispositivo, limitações e ambiente. O sistema não deve presumir que todos sabem o mesmo.
- **Usabilidade:** capacidade de o sistema ser usado para atingir objetivos de maneira adequada em um contexto de uso. Perguntas de avaliação: é fácil aprender? É fácil achar as funções? O usuário conclui a tarefa? Quantos erros? Ajuda a se recuperar? Exige memorizar muito?
- **Pilares da usabilidade:** facilidade de aprendizado, eficiência, memorabilidade, baixo índice de erros, satisfação.
- **UX (User Experience):** conceito mais amplo que a usabilidade. Inclui sentimentos, percepções (confiança, segurança percebida, frustração, previsibilidade, controle) e a jornada completa do usuário. Usabilidade é um atributo de qualidade de uma tela ou sistema; UX é a experiência total.
- Exemplo do terminal de estacionamento: se o ticket é abandonado na máquina, o problema pode estar no projeto da interação, não no usuário.

**Interface x Interação**

| Interface | Interação |
|---|---|
| Meio de contato (ponto de comunicação) | Processo de comunicação |
| Elementos apresentados ao usuário: botões, formulários, menus, ícones | Sequência de ações: preenchimento, navegação, seleção de comandos, feedback |

Tipos de interface: gráfica (UI), de hardware (cabos, USB), de programação (contratos entre partes de código) e humana (ex.: volante).

**Objetivos da IHC:** eficiência, eficácia, facilidade de aprendizagem (consistência ajuda), prevenção de erros (ex.: "Deseja realmente excluir?"), recuperação de erros e acessibilidade. A acessibilidade deve entrar no projeto desde as etapas iniciais.

---

## Aula 2: Paradigmas de Interação

**Paradigma de interação:** forma predominante de organizar a comunicação entre usuário e sistema. Define como o usuário envia comandos, como o sistema apresenta informações, quais dispositivos são usados, que conhecimento se exige, como é o feedback e quais sentidos participam.

Os paradigmas **coexistem** e não se substituem. Cada um é melhor em uma situação (o teclado físico ainda é mais rápido para textos longos; o toque é bom para navegação casual; a IA funciona como camada extra).

**Evolução:** processamento em lote → linha de comando → interfaces gráficas → Web → dispositivos móveis → toque → voz/gestos → RV/RA → interfaces conversacionais → IA multimodal. A tendência é o computador se adaptar às formas humanas de comunicação.

- **Processamento em lote (batch):** o usuário prepara instruções e dados, o computador executa depois. Não há interação contínua, e a distância entre ação e resposta é grande.
- **CLI (Command-Line Interface):** comandos textuais (ls, pwd, mkdir, cd, rm).
  - Vantagens: eficiência para experientes, baixo consumo gráfico, automação, uso remoto, scripts, precisão.
  - Desvantagens: curva de aprendizagem, memorizar comandos, erros de sintaxe, pouca descoberta visual, comandos destrutivos rápidos.
  - Ainda relevante em Linux, servidores, redes, Docker, Git, nuvem, segurança, DevOps.
- **GUI (Graphical User Interface):** janelas, ícones, menus, ponteiro, botões. O modelo **WIMP** significa Windows, Icons, Menus, Pointer. Traz a **manipulação direta** (arrastar arquivo, redimensionar janela), com feedback imediato, ações compreensíveis, possibilidade de desfazer e representação visual consistente.
- **Web:** navegador como plataforma. Trouxe hiperlinks, navegação não linear, formulários, buscas e acesso multiplataforma. O hipertexto cria problemas de IHC: onde estou, de onde vim, para onde posso ir. Daí a importância de menus, breadcrumbs, busca, hierarquia visual e arquitetura da informação.
- **Dispositivos móveis:** mobilidade, telas pequenas, sensores (GPS, câmera, microfone, acelerômetro, giroscópio), notificações e interação contextual. **Interfaces responsivas** adaptam a apresentação ao espaço disponível, em vez de só encolher a versão desktop.
- **Toque:** manipulação direta (dedo → objeto). Gestos: tap (selecionar), double tap (ampliar/ativar), long press (opções adicionais), swipe (navegar), drag (mover), pinch (reduzir), spread (ampliar).
- **Voz:** fala → captura → reconhecimento → interpretação → execução. Vantagens: mãos livres, acessibilidade. Limitações: ruído, reconhecimento incorreto, sotaques, privacidade, dificuldade de mostrar muita informação só por áudio.
- **Gestos:** movimentos corporais como entrada.
- **RV x RA:** Realidade Virtual cria ambiente predominantemente digital, imersivo, com isolamento do ambiente externo (headset frequente). Realidade Aumentada enriquece o ambiente físico com informação digital sobreposta (smartphone, tablet ou óculos; comum em manutenção e informação contextual).
- **Conversacional / IA:** linguagem natural, interpretação de contexto, multimodal. Limitações: ambiguidade, imprevisibilidade, necessidade de validar as respostas.

**Critérios para analisar um paradigma:** facilidade de aprendizagem, eficiência, memorização, erros, acessibilidade, feedback, contexto, recursos (hardware/software), privacidade, sustentabilidade.

**Sustentabilidade digital (Aula 2):**
- Obsolescência: novas versões de software que deixam hardware funcional sem suporte geram trocas. Pergunta-chave: dá para evoluir a interface sem obrigar a trocar hardware funcional? Práticas: software eficiente, interfaces leves, compatibilidade, manutenção, modularidade, vida útil estendida.
- O ciclo completo inclui extração, fabricação, transporte, utilização, manutenção, reutilização e reciclagem/descarte, não só o consumo durante o uso.
- Dimensão social: leitores de tela, navegação por teclado, legendas, contraste, ampliação, voz, linguagem compreensível. A multimodalidade amplia o acesso.
- Interfaces que mostram consumo de energia ou água, dashboards ambientais etc. transformam dados técnicos em informação útil para decisão.

---

## Aula 3: Fatores Humanos

**Fatores humanos:** características, capacidades e limitações das pessoas ao interagir com sistemas. Em IHC não basta perguntar "o sistema funciona?". É preciso perguntar "o usuário consegue entender como ele funciona?".

**Ciclo da interação:** usuário → percepção → interpretação → decisão → ação → interface → sistema → **feedback** → usuário. Sem feedback, o usuário não sabe se a ação ocorreu (e pode clicar de novo e duplicar operações).

**Três categorias:**
1. **Físicos:** capacidade motora, mobilidade, precisão, fadiga, postura, alcance. Exemplo: um botão "[X]" pequeno em tela de toque causa mais erro que um botão "[EXCLUIR]" maior.
2. **Perceptivos:** visão, audição, tato.
3. **Cognitivos:** atenção, memória, aprendizagem, modelo mental, carga cognitiva.

**Percepção e hierarquia visual:** usar tamanho, contraste, espaçamento, agrupamento, posição, tipografia e formas. Símbolo + texto ("✓ Pagamento realizado com sucesso") é mais claro que só texto. Agrupar campos (dados pessoais, contato, endereço) reduz o esforço.

**Leis da Gestalt** ("o todo é maior que a soma das partes"): proximidade, semelhança, fechamento, continuidade, figura e fundo, simetria, pregnância (simplicidade).

**Atenção:** é limitada.
- Seletiva: o usuário foca no que se relaciona ao objetivo atual; elementos irrelevantes competem pela atenção.
- Dividida: acompanhar várias fontes ao mesmo tempo (ex.: motorista com GPS). Interfaces em situações críticas devem exigir pouca atenção visual contínua.

**Memória:** sensorial (muito breve) → de trabalho (mantém temporariamente, ex.: código 859427) → de longo prazo (conhecimentos e experiências; ex.: símbolos de lupa, casa, carrinho).
- **Reconhecimento x recordação:** favorecer o reconhecimento (escolher o departamento numa lista) em vez de exigir recordação (digitar o código de memória).

**Aprendizagem:**
- Consistência (mesmo botão "Salvar" em todas as telas, em vez de Salvar/Confirmar/Finalizar/OK para a mesma coisa).
- Transferência de aprendizagem (Ctrl+C, Ctrl+V, Ctrl+Z funcionam em vários programas).

**Modelo mental:** representação interna que o usuário faz de como o sistema funciona. Não precisa ser tecnicamente correta. Metáfora da pasta. Problema: quando modelo do usuário ≠ comportamento do sistema (ex.: o usuário acha que excluir apaga de vez, mas o arquivo vai para a lixeira).

**Affordance:** propriedade que permite perceber como interagir com algo sem instruções (James Gibson; popularizada por Don Norman). Um botão "[COMPRAR]" deve parecer clicável; texto clicável que parece texto comum é um problema. **Significadores** são pistas de uso: "Clique aqui", lupa, seta, sublinhado de link, rótulos, bordas de campos.

**Limitações:** permanentes, temporárias e **situacionais** (ambiente barulhento dificulta ouvir como uma deficiência auditiva; por isso legendas ajudam muita gente).

**Carga cognitiva:** recursos mentais exigidos (tarefa + informações + decisões + memorização + navegação). Excesso aumenta erros, demora, abandono, frustração e pedidos de suporte. Estratégias: eliminar o desnecessário, agrupar, títulos claros, hierarquia, terminologia conhecida, valores padrão, exemplos, feedback, evitar exigir memorização, padrões conhecidos, instruções no momento certo e dividir tarefas complexas (formulário em etapas, sem exagerar nelas).

**Prevenção de erros e feedback:** confirmação antes de ações destrutivas ("Você está prestes a excluir 327 registros. Não poderá ser desfeito."). "Processando..." seguido de "✓ Formulário enviado".

**Acessibilidade:** não depender só de visão, audição, precisão motora, percepção de cor ou memória. Cor só como complemento (erro com texto "CPF inválido", e não só campo vermelho). Para idosos: legibilidade, contraste, tamanho, linguagem clara, poucas etapas, tempo suficiente, recuperação de erros. A meta é uma interface para uma população diversa, não "interface para idosos".

**Sustentabilidade:** interface ruim causa erros, retrabalho, mais operações, mais tempo, mais processamento e comunicação. Mas sustentabilidade digital também depende de eficiência de software, infraestrutura, servidores, redes, armazenamento, vida útil dos equipamentos, consumo e descarte.

**No desenvolvimento:** requisitos (quem usa, onde, dispositivo, experiência, necessidades), projeto (estrutura, navegação, hierarquia, mensagens), implementação (acessibilidade, responsividade, validações, teclado) e testes (tempo, erros, dificuldades, satisfação).

---

## Aula 4: Projeto de Interfaces (Projeto Centrado no Usuário)

- O projeto começa pelo usuário, pelas tarefas e pelo contexto, e não por cores, botões e fontes.
- **PCU (Projeto Centrado no Usuário):** pergunta inicial é "o que o usuário precisa fazer?". A abordagem orientada ao sistema (sistema → funcionalidades → telas → usuário) é o oposto.
- Fluxo centrado no usuário: Usuários → Necessidades → Tarefas → Requisitos → Projeto → Protótipo → Avaliação → Aprimoramento.
- **Processo iterativo:** ciclos de criar, testar e melhorar. Vantagens: redução de riscos, flexibilidade, melhoria contínua. A primeira interface raramente é a definitiva.

**Seis etapas:** (1) identificar usuários, (2) compreender o contexto, (3) identificar necessidades, (4) definir requisitos, (5) desenvolver soluções (fluxos, esboços, wireframes, protótipos), (6) avaliar. Se achar problema: alterar o projeto, novo protótipo, nova avaliação.

**Requisitos:** funcionais (o que o usuário pode fazer), de interação (como acontece; ex.: funcionalidade "excluir cadastro" x requisito de interface "pedir confirmação antes de excluir") e de usabilidade (reduzir erros, facilitar aprendizagem, dar feedback, manter consistência). Interface eficiente não é a que tem poucas telas, e sim a que tem etapas que fazem sentido para a tarefa.

**Persona:** representação de um grupo relevante de usuários, construída a partir de dados reais (entrevistas, questionários, observação, análise de tarefas, registros de uso), e não da imaginação da equipe. Exemplo: Mariana.

**Cenário:** situação em que a persona usa o sistema para um objetivo (contexto, objetivo, necessidade, possível problema).

**Cadeia (cada etapa reduz a abstração):** usuário → persona → cenário → tarefa → fluxo → wireframe → protótipo → interface.

**Fluxo de interação:** caminhos percorridos para realizar uma tarefa. Criar fluxos antes das telas ajuda a definir como se chega às telas, o que acontece em erro, como voltar, quais decisões e quais etapas são obrigatórias.

**Wireframe:** mostra a **estrutura** (posição do menu, organização, campos, botões, hierarquia), sem definir cores, fotos, tipografia final, animações ou identidade visual.

**Protótipo:** representação da solução para explorar, comunicar e avaliar ideias antes da implementação, com custo menor.

| | Baixa fidelidade | Alta fidelidade |
|---|---|---|
| Detalhamento | Baixo (papel, quadro, cartões) | Alto (cores, fontes, navegação funcional) |
| Velocidade | Maior | Menor |
| Alterações | Simples | Mais trabalhosas |
| Uso | Exploração inicial | Validação mais avançada |

---

## Aula 5: Avaliação de Interfaces

- Uma interface não é adequada só porque funciona tecnicamente. Pode acessar o banco e calcular certo e ainda ter botão escondido, erros em códigos técnicos e nenhuma confirmação.
- **Avaliação de interfaces:** análise sistemática para verificar se usuários realizam tarefas adequadamente no contexto de uso. Aspectos: eficácia, eficiência, satisfação, facilidade de aprendizagem, prevenção/recuperação de erros, acessibilidade.
- Evita decisões baseadas na opinião do desenvolvedor ("para mim o botão está visível"). A pergunta certa é se os usuários conseguem localizar o botão quando precisam.

**Dois grupos de métodos (complementares):**
- **Sem usuários (especialistas):** avaliação heurística, inspeção de interface, walkthrough cognitivo, inspeção de consistência, análise por diretrizes.
- **Com usuários:** testes de usabilidade, entrevistas, questionários, observação, análise de tarefas.

**As 10 heurísticas de Jakob Nielsen:**
1. Visibilidade do estado do sistema (feedback em tempo real).
2. Correspondência entre o sistema e o mundo real (linguagem do usuário).
3. Controle e liberdade do usuário ("saída de emergência", desfazer).
4. Consistência e padrões.
5. Prevenção de erros (ex.: desativar o botão de envio até preencher os campos).
6. Reconhecimento em vez de memorização.
7. Flexibilidade e eficiência de uso (atalhos para experientes).
8. Estética e design minimalista.
9. Ajudar a reconhecer, diagnosticar e recuperar-se de erros (mensagem simples, precisa, com solução).
10. Ajuda e documentação.

**Registro de problemas:** de forma objetiva (tela, elemento, problema, consequência, heurística relacionada, recomendação). "A tela está ruim" não serve.

**Severidade:** 0 não é problema; 1 cosmético (baixa prioridade); 2 pequeno (prejudica mas permite concluir); 3 grave (dificuldade significativa); 4 crítico (pode impedir a tarefa).

**Teste de usabilidade:** observa pessoas executando tarefas representativas. Planejar: objetivo, participantes, tarefas, métricas, procedimentos.
- Tarefa adequada = objetivo real, sem ensinar o caminho ("Compre um notebook de até R$ 4.000 e coloque no carrinho"), e não "clique em Produtos > Informática > Notebook".
- O avaliador não deve orientar o participante. Pode dizer: "faça como faria normalmente se estivesse sozinho". O comportamento é registrado.
- Observar: hesitações, caminhos incorretos, cliques repetidos, retornos, mensagens de erro, pedidos de ajuda, abandono, comentários espontâneos.

**Métricas:**
- **Taxa de conclusão = (tarefas concluídas ÷ tarefas realizadas) × 100.** Ex.: 17/20 = 85%.
- Tempo (precisa de contexto para interpretar), taxa de erros (concentração de erros no mesmo ponto indica problema de projeto), número de cliques, etapas, pedidos de ajuda, retornos, abandono, satisfação.
- **SUS (System Usability Scale):** questionário padronizado de percepção de usabilidade.
- **Quantitativos mostram quanto** o problema ocorreu; **qualitativos mostram como e por quê**. Registre "6 dos 10 participantes tiveram dificuldade para localizar o carrinho", não "os usuários tiveram dificuldade".

**Sustentabilidade:** interface eficiente reduz ações desnecessárias, retrabalho, impressões e abandono. Se o serviço digital é difícil, as pessoas imprimem, telefonam, vão presencialmente e repetem cadastros.

---

## Aula 6: Arquitetura da Informação (AI)

- Problema típico: o documento existe, mas encontrá-lo exige esforço excessivo (ex.: calendário acadêmico escondido, busca com dezenas de resultados antigos).
- **AI:** disciplina que estrutura, organiza, rotula e conecta conteúdos para facilitar usabilidade e encontrabilidade. Responde: onde estou? o que existe aqui? para onde posso ir? como encontro? como volto?
- **AI = Organização + Rotulagem + Navegação + Busca.**
- **AI x Interface:** a AI determina como informações e funções são organizadas. A interface define como são apresentadas (cores, fontes, botões, ícones). Interface bonita pode ter AI deficiente.

**Sistemas de organização:** alfabética, cronológica, geográfica, por assunto, por público, por tarefa. Em sistemas reais costumam ser combinados.

**Taxonomia:** estrutura que classifica informações em categorias e subcategorias (bibliotecas digitais, portais governamentais, e-commerce, repositórios científicos).

**Hierarquia:** níveis de importância e relacionamento. Hierarquia muito profunda exige muitos passos, e a solução são caminhos alternativos e atalhos.

**Rotulagem:** rótulos devem ser claros, curtos, consistentes, compreensíveis e representativos. Ruins: "Mais", "Outros", "Opções", "Soluções", "Clique aqui". Melhores: "Baixar Calendário Acadêmico", "Serviços Acadêmicos".

**Navegação:** global (sempre disponível), local (da seção atual), contextual (relações dentro do conteúdo, "Consulte também") e **breadcrumbs** (trilha: Início > Cursos > Graduação > Sistemas para Internet; mostram a posição).

**Busca:** palavras-chave, relevância, filtros (ano, campus, curso, tipo), ordenação, tratamento de erros e de ausência de resultados. Filtros reduzem o espaço informacional. AI não é só armazenar, é permitir recuperar com eficiência.

**Sitemap x menu:** sitemap representa a estrutura completa/planejada (árvore de páginas). Menu é um componente de interface que dá acesso a parte dela. Nem toda página do sitemap precisa estar no menu principal.

**AI e UX:** melhor organização → navegação compreensível → informação mais fácil de achar → menos esforço → melhor experiência. Um site com design excelente tem UX ruim se o usuário não acha o que procura (ex.: comprovante de matrícula enterrado em "Sistema > Recursos > Outras funcionalidades > ..." quando deveria estar em "Área do Aluno > Documentos").

**Sequência da aula:** Conteúdo → Classificação → Taxonomia → Hierarquia → Rotulagem → Navegação → Busca → UX.

**Sustentabilidade digital:** uso responsável da tecnologia para reduzir impactos ambientais, sociais e econômicos. Pilares: eficiência energética, gestão de resíduos, inclusão social, uso ético de dados. A AI ajuda a reduzir navegação desnecessária, páginas redundantes, duplicação, armazenamento e tempo de busca, mas não se deve afirmar que uma mudança de AI reduz o consumo de energia sem avaliação técnica. Sua contribuição mais direta é a eficiência informacional e operacional.

---

## Aula 7: Acessibilidade Digital e Design Inclusivo

- Um serviço ambiental (ex.: agendar descarte de eletrônicos) pode excluir pessoas: cartaz só em imagem, vídeo sem legenda, pontos só em verde no mapa, letras claras sobre fundo branco, botão só com mouse.
- Três dimensões de análise: **ambiental, social, econômica** (barreiras geram retrabalho, abandono, atendimento extra). A acessibilidade contribui diretamente para a inclusão, mas redução de impacto ambiental precisa de avaliação própria.
- **Acessibilidade digital:** condição que permite a pessoas com deficiência perceber, compreender, navegar e interagir com conteúdos e serviços digitais. Estar na internet não é estar acessível (ex.: botão só com desenho, sem nome acessível, é inútil para quem usa leitor de tela).

| Conceito | Pergunta |
|---|---|
| Acessibilidade | Há barreiras que impedem pessoas com deficiência de realizar a tarefa? |
| Usabilidade | A tarefa pode ser feita com clareza e eficiência? |
| Design inclusivo | Quais diferenças humanas e contextos estão sendo considerados? |

- **Design inclusivo como processo:** quem usará? quem pode estar sendo excluído? que decisão produz a exclusão? que alternativas permitem a mesma tarefa? como verificar com os afetados? (ex.: se o endereço só se informa arrastando um marcador no mapa, oferecer campos de endereço).
- Um botão de aumentar fonte **não** torna o site acessível (não resolve imagens sem descrição, vídeos sem legenda, controles sem nome, dependência de mouse).

**Barreiras e soluções:** cegueira (texto alternativo, estrutura para leitor de tela), baixa visão (ampliação, contraste), daltonismo/dificuldade com cores (rótulos, símbolos, texto), surdez (legendas), limitação motora (teclado), dificuldades cognitivas (linguagem clara, organização previsível), limitação de fala (canal textual).

**Tecnologias assistivas:** leitores de tela, ampliadores, linhas braille, reconhecimento de voz, acionadores e dispositivos adaptados. Elas dependem de informação adequada da interface (leitor de tela não corrige formulário sem rótulos nos campos).

**Limitações:** permanentes, temporárias (braço imobilizado) e situacionais (ambiente sem poder ouvir o áudio).

**WCAG (Web Content Accessibility Guidelines):** diretrizes do W3C; a aula usa a versão **2.2**. Têm princípios, diretrizes e critérios de sucesso com níveis A, AA, AAA. Conformidade AA exige atender aos critérios aplicáveis de A **e** AA.

**Quatro princípios (POUR):**
- **Perceptível:** a informação pode ser percebida (texto além de imagem; legendas; gráfico com dados em tabela).
- **Operável:** os controles podem ser acionados (menu que só abre com mouse viola isso; oferecer teclado e foco visível).
- **Compreensível:** a pessoa entende o que fazer e como corrigir ("Erro 27" é ruim; "Informe a quantidade usando um número inteiro maior que zero" é bom).
- **Robusto:** interpretável por diferentes agentes de usuário e tecnologias assistivas (usar botão HTML nativo, e não um texto programado para parecer botão). "Robusto" aqui trata de compatibilidade, não de potência do computador.

**Contraste (nível AA):** texto comum **4,5:1**; texto grande **3:1** (texto grande ≥ 18 pt, ou 14 pt em negrito). Há exceções (logotipos etc.). A conformidade exige calcular ou medir.

**Cor não deve carregar sozinha o significado:** erro em vermelho → mensagem textual; ponto "disponível" em verde → rótulo "Disponível"; gráfico só por cor → rótulos, padrões ou símbolos.

**Teclado:** toda funcionalidade deve ser operável por teclado (exceção: funções que dependem do percurso do movimento, como desenho à mão livre).

**Formulários acessíveis:** `label` associado ao campo por `for`/`id`; **placeholder não substitui o rótulo** (some ao digitar); `type="email"`, `autocomplete`, `aria-describedby` (orientação complementar) e `required`.

---

## Aula 8: IHC e Sustentabilidade

- Problema inicial: trocar formulários impressos por sistema digital não torna o sistema sustentável, se ele exige celular novo, tem vídeos automáticos, perde dados no erro e obriga a imprimir o comprovante. É preciso considerar equipamentos, eletricidade, transmissão de dados, manutenção, acessibilidade e a impressão.
- **Desenvolvimento sustentável:** atender às necessidades atuais preservando as condições das gerações futuras (dimensões ambiental, social, econômica). Agenda 2030; **ODS 12** = consumo e produção responsáveis.

**Duas perspectivas complementares:**
- **Sustentabilidade da TI:** reduzir os impactos dos próprios equipamentos, sistemas e infraestrutura (ex.: evitar processamento desnecessário).
- **TI para a sustentabilidade:** usar sistemas para melhorar atividades de outros setores (ex.: identificar desperdício de água).
- Um app de monitoramento de água ilustra as duas, pois ajuda a achar vazamentos, mas usa sensores, rede, armazenamento e dispositivos. Para saber se compensa, é preciso conhecer o desperdício evitado, os recursos para operar, a duração e a alternativa de comparação.

**Ciclo de vida:** extração e transformação de materiais → fabricação e transporte → aquisição e implantação → uso e manutenção → reutilização, recuperação e destinação final. Trocar todos os computadores por modelos mais eficientes nem sempre é melhor: é preciso comparar fabricação, estado dos existentes, necessidade e economia ao longo do tempo.

**Contribuição da IHC:** Eli Blevis propôs o **Sustainable Interaction Design** (sustentabilidade no centro do projeto de interação: descarte, renovação, reutilização). Interface confusa leva a tarefas repetidas, mas o efeito ambiental deve ser verificado no contexto real. **Menos cliques não significa automaticamente menos energia.**

Exemplos de problema → melhoria: formulário que apaga tudo no erro (preservar campos); usuário não acha documento (melhorar rótulos, busca, organização); botão sem indicação de processamento gera cliques repetidos (mostrar andamento, impedir duplicidade); download de arquivo grande para consulta simples (mostrar o essencial na página); atualização que exige hardware superior sem necessidade (rever requisitos, testar em equipamento modesto).

**Comportamento do usuário (5 aspectos):** informação, esforço, custo, hábito, condições reais. Não atribuir todo o resultado ao indivíduo: empresas, infraestrutura e políticas também condicionam.

**Incentivo x manipulação:** informar que a impressão é frente e verso e permitir alterar é incentivo legítimo; cobrança "ambiental" sem explicação e difícil de remover é manipulação. Exemplo: 20 páginas × 3 cópias = 60 folhas (uma face) ou 30 folhas (frente e verso).

**Feedback compreensível:** deve indicar **unidade, período e referência de comparação** (ex.: "Consumo registrado nesta semana: 42 kWh", e não "Seu consumo está ruim"). Considerar fatores como número de usuários, dias de funcionamento, temperatura e volume de trabalho.

**Incentivos contraditórios:** premiar com pontos "de sustentabilidade" cada compra estimula consumo, e contar compras não prova benefício ambiental.

**Green IT (TI Verde):** práticas, projetos e tecnologias para minimizar o impacto ambiental da TIC (fabricação, eficiência energética, descarte de resíduos eletrônicos, ecodesign de software). A **Green Software Foundation** organiza a abordagem em **eficiência energética**, **eficiência de hardware** e **consciência de carbono** (intensidade de carbono da eletricidade; ex.: horário de tarefas flexíveis).

**Papel do profissional de SI:** análise de negócios (questionar a necessidade), requisitos (objetivos ambientais mensuráveis), UX/IHC (pesquisar barreiras), desenvolvimento (desperdício de processamento e dados), infraestrutura (ajustar capacidade), gestão (comparar custos e impactos na vida útil), governança de dados (coleta, retenção, descarte), avaliação (comunicar resultados, limites e método).

---

## Aula 9: Impactos Ambientais da Tecnologia (hardware, energia, resíduos)

- Atividades digitais parecem imateriais, mas dependem de equipamentos, infraestrutura (antenas, fibras, servidores) e energia. Substituir uma atividade presencial por digital **nem sempre** reduz o impacto ambiental.
- **Ciclo de vida do equipamento:** extração (minerais, água, rejeitos) → fabricação (chips, placas, telas, baterias; energia, água, químicos) → distribuição (transporte, embalagens) → utilização (eletricidade, manutenção) → extensão da vida útil (reparo, atualização, reutilização) → fim de vida (coleta, tratamento, recuperação de materiais).
- **Impactos incorporados:** impactos das etapas anteriores ao uso (extração, fabricação, transporte). Um equipamento novo já tem impacto antes de ser ligado. Um computador novo pode consumir menos que o antigo, mas é preciso considerar a fabricação dele e o destino do anterior.
- **Manter ou substituir:** considerar desempenho necessário, funcionamento e segurança, suporte de software, manutenção/atualização, consumo medido, impactos da fabricação dos substitutos e destino dos antigos. Prolongar a vida útil pode reduzir a fabricação, mas depende das condições reais.
- **Comparar serviços equivalentes** (ex.: 30 postos de trabalho aptos a executar as atividades), e não apenas "um computador antigo x um novo".

**Potência x energia:**
- **Potência (W):** taxa de uso de energia em um instante.
- **Energia (kWh):** depende da potência e do tempo → **Energia (kWh) = potência (kW) × tempo (h)**.
- Exemplo da aula: 30 computadores × 120 W × 5 h/dia × 20 dias = **360 kWh/mês**.
- A capacidade nominal de uma fonte (500 W) não é o consumo contínuo.

**Consumo ≠ emissão:** a emissão associada à eletricidade depende de como ela é produzida. Estimativa simplificada: **emissões = energia consumida × fator de emissão** (informar origem, período e metodologia do fator). Dois data centers com o mesmo consumo podem ter emissões diferentes.

**Centros de dados (data centers):** instalações com servidores, armazenamento, rede, alimentação/proteção elétrica e refrigeração. A IEA estimou ~**415 TWh** em 2024, cerca de **1,5%** do consumo mundial de eletricidade (dado só de data centers, não de todos os equipamentos digitais). A **refrigeração** importa porque o calor precisa ser removido.

Software que gasta recursos à toa: consultas repetidas ao banco, processamento em segundo plano sem necessidade, arquivos maiores que o necessário, atualização de tela excessiva, armazenamento sem critério de retenção, reprodução automática não solicitada. Reduzir essas operações pode reduzir a demanda, mas a economia elétrica não é diretamente proporcional e precisa ser verificada.

**Obsolescência:** funcional, por incompatibilidade, **percebida** (continua útil mas é visto como ultrapassado) e **programada** (vida útil deliberadamente limitada; exige evidência de decisão intencional). Um defeito, isoladamente, não demonstra obsolescência programada. Celular que funciona mas sem atualizações de segurança não equivale a um plenamente suportado (funcionamento físico, compatibilidade e segurança são dimensões distintas).

**Lixo eletrônico:** Global E-waste Monitor 2024: ~**62 milhões de toneladas** geradas em 2022, das quais **22,3%** com coleta e reciclagem formal ambientalmente adequada documentadas.
- Reparar = recuperar o funcionamento; Reutilizar = usar de novo; Recondicionar = preparar para novo uso após avaliação e intervenções; Reciclar = processar resíduos para recuperar materiais.
- Gestão sustentável combina reduzir demanda, estender a vida útil, reutilizar e reciclar.
- **Logística reversa** (SINIR): entrega em pontos de recebimento. Em instituições, seguir procedimentos patrimoniais. Antes de doar: condições de uso, necessidade de quem recebe, **tratamento dos dados armazenados**, registro e autorização, destinação dos componentes inutilizáveis. Doar equipamento sem recuperação só transfere o problema do descarte.

**Duas formas de atuação:** reduzir o impacto da própria tecnologia x usar tecnologia para reduzir outros impactos (ex.: sistema que identifica consumo anormal de energia). Todo sistema ambiental tem impactos próprios.

**Interfaces que favorecem decisões ambientais:** (a) tornar o consumo visível (com período, origem dos dados e referência); (b) comparações adequadas (consumo total, por hora, por atendimento, nº de equipamentos); (c) facilitar ação concreta ("salve seus arquivos e siga o procedimento de desligamento"), e não "Seja sustentável"; (d) configurações adequadas (economia de energia, autoplay desativado, qualidade de mídia selecionável, pré-visualização de impressão, aviso de duplicidade); (e) apoiar manutenção e reutilização (inventário com idade, configuração, histórico, suporte).

**Limites éticos:** dados verificáveis, diferenciar medição de estimativa, explicar indicadores, preservar acessibilidade, evitar exposição individual desnecessária, permitir revisão e **evitar alegações ambientais sem fundamento** (ex.: "Você salvou cinco árvores" sem metodologia).

**Efeito rebote:** melhoria de eficiência parcialmente compensada pelo aumento do uso. Ex.: consumo por operação de 10 → 6 (−40%), mas com mais operações o consumo total subiu 20%. Avaliar eficiência exige acompanhar o volume total de uso.

---

## Aula 10: Cidades Inteligentes (Smart Cities)

- Sensores, câmeras e app não bastam: se os ônibus continuam atrasados, alertas não chegam a todos e quem não tem smartphone não solicita serviços, a cidade não é necessariamente inteligente.
- **Smart city:** usa TIC, dados e formas de gestão para melhorar serviços urbanos e qualidade de vida. A definição da **ITU** inclui as necessidades das gerações presentes e futuras (econômica, social, ambiental, cultural). A **Carta Brasileira para Cidades Inteligentes** liga transformação digital a desenvolvimento urbano sustentável, redução de desigualdades, participação social e uso responsável de dados.
- A quantidade de equipamentos não prova qualidade. Perguntas: qual problema foi resolvido, quem foi beneficiado, quais custos e impactos? Dimensões: **ambiental, social, econômica e governança** (responsáveis, transparência, participação). A interface é só uma parte; um app de coleta seletiva só funciona se os resíduos tiverem destinação adequada.

**Infraestrutura urbana conectada:** integração de equipamentos e serviços urbanos com redes e sistemas de informação (ônibus enviando localização, medidores de energia, sensores de nível de córrego, luminárias que informam falhas, contêineres que informam nível). A informação precisa chegar a quem possa agir.

**IoT (Internet das Coisas):** objetos físicos com identificação, processamento e comunicação, que trocam dados com outros sistemas.

| Componente | Função |
|---|---|
| Sensor | Mede uma condição física |
| Controlador | Processa leituras e executa regras |
| Atuador | Executa ação física |
| Rede | Transporta os dados |
| Plataforma | Armazena, integra, analisa |
| Interface | Permite consulta/interação humana |

**Um sensor mede; um atuador age.** Um sistema pode só monitorar, sem ação automática.

**Da coleta à decisão (ex.: alagamentos):** coleta → transmissão → armazenamento → tratamento → análise → comunicação → ação e avaliação. Cuidados: calibração e manutenção dos sensores, detectar interrupções, controlar acesso, identificar duplicidades e falhas, considerar incertezas, comunicar de forma compreensível, verificar se a resposta funcionou.

**Dado anômalo:** leituras de 1,20 m, 1,23 m, "sem leitura" e 12,50 m. Não se conclui na hora que o nível subiu: pode ser ocorrência real, falha do equipamento ou erro de unidade/transmissão. Sinalizar a anomalia e validar. Ausência de leitura não significa ausência de risco; informação antiga deve aparecer como desatualizada; valores incomuns não devem ser descartados automaticamente.

**Interoperabilidade:** capacidade de sistemas diferentes trocarem e usarem informações (exige acordo sobre formatos, localização, horários, unidades e significado).

**Aplicações (possibilidades de projeto; os benefícios precisam ser medidos em cada caso):**
- **Mobilidade:** localização e previsão de chegada de ônibus (indicar quando a previsão foi atualizada e informação de acessibilidade); reduzir o tempo de viagem de carro, por si só, não prova mobilidade sustentável. Indicadores: regularidade, tempo de espera, acessibilidade, participação dos modos de transporte.
- **Energia e iluminação:** exemplo 1.000 kWh → 750 kWh = redução de 25%, mas verificar área atendida, tempo de funcionamento, adequação da iluminação, consumo dos controles e custos. Reduzir iluminação inadequadamente prejudica circulação e acessibilidade.
- **Resíduos:** sensores e apps não separam, coletam ou reciclam sozinhos; precisam de equipes, cooperativas e infraestrutura. Indicadores: transbordamentos, distância percorrida, quantidade recuperada, contaminação.
- **Monitoramento ambiental:** temperatura, chuva, ruído, poluentes. Uma medição em um ponto não representa todo o bairro.

**Impactos da própria tecnologia:** energia de equipamentos/redes/processamento, fabricação, vida útil e reparo, baterias, resíduos eletrônicos, frequência da coleta de dados (transmitir a leitura de uma lixeira a cada segundo costuma ser desnecessário). **Efeito rebote:** o consumo por equipamento cai, mas muitos equipamentos adicionais podem elevar o consumo total.

**Governança digital:** responsabilidades, critérios e participação para orientar o uso de tecnologia e dados. Perguntas: qual problema público? quem responde? quais dados (evitar coleta excessiva; consultar horário de coleta não exige acesso aos contatos)? quem acessa? por quanto tempo? como contestar erro? como continua em caso de falha? como divulgar resultados?

**Inclusão digital (5 condições):** conexão, dispositivo adequado, conhecimento, acessibilidade da interface e atendimento alternativo. Se o agendamento de coleta de móveis é só por app, quem não tem smartphone fica de fora. Melhoria: integrar app, site e atendimento assistido no mesmo sistema. Participação cidadã inclui quem não usa canais digitais.

---

## Aulas 11 e 12: Biotecnologia

**Atenção:** nos PDFs dessas duas aulas só foram extraídos os slides de abertura e os objetivos (os slides têm só 8 páginas e terminam em "Fundamentos da Biotecnologia" e "Biotecnologia Moderna"). Abaixo estão os tópicos que a professora listou como objetivos, com definições gerais de apoio. Confira nos slides/aula se há conteúdo adicional.

**Aula 11: Fundamentos**
- Definir biotecnologia e sua importância para a sociedade.
- Diferenciar biotecnologia **tradicional** (ex.: fermentação para pão, queijo, vinho) e **moderna** (engenharia genética, DNA recombinante).
- Identificar organismos, células e moléculas usados em processos biotecnológicos.
- Conceitos introdutórios de DNA, genes e engenharia genética.
- Aplicações em saúde, agricultura, indústria e preservação ambiental.
- Relação com sustentabilidade.
- Integração com informática: programação, bancos de dados, IA, sensores e IoT.

**Aula 12: Biotecnologia moderna**
- Engenharia genética e **OGMs** (organismos geneticamente modificados: organismos cujo material genético foi alterado por técnicas de engenharia genética).
- Diagnóstico de doenças e produção de medicamentos.
- Aplicações ambientais e industriais.
- **Bioinformática** e bancos de dados biológicos (uso de computação, algoritmos, sistemas de informação e IA para armazenar e analisar dados biológicos, como sequências de DNA).
- Riscos, benefícios e implicações éticas, sociais e ambientais.
- Integração de sustentabilidade, informática, acessibilidade, tecnologias digitais e biotecnologia.

---

# PARTE 2: 40 PERGUNTAS (múltipla escolha)

O gabarito comentado está no final.

## Aula 1

**1.** Considere dois aplicativos bancários. O A tem visual sofisticado, muitas animações, menus escondidos e ícones sem descrição. O B é visualmente simples, com funções principais claras, confirmação antes de operações críticas e mensagens de erro compreensíveis. Do ponto de vista da IHC:
a) O A é melhor, porque IHC trata principalmente da aparência.
b) O B pode oferecer melhor experiência, porque IHC avalia se o usuário realiza suas tarefas com facilidade, e não só a beleza.
c) Os dois são equivalentes, desde que executem as mesmas funções.
d) Nenhum dos dois, pois IHC trata apenas de hardware.

**2.** Qual item abaixo é exemplo de **interação** (e não de interface)?
a) Um botão.
b) Um menu.
c) Um ícone.
d) A sequência de ações de navegar e preencher um formulário recebendo feedback.

**3.** Sobre usabilidade e UX, é correto afirmar:
a) UX é mais amplo: inclui a usabilidade e também sentimentos, percepções e a jornada completa do usuário.
b) Usabilidade e UX são sinônimos.
c) UX trata apenas da aparência visual.
d) Usabilidade engloba a UX.

## Aula 2

**4.** Sobre os paradigmas de interação, é correto afirmar:
a) Cada novo paradigma elimina o anterior.
b) Hoje só existem a interface gráfica e o toque.
c) Eles frequentemente coexistem, pois cada um funciona melhor em determinada situação.
d) A linha de comando foi abandonada.

**5.** Sobre a CLI (interface de linha de comando), é correto afirmar:
a) É a que oferece maior descoberta visual das funções.
b) Exige conhecer a sintaxe e tem curva de aprendizagem maior, mas é muito eficiente para usuários experientes e permite automação por scripts.
c) Baseia-se no modelo WIMP.
d) Raramente é usada em servidores e DevOps.

**6.** Na sigla WIMP, associada às interfaces gráficas, as letras representam:
a) Windows, Icons, Menus, Pointer.
b) Web, Interface, Mobile, Protocol.
c) Wireless, Input, Monitor, Panel.
d) Windows, Input, Mouse, Program.

**7.** Um usuário aponta a câmera do smartphone para um equipamento e a tela mostra informações digitais sobrepostas à imagem real. Esse recurso é:
a) Realidade Virtual.
b) Interface de linha de comando.
c) Interface conversacional.
d) Realidade Aumentada.

## Aula 3

**8.** Em uma tela sensível ao toque, um botão "[X]" muito pequeno aumenta os erros de seleção em comparação com um botão "[EXCLUIR]" maior. Isso se relaciona principalmente a fatores:
a) Cognitivos.
b) Perceptivos.
c) Físicos.
d) De memória sensorial.

**9.** Aplicando a regra de favorecer o reconhecimento em vez da recordação, a melhor solução para informar o departamento em um formulário é:
a) Oferecer uma lista de departamentos para o usuário selecionar.
b) Pedir que o usuário digite o código do departamento.
c) Mostrar o código em uma tela anterior e exigir que o usuário lembre dele.
d) Remover o campo e deduzir o departamento automaticamente.

**10.** Em um formulário, os campos de endereço aparecem próximos entre si e separados dos campos de contato, formando grupos visuais. Qual lei da Gestalt explica essa percepção?
a) Continuidade.
b) Proximidade.
c) Fechamento.
d) Simetria.

**11.** O usuário acredita que "excluir arquivo" o apaga definitivamente, mas o sistema o envia para a lixeira. Esse problema ilustra:
a) Baixo contraste.
b) Carga cognitiva excessiva.
c) Memória sensorial.
d) Modelo mental do usuário diferente do comportamento do sistema.

**12.** Um texto clicável tem aparência de texto comum e o usuário não percebe que há uma ação disponível. Isso é um problema de:
a) Carga cognitiva.
b) Falta de feedback.
c) Affordance (e falta de significadores).
d) Lei de fechamento.

## Aula 4

**13.** Sobre o Projeto Centrado no Usuário (PCU):
a) Começa definindo as telas e as funcionalidades do sistema.
b) Começa perguntando o que o usuário precisa fazer e é um processo iterativo (projeto, protótipo, avaliação e aprimoramento).
c) É linear e a primeira interface é considerada definitiva.
d) Dispensa avaliação com usuários.

**14.** O wireframe é:
a) Uma representação da estrutura da interface (posição de menu, campos, botões, hierarquia), sem definir a aparência final.
b) Um protótipo de alta fidelidade com cores e tipografia finais.
c) Um teste de usabilidade com participantes.
d) Uma persona detalhada.

**15.** Uma persona útil é:
a) Um usuário fictício criado pela imaginação da equipe.
b) Um usuário real que participa do teste.
c) O mesmo que um cenário de uso.
d) A representação de um grupo relevante de usuários, construída a partir de dados levantados (entrevistas, observação, questionários).

## Aula 5

**16.** O botão "desfazer", que funciona como "saída de emergência" para o usuário, corresponde à heurística de Nielsen:
a) Visibilidade do estado do sistema.
b) Prevenção de erros.
c) Controle e liberdade do usuário.
d) Flexibilidade e eficiência de uso.

**17.** Desativar o botão de envio até que os campos obrigatórios estejam preenchidos exemplifica a heurística:
a) Visibilidade do estado do sistema.
b) Prevenção de erros.
c) Estética e design minimalista.
d) Ajuda e documentação.

**18.** Em um teste de usabilidade, qual é um exemplo de tarefa **adequada**?
a) "Você precisa comprar um notebook de até R$ 4.000. Localize um modelo e coloque-o no carrinho."
b) "Clique no menu Produtos, depois em Informática e em Notebook."
c) "Você acha este aplicativo fácil de usar?"
d) "Informe se o contraste da tela é agradável."

**19.** Em um teste, foram realizadas 24 tentativas de uma tarefa e 18 terminaram com sucesso. A taxa de conclusão é:
a) 25%.
b) 60%.
c) 133%.
d) 75%.

## Aula 6

**20.** Sobre Arquitetura da Informação (AI):
a) Trata apenas de cores e fontes.
b) É o mesmo que o menu do site.
c) Envolve organização, rotulagem, navegação e busca, definindo como a informação é estruturada, enquanto a interface define como ela é apresentada.
d) É o mapa visual do site.

**21.** Sobre sitemap e menu:
a) O sitemap representa a estrutura completa ou planejada; o menu é um componente da interface que dá acesso a parte dessa estrutura.
b) São a mesma coisa.
c) O menu representa toda a arquitetura da informação.
d) Todas as páginas do sitemap devem aparecer no menu principal.

**22.** "Início > Cursos > Graduação > Sistemas para Internet" é um exemplo de:
a) Rótulo genérico.
b) Breadcrumb (trilha de navegação), que mostra a posição do usuário na estrutura.
c) Busca com filtros.
d) Taxonomia de produtos.

## Aula 7

**23.** Sobre acessibilidade, usabilidade e design inclusivo:
a) São sinônimos.
b) A acessibilidade avalia se a tarefa é feita com clareza e eficiência.
c) O design inclusivo só considera pessoas com deficiência visual.
d) A acessibilidade pergunta se há barreiras que impedem pessoas com deficiência de realizar a tarefa; a usabilidade, se ela é clara e eficiente; o design inclusivo considera a diversidade humana desde a definição do problema.

**24.** Um menu abre apenas ao passar o mouse e não pode ser aberto pelo teclado. Qual princípio das WCAG é violado?
a) Perceptível.
b) Compreensível.
c) Operável.
d) Robusto.

**25.** Para o critério de contraste mínimo das WCAG (nível AA), as relações mínimas são:
a) 3:1 para texto comum e 4,5:1 para texto grande.
b) 4,5:1 para texto comum e 3:1 para texto grande.
c) 7:1 para qualquer texto.
d) 2:1 para texto comum e 1,5:1 para texto grande.

**26.** Em formulários acessíveis:
a) Deve-se associar o `label` ao campo (com `for` e `id`), e o placeholder não substitui o rótulo.
b) O placeholder é suficiente para identificar o campo.
c) Basta destacar o campo obrigatório em vermelho.
d) O rótulo é dispensável se o campo tiver `type` definido.

## Aula 8

**27.** Um aplicativo de monitoramento de água que ajuda a identificar vazamentos, mas usa sensores, rede, armazenamento e dispositivos, ilustra:
a) Apenas a sustentabilidade da TI.
b) Apenas a TI para a sustentabilidade.
c) Nenhuma das duas perspectivas.
d) As duas perspectivas: TI para a sustentabilidade e sustentabilidade da própria TI.

**28.** Segundo a aula, qual mensagem de feedback é a mais útil para o usuário?
a) "Seu consumo está ruim."
b) "Entrega verde."
c) "Consumo registrado nesta semana: 42 kWh."
d) "Você economizou muito."

**29.** A Green Software Foundation organiza sua abordagem em:
a) Velocidade, custo e escalabilidade.
b) Eficiência energética, eficiência de hardware e consciência de carbono.
c) Usabilidade, acessibilidade e satisfação.
d) Reutilização, reciclagem e doação.

## Aula 9

**30.** "Impactos incorporados" de um equipamento eletrônico são:
a) Os impactos das etapas anteriores ao uso, como extração, fabricação e transporte.
b) A eletricidade consumida enquanto está ligado.
c) Os impactos do descarte.
d) O consumo em modo de espera.

**31.** Um laboratório tem 20 computadores com potência média de 100 W, usados 4 horas por dia durante 15 dias no mês. A energia consumida no mês é:
a) 8 kWh.
b) 12 kWh.
c) 60 kWh.
d) 120 kWh.

**32.** Sobre consumo de energia e emissões:
a) Dois data centers com o mesmo consumo sempre emitem o mesmo.
b) A emissão é igual à potência nominal da fonte.
c) A emissão associada à eletricidade depende de como ela é produzida; dois data centers com o mesmo consumo podem ter emissões diferentes.
d) A emissão independe da origem da eletricidade.

**33.** Sobre obsolescência e resíduos eletrônicos:
a) Todo defeito demonstra obsolescência programada.
b) Um celular que funciona, mas não recebe atualizações de segurança, não equivale a um aparelho plenamente suportado; funcionamento físico, compatibilidade e segurança são dimensões distintas.
c) Reutilizar e reciclar são ações equivalentes.
d) Doar um equipamento inutilizável resolve o problema do descarte.

## Aula 10

**34.** O efeito rebote ocorre quando:
a) Um ganho de eficiência é parcialmente compensado pelo aumento do uso.
b) O sensor envia leituras repetidas.
c) O consumo total cai mais do que o esperado.
d) O equipamento é substituído por um modelo mais novo.

**35.** Sobre cidades inteligentes:
a) A quantidade de sensores e câmeras instalados mede a qualidade da solução.
b) Importa apenas a dimensão ambiental.
c) É preciso avaliar qual problema foi resolvido, quem foi beneficiado, os custos e os impactos, considerando as dimensões ambiental, social, econômica e de governança.
d) Basta disponibilizar um aplicativo.

**36.** Em um sistema IoT de iluminação, qual descrição está correta?
a) O sensor altera a intensidade da luminária.
b) O atuador mede a luminosidade.
c) O controlador transporta os dados pela rede.
d) O sensor mede a luminosidade, o controlador aplica a regra e o atuador altera a intensidade da luminária.

**37.** Um sensor de nível de água registra 1,20 m, 1,23 m, sem leitura e depois 12,50 m. A conduta mais adequada é:
a) Sinalizar a anomalia e validar, pois pode ser ocorrência real, falha do equipamento ou erro de unidade/transmissão.
b) Concluir imediatamente que há alagamento.
c) Descartar automaticamente o valor.
d) Ignorar a falta de leitura, pois ela indica ausência de risco.

**38.** Uma prefeitura passa a oferecer o agendamento de coleta de móveis exclusivamente por aplicativo. A melhoria proposta na aula foi:
a) Manter só o aplicativo, que é mais sustentável.
b) Integrar aplicativo, site e atendimento assistido ao mesmo sistema de solicitações.
c) Substituir o aplicativo por atendimento só presencial.
d) Exigir acesso aos contatos do celular para identificar o usuário.

## Aulas 11 e 12

**39.** A bioinformática pode ser descrita como:
a) O estudo exclusivo do hardware de laboratórios.
b) A produção artesanal de alimentos por fermentação.
c) O uso de computação, bancos de dados biológicos, algoritmos e IA para armazenar e analisar dados biológicos.
d) A substituição de organismos vivos por programas de computador.

**40.** Um organismo geneticamente modificado (OGM) é:
a) Qualquer organismo cultivado em larga escala.
b) Um alimento produzido por fermentação tradicional.
c) Um organismo criado sem material genético.
d) Um organismo cujo material genético foi alterado por técnicas de engenharia genética.

---

# GABARITO COMENTADO

| Nº | Resp. | Por quê |
|---|---|---|
| 1 | B | IHC avalia se o usuário realiza tarefas com facilidade, e não apenas a beleza. |
| 2 | D | Interação é o processo (sequência de ações, navegação, preenchimento, feedback). Botão, menu e ícone são interface. |
| 3 | A | UX engloba a usabilidade e os sentimentos, percepções e a jornada completa. |
| 4 | C | Paradigmas coexistem e cada um serve melhor a certa situação. |
| 5 | B | CLI exige conhecer a sintaxe (curva maior), mas é eficiente para experientes e automatiza. |
| 6 | A | WIMP = Windows, Icons, Menus, Pointer. |
| 7 | D | Realidade Aumentada sobrepõe informação digital ao ambiente físico. |
| 8 | C | Capacidade motora e precisão são fatores físicos. |
| 9 | A | Reconhecimento (escolher numa lista) reduz a carga de memória. |
| 10 | B | Lei da proximidade: itens próximos formam um grupo. |
| 11 | D | Problema de modelo mental: modelo do usuário ≠ comportamento do sistema. |
| 12 | C | Faltam affordance e significadores que indiquem a ação possível. |
| 13 | B | O PCU parte das necessidades do usuário e é iterativo. |
| 14 | A | Wireframe mostra a estrutura, não a aparência final. |
| 15 | D | A persona é construída a partir de dados reais, não da imaginação. |
| 16 | C | Controle e liberdade do usuário (saída de emergência, desfazer). |
| 17 | B | Impedir o erro antes que ocorra é prevenção de erros. |
| 18 | A | Tarefa adequada tem objetivo real e não ensina o caminho. |
| 19 | D | 18 ÷ 24 × 100 = 75%. |
| 20 | C | AI = organização + rotulagem + navegação + busca; a interface cuida da apresentação. |
| 21 | A | Sitemap = estrutura completa; menu = acesso a parte dela. |
| 22 | B | Breadcrumb é a trilha de navegação. |
| 23 | D | Cada conceito tem uma pergunta orientadora distinta. |
| 24 | C | Princípio Operável (uso por teclado). |
| 25 | B | AA: 4,5:1 texto comum; 3:1 texto grande. |
| 26 | A | `label` com `for`/`id`; placeholder não substitui rótulo. |
| 27 | D | O app apoia a economia de água e também consome recursos próprios. |
| 28 | C | Feedback útil traz unidade, período e referência. |
| 29 | B | Eficiência energética, eficiência de hardware e consciência de carbono. |
| 30 | A | Impactos incorporados vêm de extração, fabricação e transporte. |
| 31 | D | 20 × 0,1 kW × 4 h × 15 dias = 120 kWh (8 kWh é só o consumo de um dia). |
| 32 | C | A emissão depende da forma como a eletricidade é gerada (fator de emissão). |
| 33 | B | Funcionamento, compatibilidade e segurança são dimensões distintas; defeito isolado não prova obsolescência programada. |
| 34 | A | Ganho de eficiência anulado em parte pelo aumento do uso. |
| 35 | C | A quantidade de equipamentos não prova qualidade; avaliar problema, beneficiados, custos, impactos e dimensões. |
| 36 | D | Sensor mede, controlador processa, atuador age. |
| 37 | A | A leitura exige verificação e procedimento de validação; não se conclui nem se descarta automaticamente. |
| 38 | B | Múltiplos canais no mesmo sistema evitam a exclusão digital. |
| 39 | C | Bioinformática une computação e dados biológicos. |
| 40 | D | OGM tem material genético alterado por engenharia genética. |
