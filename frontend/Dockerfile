FROM node:lts-alpine AS builder

WORKDIR /app

# Install dependencies
COPY . .


RUN npm ci


# Copy the application source

RUN npm run build

# CMD [ "npm", "run", "serve" ]


FROM nginx:stable-alpine

WORKDIR /usr/share/nginx/html
# Remove default nginx static assets
RUN rm -rf ./*

COPY nginx.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /app/dist .

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]