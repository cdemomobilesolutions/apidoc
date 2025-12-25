# apidoc
cDemo API Docs

Build with Docker
-----------------

```bash
docker build -t cdemo-apidoc .
```

```bash
docker run -it --rm -v $(pwd):/docs cdemo-apidoc make html
```
