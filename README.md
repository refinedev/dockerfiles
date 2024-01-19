# Refine Dockerfiles

Here you can find example Refine Dockerfiles for `nextjs`, `remix` and `vite` projects.

Navigate to each folder to see the Dockerfile and their README's.

These Dockerfiles uses [Docker's multi-stage build best practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices) for security and optimizing image sizes.

Final image runs application with `non-root` user and doesn't include `devDependencies`.

## Running examples

### NextJS

```bash
cd nextjs/example

docker build -t nextjs -f ../Dockerfile .

docker run -p 3000:3000 nextjs
```

### Remix

```bash
cd remix/example

docker build -t remix -f ../Dockerfile .

docker run -p 3000:3000 remix
```

### Vite

```bash
cd vite/example

docker build -t vite -f ../Dockerfile.nginx .

docker run -p 5173:80 vite

# or

docker build -t vite -f ../Dockerfile.serve .

docker run -p 5173:3000 vite
```
