# Cairn Local

Run a local OpenAI-compatible inference router, connect trusted peers, and review routes from a browser console on your machine.

**[Download Cairn Local](https://github.com/Use-Cairn/cairn-local/releases/download/local-a7cdebf/cairn-local-a7cdebf.zip)** · [View release](https://github.com/Use-Cairn/cairn-local/releases/tag/local-a7cdebf)

## Quick start

1. Install **Node.js 24.12 or later** with npm.
2. Download and extract `cairn-local-a7cdebf.zip`.
3. Open a terminal in the extracted folder containing `package.json` and run:

   ```sh
   npm ci --ignore-scripts
   npm run demo
   ```

The demo uses two temporary synthetic providers to verify routing and test JSON and streaming responses. It requires no model download and shuts down when it finishes.

## Connect a local Ollama model

1. Start Ollama with a chat model you already have installed.
2. Copy `config.example.json` to `config.local.json` and replace `replace-with-your-installed-model` with the exact model name.
3. Set `ROUTER_API_KEY` in your terminal environment to a private bearer key of your choice.
4. Validate the configuration and start the router:

   ```sh
   npm run check -- config.local.json
   npm start -- config.local.json
   ```

Configure your OpenAI-compatible client to use `http://127.0.0.1:8787/v1` as its base URL, `local-chat` as its model, and the same bearer key.

## Open the operator console

Set `CAIRNMESH_OPERATOR_KEY` in your terminal environment to a separate private key, run `npm run operator`, and open the loopback URL printed in the terminal. Use that key to unlock the console.

This preview runs locally. Public-chain settlement is disabled.
