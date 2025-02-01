# Simple frontend that interfaces with ollama running deepseek ai

To make it work:

**Set Up Your Environment**
- Install Ollama on your system if you haven't already.
- Download the AI model through Ollama
  - In my app i use deepseek-r1:32b -> about 25 GB of RAM (Kinda slow)
  - You can also use deepseek-r1:14b -> about 11 GB of RAM
- You can access Ollama API though the default port http://localhost:11434/api/generate

The fetch:
```javascript
const message = {
method: 'POST',
headers: {
'Content-Type': 'application/json',
},
body: JSON.stringify({
model: 'deepseek-r1:32b', // Replace with your model name if needed
prompt: "Put here what you ask",
}),
};
```

Pretty cool to host everything on the same machine, no access to the internet required

To make the AI faster you need an NVIDIA Gpu with a lot of gpu memory, thankfully the model still works on the RAM using the actual CPU to compute (slower but usable)

I tried to add markdown support, right now it will convert the markdown to html at the end of the response
