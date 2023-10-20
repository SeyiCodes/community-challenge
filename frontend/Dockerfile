FROM node:14-alpine AS builder

WORKDIR /app

# Install dependencies
COPY . .

RUN yarn install && yarn build

# Copy the application source

# CMD [ "npm", "run", "serve" ]


FROM nginx:stable-alpine

WORKDIR /usr/share/nginx/html
# Remove default nginx static assets

RUN rm -rf ./*

COPY nginx.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /app/dist .

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]