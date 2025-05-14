This is a minimal reproducible repo to show that [Next.js](https://nextjs.org) request URL is incorrect in standalone output.

## Steps
1. Run `npm ci` to install dependencies.
2. Run `npm run build` to build standalone output.
3. Run `node ./.next/standalone/server.js` to run the standalone server. It is expected that the server listening on `0.0.0.0` on network.
    ```
    ▲ Next.js 15.4.0-canary.34
    - Local:        http://localhost:3000
    - Network:      http://0.0.0.0:3000
    ```
4. Access `http://localhost:3000/get/127.0.0.5/show/127.0.0.1` from browser. The request URL printed is incorrect.
    ```
    Request URL: http://0.0.0.0:3000/get/localhost/show/127.0.0.1
    ```
