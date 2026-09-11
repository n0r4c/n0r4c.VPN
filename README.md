# NØR4C.VPN

<p align="center">
  <img src="https://img.shields.io/badge/NØR4C-VPN-ab0000?style=for-the-badge&labelColor=000000">
  <img src="https://img.shields.io/badge/WireGuard-VPN-white?style=for-the-badge&labelColor=000000">
  <img src="https://img.shields.io/badge/Cyber%20Security-LAB-ab0000?style=for-the-badge&labelColor=000000">
  <img src="https://img.shields.io/badge/Linux-LAB-white?style=for-the-badge&labelColor=000000">
</p>

<h3 align="center">
  Your network. Your tunnel. Your rules.
</h3>

<p align="center">
  Laboratório de VPN, Redes e CyberSec desenvolvido por <b>NØR4C</b>.
</p>

---

## ◉ SOBRE

O **NØR4C.VPN** é um projeto educacional e prático criado para estudar e implementar uma infraestrutura de VPN utilizando **WireGuard**, Linux e conceitos modernos de segurança de redes.

O projeto não tem como objetivo apenas "instalar uma VPN".

A proposta é entender o que existe por trás de uma conexão segura:

<pre>
CLIENTE
   │
   │ Internet
   ▼
┌─────────────────────┐
│    NØR4C.VPN        │
│                     │
│     WireGuard       │
│     Firewall        │
│     Routing         │
│     DNS             │
│     Monitoring      │
└──────────┬──────────┘
           │
           │ Tunnel
           ▼
┌─────────────────────┐
│    HOME NETWORK     │
│                     │
│ NAS                 │
│ Raspberry Pi        │
│ Servers             │
│ IoT                 │
│ Workstations        │
└─────────────────────┘
</pre>

A partir dessa infraestrutura, estudaremos:

- Redes
- TCP/IP
- UDP
- NAT
- Routing
- DNS
- Firewall
- VPN
- Criptografia
- WireGuard
- Linux
- Hardening
- Monitoramento
- Segmentação
- Zero Trust
- Segurança de endpoints
- Detecção de anomalias
- Análise de tráfego

---

## ◉ OBJETIVOS

O NØR4C.VPN possui quatro objetivos principais:

### 01 — APRENDER

Entender como redes e VPNs funcionam internamente.

### 02 — IMPLEMENTAR

Construir uma VPN funcional utilizando infraestrutura real.

### 03 — PROTEGER

Aplicar princípios de CyberSec na infraestrutura.

### 04 — EXPERIMENTAR

Transformar a VPN em um laboratório para estudar segurança de redes.

---

## ◉ STACK

### Operating System

**Linux**

### VPN

**WireGuard**

### Networking

- IPv4
- IPv6
- UDP
- NAT
- Routing
- DNS

### Security

- Firewall
- Hardening
- Key Management
- Least Privilege
- Segmentation
- Monitoring

### Tools

- `ip`
- `ss`
- `ping`
- `traceroute`
- `dig`
- `tcpdump`
- `nmap`
- `wg`

---

## ◉ ARQUITETURA

A arquitetura base do projeto:

<pre>
                         INTERNET
                             │
                             │
                     Public Network
                             │
                             ▼
                 ┌─────────────────────┐
                 │    NØR4C.VPN        │
                 │                     │
                 │      Linux          │
                 │      WireGuard      │
                 │      Firewall       │
                 │      DNS            │
                 └──────────┬──────────┘
                            │
                    Encrypted Tunnel
                            │
             ┌──────────────┴──────────────┐
             │                             │
             ▼                             ▼
      ┌─────────────┐               ┌─────────────┐
      │ NØR4C.NAS   │               │ HOME-LAB    │
      │             │               │             │
      │ Storage     │               │ Servers     │
      │ Backup      │               │ Raspberry   │
      └─────────────┘               └─────────────┘
             │
             ▼
      ┌─────────────┐
      │ IoT / LAN   │
      └─────────────┘
</pre>

---

## ◉ COMO A VPN FUNCIONA

Uma VPN cria uma interface de rede virtual capaz de transportar tráfego através de uma conexão criptografada.

