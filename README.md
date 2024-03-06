## STEPS TO RUN THIS PROJECT

```bash
ollama run serve
ollama pull llama2
```

```bash
npm start
```

## Quick Integration Guide

**Ensure Ollama API Server is Running**: Follow the official instructions to get Ollama up and running on your machine

**Enter Ollama Host URL**: Provide the Ollama Host URL where the API server is accessible (e.g., `http://localhost:11434`)

```bash
sudo apt update
sudo apt install nginx
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d yourdomain.com
```

Then, edit the nginx configuration file `/etc/nginx/sites-enabled/default` and add the following block:

```nginx
    location /ollama/ {
        proxy_pass http://localhost:11434;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;

        # Disable buffering for the streaming responses
        proxy_buffering off;
    }
```

Reach out to our community if you need help with this.

<br/>
