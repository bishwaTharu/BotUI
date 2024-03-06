## STEPS TO RUN THIS PROJECT

```bash
ollama run serve
ollama pull llama2
```

## Quick Integration Guide STEPS

**Ensure Ollama API Server is Running**: Follow the official instructions to get Ollama up and running on your machine

- For detailed instructions on setting up the Ollama API server, please refer to the
  [Ollama download page](https://ollama.ai/download) and [instructions for linux](https://github.com/jmorganca/ollama/blob/main/docs/linux.md).

**Enter Ollama Host URL**: Provide the Ollama Host URL where the API server is accessible (e.g., `http://localhost:11434`)
**Refresh Model List**: Once connected, refresh the list of available models to include the Ollama models

> Optional: use the Ollama Admin interface to see which models are available and 'Pull' them in your local machine. Note
> that this operation will likely timeout due to Edge Functions timeout on the big-AGI server while pulling, and
> you'll have to press the 'Pull' button again, until a green message appears.
> **Chat with Ollama models**: select an Ollama model and begin chatting with AI personas

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

```bash
npm run start
```
