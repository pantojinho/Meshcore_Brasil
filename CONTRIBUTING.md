# Como contribuir para o MeshCore Brasil

Antes de enviar qualquer pull request (PR), por favor revise as informações a seguir.

PRs não solicitados, sem discussão prévia ou issues abertas, podem ser
rejeitados. O mesmo vale para alterações muito abrangentes (ex.: 100 arquivos
modificados) ou que cubram muitas mudanças separadas. Se as alterações forem
claramente geradas por IA, também poderão ser rejeitadas. [Saiba mais](#uso-de-ia)

## Checklist de Primeiros Passos

### **Encontrou um bug?**

* **Certifique-se de que o bug ainda não foi reportado** pesquisando no GitHub em [Issues](https://github.com/pantojinho/Meshcore_Brasil/issues).

* Se você não encontrar uma issue aberta que aborde o problema, [abra uma nova](https://github.com/pantojinho/Meshcore_Brasil/issues/new).
Certifique-se de incluir um **título e uma descrição clara**, o máximo de
informações relevantes possível, e um **exemplo de código** ou um **caso de
teste executável** demonstrando o comportamento esperado que não está ocorrendo.
Você também pode incluir screenshots ou vídeo.

* NÃO comece a trabalhar e envie um PR neste momento; por favor, discuta o
problema e seu plano de implementação primeiro.

### **Você corrigiu espaços em branco, formatou código ou fez uma alteração puramente cosmética?**

Alterações de natureza cosmética que não adicionam nada substancial à
estabilidade, funcionalidade ou testabilidade da aplicação geralmente não serão
aceitas.

### **Você pretende adicionar uma nova feature ou alterar uma existente?**

* Sugira sua mudança em uma nova issue como um pedido de feature.

* NÃO comece a trabalhar e envie um PR neste momento; por favor, discuta a
mudança e seu plano de implementação primeiro.

* Após ser decidido que a feature ou mudança se encaixa nos objetivos do
projeto, você pode começar a trabalhar ou abrir um PR se já tiver começado.

## Enviando seu patch

* Todas as alterações devem ser baseadas na branch `dev`. Ao criar seu PR,
certifique-se de alterar o destino para merge em dev, e ao começar o trabalho
em uma nova branch, certifique-se de iniciar a partir do `dev` mais recente.

* Certifique-se de que a descrição do PR descreva claramente o problema e a
solução. Inclua o número da issue relevante, se aplicável.

* O PR deve conter **apenas um commit**; a mensagem do commit deve ter um
título claro seguido de uma nova linha e, em seguida, uma breve descrição, se
necessário. PRs com múltiplos commits serão squashed em um só antes do merge,
se necessário. Consulte
[Git Mastery](https://git-mastery.org/lessons/commitMessage/) para mais
informações sobre boas mensagens de commit.

* **Antes de fazer commit das alterações** em sua branch, certifique-se de
executar tanto `dart format .` quanto `flutter analyze`. As verificações de
desenvolvimento contínuo falharão se os problemas não forem resolvidos
previamente.

## Uso de IA

Todos adoram um pouco de ajuda; agentes de IA são uma ferramenta no cinto de
muitos de nós. O projeto não é anti-IA.

No entanto, existem alguns limites para o uso aceitável. De modo geral:

* Todo código gerado por IA deve ser cuidadosamente revisado pelo contribuidor.

* As alterações devem ser bem controladas para não modificar nada fora do
escopo do patch, correção de bug, etc.

* O contribuidor deve ter uma boa compreensão do que o código faz e como a
aplicação funciona, para conseguir gerenciar o agente de forma eficaz.
