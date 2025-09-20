# Lettres de motivation

## run a build

with this config,

```yaml
services:
  latex:
    image: texlive/texlive
    volumes:
      - .:/data
    working_dir: /data
    command: [ "tail", "-f", "/dev/null" ] #infinite loop to keep the container running
```

> u can `docker compose up -d` in the root folder

run,

```bash
docker-compose exec latex latexmk -pdf -interaction=nonstopmode -synctex=1 -outdir=build ./example/main.tex
```
