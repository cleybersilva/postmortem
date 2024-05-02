# Post-mortems

É conjunto de atividades executadas após um **incidente/falha** com o objetivo de **comunicar** as causas do incidente e identificar **lições aprendidas** e **pontos de melhorias**.

Ressalva: Tem por objetivo não apontar culpados (blameless).

## Descrição breve e amigável do incidente

linguagem menos técnica, que seus clientes/usuários entenderiam.

## Causas técnicas e organizacionais

Exemplo técnico:

> Um bug introduzido no PR #1234567 causou uso excessivo de memória do componente X, sobrecarregando o servidor.

Exemplo organizacional:

> Os alertas foram disparados mas ninguém estava monitorando o dashboard naquele momento.

## Dados de monitoramento

incluir também monitoramento ausente, que teria ajudado a identificar o problema.

## Linha do tempo de evento

incluir também tentativas inócuas de resolver o problema. Detalhes de coisas de usuários e sistemas. Horário UTC.

Exemplo:

- 2024-05-10 16:26 kefferson avisou aos Devs que ele recebeu emails de onboard, onde apenas ele deveria receber

## Consequências do incidente

duração do incidente, usuários afetados, dados perdidos ou vazados.

## Ações recomendadas

cada ação deve ser mapeada para um card/issue. ações concluídas durante o processo de postmortem devem ser ressaltadas no relatório.

## Anexos: com detalhes técnicos

mensagens de log, gráficos, erros, capturas de tela, comandos executados.

## Processo de post-mortem Stack Overflow de exomplo

Durante o incidente:

- **avaliar se precisa ou nao de escrever um postmortem**
- envolvidos entram numa reunião, divulgada para toda a empresa (dev, infra)
- imediatamente um documento em branco é criado e compartilhado com todos para coleta de informações (anotar timeline)
- foco deve estar em resolver o problema, correções de longo prazo devem ser deixadas para depois.

Depois do incidente:

- Escrever relatório de postmortem, a partir do documento criado durante a investigação
- para cada item de **ações recomendadas** criar um bug/issue/card
- divulgar relatório internamente
- caso faça sentido, editar e divulgar publicamente

Template do relatório de postmortem

- Descrição do incidente
- resumo executivo (o que chefe quer saber)
- Linha do tempo de eventos (o mais preciso possível)
- Avaliação (o que deu certo e o que errado)
- Ações recomendadas (curto e longo prazo, marcar ações realizadas, criar issue para cada ação)
- Anexos: gráficos de efeitos observados

## Resumo para os executivos/liderança

| | |
| ----------------------- | ----------- |
| Incidente time-frame    | 2024-05-02 16:28 until 2024-05-05 17:15 UTC      |
| Worst-case incidente window   | ~14 minutes (between sending the emails and disabling the feature toggle), 16 hours (until we cleaned the email queue)        |
| Assets/users affected      | Stack overflow for team users       |
| Incidente Type   | Software failure        |
| Action necessary      | See list of recommended action below      |

## Referencias

- [A List of Post-mortems](https://github.com/danluu/post-mortems)
- [Sobre Post-mortems DNAD2020](https://www.youtube.com/watch?v=SmQrHlqDw7U&feature=youtu.be&t=11996)
