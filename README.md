# Deploy_Own_Server

1. Create a Public Repo.
2. Clone and Open Vs Code.
3. npm init
4. Press Enter till all the scripts gets created in Package.json and Terminal.
5. npm install --save json server
6. Create .gitignore file and add node_modules (to stop pushing node_modules to github).
7. Create a index.js file.
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

9. Go to package.json and Add a new line in Scripts - "start": "node index.js".
10. Add your Data in db.json and push to github.
11. Go to render.com and login.
12. Click on new, then on Web Services.
13. Paste the github repo link and Continue.
