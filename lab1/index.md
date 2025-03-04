## Visão Geral
Este laboratório introduz os alunos ao Border Gateway Protocol (BGP), um protocolo crítico para o roteamento entre domínios na internet. Os alunos configurarão uma topologia de múltiplos roteadores para explorar o BGP externo (eBGP), o BGP interno (iBGP) e conceitos chave do BGP, como o atributo next-hop-self.

O laboratório inclui um desafio de solução de problemas para reforçar o aprendizado e uma tarefa de automação de rede usando FastAPI e NAPALM para recuperar informações de vizinhos BGP, demonstrando práticas modernas de rede.

## Topologia
![bgp_fundamentals_diagram](https://ubjpcyfllztpftxqaldu.supabase.co/storage/v1/object/sign/img/labs/lab/md/bgp_fundamentals_diagram.webp?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1cmwiOiJpbWcvbGFicy9sYWIvbWQvYmdwX2Z1bmRhbWVudGFsc19kaWFncmFtLndlYnAiLCJpYXQiOjE3NDA5NDA5NTUsImV4cCI6MTg5ODYyMDk1NX0.Eun52MyKJbWMVVXHM9eDiwCbHkVYKaLv1ZH1aSSOGLg)
O laboratório utiliza uma topologia de três roteadores para demonstrar interações de eBGP e iBGP:

    R1 (AS 100): Um roteador atuando como o gateway entre AS 100 e AS 200.
    R2 (AS 100): Um roteador interno ao AS 100, conectado apenas ao R1.
    R3 (AS 200): Um roteador em um sistema autônomo diferente, conectado ao R1.

### Conexões
    R1 eth1 <-> R3 eth1: Peering eBGP entre AS 100 e AS 200.
    R1 eth2 <-> R2 eth1: Peering iBGP dentro do AS 100.

### Endereçamento IP
Cada roteador possui uma interface loopback0 para identificação e anúncio de rotas:

    R1: 1.1.1.1/32 (Loopback0)
    R2: 2.2.2.2/32 (Loopback0)
    R3: 3.3.3.3/32 (Loopback0)

Boa sorte e bons estudos!