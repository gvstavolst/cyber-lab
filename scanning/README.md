# Varredura de Portas e Servicos

Tecnicas de port scanning e identificacao de servicos em ambientes controlados.

## Comandos Nmap - Referencia Rapida

```bash
# Scan basico de portas
nmap -sV -sC <alvo>

# Scan completo de todas as portas
nmap -p- --min-rate 5000 <alvo>

# Deteccao de sistema operacional
nmap -O <alvo>

# Scan UDP
nmap -sU --top-ports 20 <alvo>

# Output para arquivo
nmap -sV -oN scan_resultado.txt <alvo>
```

## Portas comuns e servicos associados

| Porta | Protocolo | Servico |
|---|---|---|
| 21 | TCP | FTP |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 80 | TCP | HTTP |
| 443 | TCP | HTTPS |
| 445 | TCP | SMB |
| 3306 | TCP | MySQL |
| 3389 | TCP | RDP |