Exemplo:

<pre>
Seu dispositivo
10.8.0.2
   │
   │
   │ WireGuard
   │
   ▼
10.8.0.1
NØR4C.VPN SERVER
</pre>

O cliente não precisa necessariamente conhecer toda a infraestrutura interna.

Ele conhece apenas o peer e as rotas permitidas.

---

## ◉ WIREGUARD

O NØR4C.VPN utiliza **WireGuard** como tecnologia principal.

O WireGuard trabalha com criptografia moderna e uma arquitetura baseada em:

<pre>
Private Key
     │
     ▼
Public Key
     │
     ▼
Peer
     │
     ▼
Encrypted Tunnel
</pre>

Cada dispositivo possui sua própria identidade criptográfica.

### SERVER

- PrivateKey
- PublicKey
- Address
- ListenPort

### CLIENT

- PrivateKey
- PublicKey
- Address
- Endpoint
- AllowedIPs

---

## ◉ MODELO DE PEERS

A infraestrutura será baseada em peers independentes.

<pre>
                 NØR4C.VPN
                     │
        ┌────────────┼────────────┐
        │            │            │
        ▼            ▼            ▼
     LAPTOP       PHONE        RPI
      Peer 01      Peer 02     Peer 03
</pre>

Cada peer possui:

- Chave privada
- Chave pública
- IP VPN
- Rotas permitidas
- Endpoint
- Política de acesso

Isso permite revogar um dispositivo sem precisar alterar toda a infraestrutura.

---

## ◉ PLANO DE ENDEREÇAMENTO

Exemplo utilizado no laboratório:

### VPN NETWORK

`10.8.0.0/24`

### SERVIDOR

`10.8.0.1`

### CLIENTES

- `10.8.0.2`
- `10.8.0.3`
- `10.8.0.4`
- `10.8.0.5`

Exemplo:

<pre>
10.8.0.1  → Server
10.8.0.2  → Notebook
10.8.0.3  → Smartphone
10.8.0.4  → Raspberry Pi
</pre>

---

## ◉ FUNDAMENTOS DE CYBER SEC

O NØR4C.VPN será utilizado como laboratório para estudar os principais conceitos de segurança de redes.

### CIA TRIAD

<pre>
             SECURITY
                 │
       ┌─────────┼─────────┐
       │         │         │
       ▼         ▼         ▼
 CONFIDENTIAL  INTEGRITY  AVAILABILITY
</pre>

### Confidentiality

Somente entidades autorizadas devem acessar determinadas informações.

### Integrity

Os dados não devem ser modificados de forma não autorizada.

### Availability

Os serviços devem permanecer disponíveis quando necessários.

---

## ◉ THREAT MODEL

Antes de proteger uma infraestrutura precisamos entender contra quem estamos protegendo.

<pre>
                 INTERNET
                     │
              ┌──────┴──────┐
              │             │
              ▼             ▼
         Legitimate      Attacker
           Client
              │             │
              ▼             ▼
        ┌────────────────────────┐
        │      NØR4C.VPN         │
        └────────────────────────┘
                     │
                     ▼
                  HOME LAB
</pre>

Possíveis ameaças estudadas:

- Port scanning
- Credential attacks
- Misconfiguration
- Traffic interception
- DNS leakage
- Unauthorized access
- Rogue devices
- Exposed services
- Weak firewall rules
- Compromised endpoints

---

## ◉ ATTACK SURFACE

Um dos objetivos do projeto será reduzir a superfície de ataque.

### Antes

<pre>
INTERNET
   │
   ├── SSH
   ├── SMB
   ├── HTTP
   ├── NAS
   ├── Database
   └── Admin Panel
</pre>

### Depois

<pre>
INTERNET
   │
   ▼
VPN
   │
   ▼
AUTHORIZED NETWORK
   │
   ├── SSH
   ├── NAS
   ├── HTTP
   └── Internal Services
</pre>

A ideia é não expor serviços internos desnecessariamente.

---

## ◉ FIREWALL

O firewall será uma camada fundamental.

Arquitetura:

