# Expressive
Expressive is a suite of tools to aid in writing client and server applications with ease, using only simple javascript objects and functions.

# Coming Very Soon! #
<br>


### Simple example: ###

    const routes = {
      user: function(name, callback) {
        callback(null, `Username: ${name}`)
      },
    }
    
    const expressive = require('expressive')(routes)
    expressive.start()
    
<br>

### Features: ### 
- Nested capable Object structure defines your routes
- CRUD-L (Create, Read, Update, Delete, List) routing capabilities
- Dynamic Client-side routing file (stop hard-coding domain paths!)
- Isometric (Re-use the same code on both client and server)
- Automatic parameter destructuring
- Extendable Plugin architecture for new Protocols
- Configurable
- CommonJS, ES6, AMD builds available

<br>

### Protocols implemented: ### 
- Express
- Socket.io [In-Progress]
- mqtt [In-Progress]

<br>

### Install: ###
    npm install expressive --save

### Follow-Along Install: ###
    npm install expressive expressive-express --save

<br>
<br>

### More examples: ###

#### CRUD-L (Create, Read, Update, Delete, List) example: ####
    const routes = {
      users: {
        create: function(user, password, callback) {
    
        },
    
        read: function(user, callback) {
          callback(null, 'OKAY')
        },
    
        ...
      },
    }

    const expressive = require('expressive')(routes)
    expressive.start()

<br>

### Documentation ###

<br>

### License: ###
#### MIT: https://opensource.org/licenses/MIT ####
