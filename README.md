# AD3 · Laboratório prático com Docker

**Tópicos Avançados em Programação Web (STC0331)** · Tecnologia em Sistemas para Internet · IFC Camboriú · 2026.1
Autor: Jhonn Lenon da Silva Gonçalves

Roteiro prático de Docker feito no **GitHub Codespaces**: do primeiro container até um servidor
**NGINX** servindo uma página própria por volume. Cada passo tem o comando usado e o print do resultado.

📄 **Relatório completo:** [relatorio-ad3-docker.md](relatorio-ad3-docker.md)

## O que foi praticado

1. Conferir a instalação (`docker version`) e rodar o `hello-world`
2. Subir um container **NGINX** com porta publicada (`docker run -d -p 8080:80 nginx`)
3. Listar, parar e reiniciar containers (`docker ps`, `docker stop`, `docker start`)
4. Servir uma página própria ([index.html](index.html)) montando um **volume** no NGINX
5. Entrar no container com shell interativo (`docker exec -it ... sh`)
6. Limpar containers e imagens (`docker rm`, `docker rmi`)

## Como reproduzir

```bash
docker run -d --name meu-nginx -p 8080:80 \
  -v "$PWD/index.html:/usr/share/nginx/html/index.html:ro" nginx
# abrir http://localhost:8080
docker rm -f meu-nginx
```

## Estrutura

```
index.html                página servida pelo NGINX
relatorio-ad3-docker.md   relatório da atividade (13 etapas + conclusão)
img/                      prints de cada etapa
```