<pre>
                INTERNET
                    │
                    ▼
             ┌────────────┐
             │ FIREWALL   │
             └─────┬──────┘
                   │
          ┌────────┴────────┐
          │                 │
       ALLOW              DROP
          │                 │
          ▼                 ▼
     Authorized         Unauthorized
       Traffic             Traffic
</pre>

### Princípio utilizado

**Default Deny**

Sempre que possível:

- **ALLOW explicitly**
- **DROP everything else**

---

## ◉ PRINCÍPIO DO MENOR PRIVILÉGIO

Cada peer deve possuir somente o acesso necessário.

### Exemplo

<pre>
PHONE
VPN
 │
 ├── DNS
 ├── NAS
 └── HOME SERVER
X Database
X Admin Panel
X IoT Network
</pre>

Enquanto um administrador pode possuir:

<pre>
ADMIN
VPN
 │
 ├── DNS
 ├── NAS
 ├── Servers
 ├── Monitoring
 └── Management
</pre>

---

## ◉ SEGMENTAÇÃO

Uma evolução do projeto será separar a rede em diferentes segmentos.

<pre>
                NØR4C.VPN
                    │
          ┌─────────┼─────────┐
          │         │         │
          ▼         ▼         ▼
        ADMIN      LAB       IoT
       10.10.0    10.20.0   10.30.0
</pre>

Isso reduz o impacto de um possível comprometimento.

Exemplo:

<pre>
IoT DEVICE
    │
    X
    │
    X → ADMIN NETWORK
</pre>

---

## ◉ DNS SECURITY

DNS também fará parte do laboratório.

Estudaremos:

- DNS resolution
- DNS over HTTPS
- DNS over TLS
- DNS leaks
- Internal DNS
- Split DNS
- DNS filtering
- DNS logging

Arquitetura:

<pre>
CLIENT
  │
  ▼
VPN
  │
  ▼
NØR4C DNS
  │
  ├── Internal Domains
  │
  └── External Resolution
</pre>

---

## ◉ MONITORAMENTO

Uma infraestrutura segura também precisa ser observável.

Ferramentas estudadas:

- `wg`
- `ip`
- `ss`
- `journalctl`
- `tcpdump`
- `dig`
- `ping`
- `traceroute`
- `nmap`

Exemplo:

`wg show`

Possibilita verificar informações importantes do túnel.

---

## ◉ NØR4C.VPN CHECK

O projeto terá uma ferramenta própria para verificar a saúde da VPN.

Exemplo:

<pre>
╔══════════════════════════════════════╗
║          NØR4C.VPN CHECK             ║
╠══════════════════════════════════════╣
║ Interface       ✓ UP                 ║
║ WireGuard       ✓ ACTIVE             ║
║ Handshake       ✓ OK                 ║
║ Encryption      ✓ ACTIVE             ║
║ DNS             ✓ PROTECTED          ║
║ IPv4 Routing    ✓ OK                 ║
║ IPv6 Routing    ✓ CHECKED            ║
║ Firewall        ✓ ACTIVE             ║
║ Peers           ✓ 3 ACTIVE           ║
╠══════════════════════════════════════╣
║ STATUS: SECURE                       ║
╚══════════════════════════════════════╝
</pre>

O script ficará em:

`scripts/vpn-check.sh`

---

## ◉ TESTES DE SEGURANÇA

O laboratório também terá uma seção dedicada a validação.

### Network Discovery

Identificar hosts e serviços dentro da infraestrutura autorizada.

`nmap`

### Traffic Analysis

Inspecionar tráfego:

`tcpdump`

### Socket Analysis

Verificar serviços escutando:

`ss`

### DNS Analysis

Testar resolução:

`dig`

### VPN Analysis

Verificar peers:

`wg`

Todos os testes devem ser realizados somente em ativos próprios ou explicitamente autorizados.

---

## ◉ HARDENING

Depois da VPN funcionando, inicia a fase de hardening.

### Checklist

