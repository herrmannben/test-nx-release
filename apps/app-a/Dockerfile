# This file is generated by Nx.
#
# Build the docker image with `npx nx docker-build app-a`.
# Tip: Modify "docker-build" options in project.json to change docker build args.
#
# Run the container with `docker run -p 3000:3000 -t app-a`.
FROM docker.io/node:lts-alpine

ENV HOST=0.0.0.0
ENV PORT=3000

WORKDIR /app

RUN addgroup --system app-a && \
          adduser --system -G app-a app-a

COPY dist/apps/app-a app-a
RUN chown -R app-a:app-a .

# You can remove this install step if you build with `--bundle` option.
# The bundled output will include external dependencies.
RUN npm --prefix app-a --omit=dev -f install

CMD [ "node", "app-a" ]
