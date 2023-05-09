# Deploy_Own_Server

1. Create a Public Repo.
2. Clone and Open Vs Code.
3. npm init -y
4. npm install --save json server
5. Create a index.js file.
6. Go to package.json and Add a new line in Scripts - "start": "node index.js".
7. Create .gitignore file and add node_modules (to stop pushing node_modules to github).
8. Add the following code in index.js -

const jsonServer = require('json-server');
const server = jsonServer.create();
const router = jsonServer.router('db.json');
const middlewares = jsonServer.defaults();

server.use(middlewares);
server.use(router);
server.listen(process.env.PORT || 3000, () => {
console.log('JSON Server is running');
});

9. Write your code in db.json and push to github.
10. Go to render.com and login.
11. Click on new, then on Web Services.
12. Paste the github repo link and Continue.