- [ ] Atualizar sistema
- [ ] Atualizar WireGuard
- [ ] Configurar firewall
- [ ] Remover serviços desnecessários
- [ ] Desabilitar login SSH por senha
- [ ] Utilizar autenticação por chave
- [ ] Restringir portas
- [ ] Restringir peers
- [ ] Configurar DNS
- [ ] Validar routing
- [ ] Monitorar logs
- [ ] Configurar backups
- [ ] Revisar permissões
- [ ] Documentar mudanças

---

## ◉ SSH HARDENING

Quando SSH fizer parte da infraestrutura:

<pre>
Internet
   │
   X
   │
   ▼
VPN
   │
   ▼
SSH
</pre>

A administração pode ser limitada à interface VPN.

Exemplo conceitual:

<pre>
SSH
│
├── VPN subnet → ALLOW
│
└── Internet → DROP
</pre>

---

## ◉ KEY MANAGEMENT

As chaves privadas são informações extremamente sensíveis.

### Nunca faça

- ❌ commit private keys
- ❌ enviar private keys pelo GitHub
- ❌ colocar private keys em screenshots
- ❌ compartilhar configs reais
- ❌ reutilizar a mesma identidade em vários dispositivos

### Estrutura recomendada

<pre>
configs/
└── examples/
    ├── server.conf.example
    └── client.conf.example
</pre>

Configurações reais permanecem fora do repositório.

---

## ◉ GIT SECURITY

O próprio GitHub fará parte do laboratório.

Antes de qualquer commit:

<pre>
CHECK
├── Private Keys
├── Tokens
├── Passwords
├── API Keys
├── Credentials
├── IP information
└── Secrets
</pre>

Exemplo de arquivos que **não devem entrar no repositório**:

- `*.key`
- `*.pem`
- `*.secret`
- `.env`
- `*.conf`

Use:

`.gitignore`

para reduzir o risco de vazamento acidental.

> O `.gitignore` é uma camada de prevenção, não uma garantia de segurança. Segredos que já foram commitados podem permanecer no histórico do Git.

---

## ◉ LABORATÓRIO

O projeto será dividido em níveis.

### LEVEL 01 — NETWORK

Fundamentos:

- IPv4
- IPv6
- Subnet
- Gateway
- NAT
- Routing
- UDP
- TCP
- DNS

---

### LEVEL 02 — VPN

WireGuard:

- Installation
- Keys
- Interfaces
- Peers
- Handshake
- AllowedIPs
- Endpoint
- PersistentKeepalive

---

### LEVEL 03 — SERVER

Construção do servidor:

<pre>
Linux
  │
  ├── WireGuard
  ├── Firewall
  ├── DNS
  └── Monitoring
</pre>

---

### LEVEL 04 — CLIENT

Configuração:

- Notebook
- Smartphone
- Raspberry Pi
- Desktop
- Server

Cada dispositivo terá seu próprio peer.

---

### LEVEL 05 — ROUTING

Estudo de:

<pre>
Client
  │
  ▼
VPN
  │
  ├── Internet
  ├── LAN
  ├── NAS
  └── Services
</pre>

---

### LEVEL 06 — SECURITY

Aplicação de:

- Firewall
- Hardening
- Segmentation
- Least Privilege
- Key Management
- Monitoring

---

### LEVEL 07 — RED TEAM / BLUE TEAM

O laboratório poderá evoluir para exercícios controlados.

### RED TEAM

Objetivo:

- Discover
- Enumerate
- Analyze
- Attempt Access

### BLUE TEAM

Objetivo:

- Detect
- Analyze
- Block
- Harden
- Recover

Tudo realizado exclusivamente em ambientes próprios ou explicitamente autorizados.

---

## ◉ CYBER SECURITY LAB

Uma das evoluções do projeto será transformar a VPN em uma pequena infraestrutura de Cyber Security.

<pre>
                    NØR4C.VPN
                        │
        ┌───────────────┼───────────────┐
        │               │               │
        ▼               ▼               ▼
     NETWORK          SECURITY        MONITOR
        │               │               │
        ▼               ▼               ▼
      DNS            Firewall          Logs
      DHCP           IDS/IPS           Alerts
      Routing        Hardening         Metrics
</pre>

---

## ◉ ZERO TRUST

Em fases futuras:

> **Never Trust. Always Verify.**

