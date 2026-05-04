# Escalacao de Privilegios no Linux

Anotacoes de referencia para tecnicas de privilege escalation em ambientes Linux.

## Enumeracao inicial

```bash
# Usuario atual e grupos
id
whoami
groups

# Sistema operacional
uname -a
cat /etc/os-release

# Processos em execucao
ps aux

# Servicos ativos
systemctl list-units --type=service
```

## Vetores comuns

**SUID binaries**
```bash
find / -perm -4000 -type f 2>/dev/null
```

**Sudo permissions**
```bash
sudo -l
```

**Cron jobs**
```bash
cat /etc/crontab
ls -la /etc/cron*
```

**Arquivos com permissao de escrita**
```bash
find / -writable -type f 2>/dev/null | grep -v proc
```

**Senhas em arquivos de configuracao**
```bash
grep -r "password" /etc --include="*.conf" 2>/dev/null
grep -r "passwd" /home 2>/dev/null
```

## Ferramentas automatizadas

- LinPEAS
- LinEnum
- linux-exploit-suggester
