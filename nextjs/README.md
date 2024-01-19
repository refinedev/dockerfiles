# NextJS Dockerfile

### Usage

First, we need to add `output: "standalone"` to `next.config.js` file.

This will create a folder at `.next/standalone` at build step, which Dockerfile will use to serve the image.

See [NextJS docs](https://nextjs.org/docs/pages/api-reference/next-config-js/output#automatically-copying-traced-files) for more info.

```bash
docker build -t nextjs -f Dockerfile .

docker run -p 3000:3000 nextjs
```