O fato de um dispositivo estar conectado à VPN não significa automaticamente que ele possui acesso total.

Modelo:

<pre>
DEVICE
  │
  ▼
IDENTITY
  │
  ▼
POLICY
  │
  ▼
RESOURCE
</pre>

---

## ◉ ROADMAP

- [x] Project initialization
- [x] README
- [ ] Network fundamentals
- [ ] WireGuard fundamentals
- [ ] Linux server
- [ ] VPN server
- [ ] VPN client
- [ ] Routing
- [ ] Firewall
- [ ] DNS
- [ ] Hardening
- [ ] Monitoring
- [ ] VPN CHECK
- [ ] Security tests
- [ ] Segmentation
- [ ] Zero Trust
- [ ] Red Team / Blue Team Lab
- [ ] NØR4C Security Dashboard

---

## ◉ ESTRUTURA DO PROJETO

<pre>
NØR4C.VPN/
│
├── README.md
│
├── docs/
│   ├── 01-fundamentos.md
│   ├── 02-wireguard.md
│   ├── 03-servidor.md
│   ├── 04-clientes.md
│   ├── 05-routing.md
│   ├── 06-dns.md
│   ├── 07-firewall.md
│   ├── 08-hardening.md
│   ├── 09-monitoramento.md
│   └── 10-security-lab.md
│
├── configs/
│   └── examples/
│
├── scripts/
│   └── vpn-check.sh
│
├── diagrams/
│
├── LICENSE
│
└── .gitignore
</pre>

---

## ◉ CHECKLIST FINAL

### NETWORK

- [ ] IP addressing
- [ ] Routing
- [ ] NAT
- [ ] DNS
- [ ] Firewall

### VPN

- [ ] WireGuard installed
- [ ] Server configured
- [ ] Client configured
- [ ] Handshake verified
- [ ] Routing verified

### SECURITY

- [ ] Firewall enabled
- [ ] Services minimized
- [ ] SSH hardened
- [ ] Keys protected
- [ ] Logs monitored
- [ ] Network segmented

### TESTING

- [ ] Port scan
- [ ] Service enumeration
- [ ] DNS test
- [ ] Traffic inspection
- [ ] VPN validation
- [ ] Firewall validation

---

## ◉ PRINCÍPIOS NØR4C

<pre>

CONHEÇA A REDE.
ENTENDA A SUPERFÍCIE DE ATAQUE.
MINIMIZE A CONFIANÇA.
VERIFIQUE TUDO.
REGISTRE O QUE IMPORTA.
PROTEJA AS CHAVES. 
DOCUMENTE TUDO.

</pre>

---

## ◉ LAB RULES

Este projeto foi desenvolvido para aprendizado prático de **Cyber Security**.

Os exercícios de segurança devem ser executados somente:

- em equipamentos próprios;
- em laboratórios controlados;
- em ambientes de CTF;
- ou com autorização explícita do proprietário.

A finalidade do projeto é aprender a **construir, analisar, testar e defender infraestrutura de rede**.

Nenhum conteúdo deste projeto deve ser utilizado para obter acesso não autorizado a sistemas, redes, dispositivos ou informações de terceiros.

---

## ◉ ECOSSISTEMA NØR4C

O NØR4C.VPN foi pensado para fazer parte de um ecossistema maior:

<pre>
                    NØR4C
                      │
       ┌──────────────┼──────────────┐
       │              │              │
       ▼              ▼              ▼
   NØR4C.NAS      NØR4C.VPN      NØR4C.DNS
       │              │              │
       └──────────────┼──────────────┘
                      │
                      ▼
               NØR4C.HOME-LAB
                      │
                      ▼
             NØR4C.SECURITY-LAB
                      │
                      ▼
               NØR4C.CYBER-LAB
</pre>

A ideia é construir uma infraestrutura completa, modular e documentada.

---

## ◉ NØR4C

> **NO RESTRICTION.**

Conhecimento deve ser explorado.

Infraestrutura deve ser compreendida.

Segurança deve ser construída.

---

<p align="center">
  <b>NØR4C.VPN</b>
  <br>
  <i>Your network. Your tunnel. Your rules.</i>
</p>