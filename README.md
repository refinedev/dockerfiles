<div align="center" style="margin: 30px;">
  <a href="https://refine.dev">
    <img alt="refine logo" src="https://refine.ams3.cdn.digitaloceanspaces.com/readme/refine-readme-banner.png">
  </a>
</div>

<br/>

<div align="center">
  <a href="https://refine.dev">Home Page</a> |
  <a href="https://discord.gg/refine">Discord</a> |
  <a href="https://refine.dev/examples/">Examples</a> |
  <a href="https://refine.dev/blog/">Blog</a> |
  <a href="https://refine.dev/docs/">Documentation</a>

<br/>
<br/>

[![Discord](https://img.shields.io/discord/837692625737613362.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)](https://discord.gg/refine)
[![Twitter Follow](https://img.shields.io/twitter/follow/refine_dev?style=social)](https://twitter.com/refine_dev)

<a href="https://www.producthunt.com/posts/refine-3?utm_source=badge-top-post-badge&utm_medium=badge&utm_souce=badge-refine&#0045;3" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/top-post-badge.svg?post_id=362220&theme=light&period=daily" alt="refine - 100&#0037;&#0032;open&#0032;source&#0032;React&#0032;framework&#0032;to&#0032;build&#0032;web&#0032;apps&#0032;3x&#0032;faster | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a>

</div>

<br/>

<div align="center">refine is an open-source, headless React framework for developers building enterprise internal tools, admin panels, dashboards, B2B applications.

<br/>

It eliminates repetitive tasks in CRUD operations and provides industry-standard solutions for critical project components like **authentication**, **access control**, **routing**, **networking**, **state management**, and **i18n**.

</div>

# Refine Dockerfiles

Here you can find example Refine Dockerfiles for `nextjs`, `remix` and `vite` projects.

Navigate to each folder to see the Dockerfile and their README's.

These Dockerfiles uses [Docker's multi-stage build best practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices) for security and optimizing image sizes.

Final image runs application with `non-root` user and only includes production artifacts.

## Usage

### NextJS

In your project root:

```bash
docker build -t nextjs -f ./Dockerfile .

docker run -p 3000:3000 nextjs
```

### Remix

In your project root:

```bash
docker build -t remix -f ./Dockerfile .

docker run -p 3000:3000 remix
```

### Vite

In your project root:

```bash
docker build -t vite -f ./Dockerfile.nginx .

docker run -p 5173:80 vite

# or

docker build -t vite -f ./Dockerfile.serve .

docker run -p 5173:3000 vite
```

## Documentation

- [Refer to documentation for more info about refine](https://refine.dev/docs/).
- [Step up to refine tutorials](https://refine.dev/docs/tutorial/introduction/index/).
