# Vite Dockerfile

### Usage

Vite build command exports static files to `dist` folder. We can use any static file server to serve these files.

We have 2 examples:

- `Dockerfile.serve`: Uses `serve` package. https://www.npmjs.com/package/serve
- `Dockerfile.nginx`: Uses nginx with Gzip config for better performance.

```bash
docker build -t vite -f ./Dockerfile.nginx .

docker run -p 5173:80 vite

# or

docker build -t vite -f ./Dockerfile.serve .

docker run -p 5173:3000 vite
```
