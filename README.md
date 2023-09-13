# [Deploy Your Own Mock Back-End JSON Server](https://abduljabbarpeer.notion.site/abduljabbarpeer/Deploying-JSON-Server-on-render-com-Heroku-Alternative-2caf242350d84941b87ba98f5d2e4376)

- Create a Public Repo, clone and open it in VS Code.
- Open terminal and enter the following commands :
- `npm init -y`
- `npm i json-server`
- Create a `.gitignore` file and add `node_modules` ( to avoid pushing node_modules folder on github ).
- Create a `index.js` file.
- Add the following code :

```
const PORT = process.env.PORT || 3000;
const jsonServer = require("json-server");

const server = jsonServer.create();
const router = jsonServer.router("db.json");
const middlewares = jsonServer.defaults();

server.use(middlewares);
server.use(router);

server.listen(PORT, () => {
  console.log(`Server is running on port : ${PORT}.`);
});
```

- Open `package.json` & add the following line in scripts keyword :
- `"server" : "node index.js"`.
- Create a `db.json` file, add your data in JSON format & push the code on github.
- Now your JSON server is ready to be deployed on any hosting platform such as render, cyclic.sh, railway, heroku etc.

### Note :

- You must have installed `node.js` on your system.
- If you want to use environment variables for PORT, run the following command in terminal : `npm i dotenv`.
- Also add the following line of code in the top of your index.js. :

```
require("dotenv").config()
```

- Create a `.env` file and add the following keyword :

```
PORT=Your_PORT_Number
```

- If you have used environment variables for PORT, do not forget to add them while deploying your server.
- Some hosting platforms may also ask you to provide the server start key, in that case give the following command : `npm run server`.
