# Fantastic Express Boilerplate (ES2015) 

> This boilerplate is written in ES2015 and requires Node 6.x+

This is a fantastic Node/Express/Bookshelf+SQL/Role-Based Authentication boilerplate. It is designed to get you up-and-running on your own project without having to setup the basic user/role models, tasks, and more.

#### Getting Started

Git clone this repository and run `npm install && npm start`.

#### Tests

Tests are written with Mocha/Chai. A boilerplate CRUD test is included). To run them, you may run `npm test`.

## Behind the Scenes

#### Gulp

Gulp powers the base server for this boilerplate. Inside of the `gulpfile.js` are a few tasks:
* `precompile` - Transforms `frontend/` Javascript files using Babel for ES2015 support & places the result inside of `/public/app-build.js`
* `watch` - watches for file changes in `frontend/` & re-runs `precompile`
* `server` - launches `node ./bin/www` using Nodemon & restarts when server-side code is recompiled
* `create_db_tables` - creates the SQL tables specified in the `const` variables in the gulfpile. (Only ran externally via `gulp create_db_tables`)
* `drop_db_tables` - drops the SQL tables specified in the `const` variables in the gulpfile. (Only ran externally via `gulp drop_db_tables`)


#### Folder Structure & Organization

* `bin/` contains the server scripts
* `controllers/` contains controllers for HTTP endpoints
* `frontend/` contains your custom client-side application code (this is transpiled to ES2015 by Babel into `public/javascripts/app-build.js`
* `models/` contains all of your database & SQL specific scripts
* `public/` contains all folders & files exposed to `/` when the server is running
* `test/` contains Mocha/Chai unit tests
* `views/` contain Handlebars views