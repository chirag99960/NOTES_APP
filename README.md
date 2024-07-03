
# NOTES APPLICATION 

In our NOTES APPLICATION, we're deploying it via Dockerfile without utilizing the default port. Instead, we aim to host this application using an NGINX reverse proxy.





## LET's START ~

### STEP 1 :
```bash
  clone this repository.
```
### STEP 2 :
```bash
  sudo apt update 

  sudo apt-get install nginx
```

### STEP 3 :
```bash
  cd notes-app
```
### STEP 4 :
```bash
   docker build . -t notesapp
```
### STEP 5 :
```bash
  docker run -d -p 8000:8000 notesapp:latest
```
### STEP 6 :
```bash
  docker ps 
  -->> It shows an running container.
  curl -L http://127.0.0.1:8000
```
### STEP 7 :
```bash
 curl -L http://127.0.0.1:8000
```
It is showing such content.
## Now using the nginx reverse proxy
We can change the such part in the sites-enabled file of nginx.

### STEP 1 :
```bash
  cd /etc/nginx/
```
There are two file to be in use 
  1 nginx.config
  2 sites.enabled 

### STEP 2 :
```bash
  cd /etc/nginx/sites-enabled
  ls

```
### STEP 3 :
```bash
  vim default
```
 Edit the part below in the image:
 ![Logo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/th5xamgrr6se0x5ro4g6.png)

## Reload your page with your public IP
![Logo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/th5xamgrr6se0x5ro4g6.png)

# Note:- No add task is working 
Now connect the api to the server.
### STEP 4 :
```bash
  cd ~
  cd notes-app/mynotes/build
  ls
```
### STEP 5 :
```bash
  sudo cp -r * /var/www/html/
  check it..
  ls /var/www/html/
```
### STEP 6 :
```bash
  check it the api is working or not!
  curl -L http://127.0.0.1:8000/api
```
### STEP 7 :
```bash
  cd /etc/nginx/sites-enabled
  vim default
```
add this part.
![Logo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/th5xamgrr6se0x5ro4g6.png)

## Now Reload your web page:

![Logo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/th5xamgrr6se0x5ro4g6.png)

Hence, it will showing our application using nginx reverse-proxy.
