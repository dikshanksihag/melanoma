# ============================================================
# Frontend Dockerfile
# Phase 4 | nginx serving static HTML/CSS/JS
# ============================================================

FROM nginx:alpine

# Copy static files to nginx web root
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY . /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]