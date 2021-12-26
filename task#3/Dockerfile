FROM node:14.15.5-slim as builder

WORKDIR /usr/src/app 
COPY ./src ./

# Add app config and secrets and Install tools and Build app
RUN touch ./src/environments/environment.ts 
COPY ./config/environment.prod.ts ./src/environments/ 
RUN npm install -g @angular/cli 
RUN npm ci   
RUN npm --verbose install 
RUN ng build --prod --output-path /home/user/website/

FROM nginx:1.19.7-alpine

# Add nginx configs and Add search engines configs and Add well known mobile links configs and Add app
COPY ./config/nginx.conf /etc/nginx/ 
COPY ./config/robots.txt /usr/share/nginx/html  
COPY ./config/sitemap.xml /usr/share/nginx/html 
COPY ./config/sitemap-static.xml /usr/share/nginx/html 
COPY ./config/apple-app-site-association /usr/share/nginx/html/.well-known/ 
COPY ./config/assetlinks.json /usr/share/nginx/html/.well-known/ 
COPY --from=builder /home/user/website/ /usr/share/nginx/html/



 



 




