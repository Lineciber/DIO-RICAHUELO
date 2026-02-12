🛠️ Relatório de Prática: Auditoria e Teste de Intrusão
1. Preparação do Ambiente e Conectividade
A configuração inicial envolveu a comunicação entre o Kali Linux e o alvo. Foi utilizado o comando ip a para identificar a interface de rede e, em seguida, o comando ping -c 3 para validar a comunicação.

O uso do parâmetro -c 3 limita o envio a apenas 3 pacotes, garantindo uma verificação rápida e limpa do status da máquina alvo.

2. Etapa de Enumeração (Nmap)
Para o mapeamento de superfície, foi utilizado o Nmap para realizar o escaneamento de portas.

Foco: Identificação do serviço FTP.

Importância: A versão do sistema encontrada é uma informação sensível e deve ser tratada com sigilo, pois serve de base para a busca de exploits específicos. O próximo passo foi validar se a porta estava aceitando conexões ativas.

3. Ataque de Força Bruta com Medusa
Diante de serviços que exigem autenticação, iniciou-se o processo de força bruta para descobrir credenciais de acesso.
<img width="331" height="80" alt="image" src="https://github.com/user-attachments/assets/c889533c-41cd-475d-8427-a816f5fa39b0" />


Cenário FTP: Realizado o teste com wordlists. A análise reforça que o sucesso depende da qualidade da lista de palavras. No caso de falha, é necessário escalar para listas mais robustas de usuários e senhas.

Cenário Web (Formulário DVWA): A configuração no Medusa foi ajustada com base nos parâmetros de desenvolvedor do navegador.

<img width="760" height="564" alt="image" src="https://github.com/user-attachments/assets/e014041b-0834-4396-a65f-bf69ebed23ff" />


Lógica do Teste: A ferramenta busca por uma "mensagem de erro" na resposta HTTP. Se a resposta não contiver o indicador de falha (ex: "Login incorrect"), o sistema identifica o acesso como bem-sucedido.

4. Conclusão e Mitigação
A prática demonstrou que credenciais fracas são a porta de entrada mais comum para ataques. Para elevar o nível de segurança, as recomendações fundamentais são:

Implementação de políticas de senhas fortes (maiúsculas, minúsculas, números e símbolos).

Inclusão de MFA (Autenticação de Múltiplos Fatores).

Monitoramento de logs para detectar múltiplas tentativas de login em curto espaço de tempo.
