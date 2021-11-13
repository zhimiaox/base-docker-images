#### 纸喵软件官方基础镜像包

```dockerfile
FROM zhimiao/hugo:0.8.92 AS build

ADD . /zhimiao

RUN hugo

FROM nginx:latest AS prod

COPY --from=build /zhimiao/public /usr/share/nginx/html
```