# Expressive
Expressive is a suite of tools to aid in writing client and server applications with ease, using only simple javascript objects and functions.

# Coming Very Soon! #
<br>


### Simple server example: ###

    const routes = {
      user: function(name, callback) {
        callback(null, `Username: ${name}`)
      },
    }
    
    const expressive = require('expressive')(routes)
    expressive.start()
    
<br>

### Simple React-Native client example: ###

    import Fetch from 'expressive-react-fetch'
    
    const routes = 'http://example.com/routes'
    const fetch = Fetch(routes)
    
    let user = await fetch.users.read(userId)
    // Do something with user 
    
<br>

### Features Key: ###
:heavy_check_mark: Complete <br>
:soon: Almost done <br>
📦 Work in Progress <br>
:tent: Not started yet <br>
:warning: Pending other features <br>
:speech_balloon: Proposal <br>
:no_entry_sign: Rejected <br>


### Features: ### 
- :heavy_check_mark: Configurable
- :heavy_check_mark: Nested capable Object structure defines your routes
- :heavy_check_mark: CRUD-L (Create, Read, Update, Delete, List) routing capabilities
- :heavy_check_mark: Auth/Validation routes run before your CRUD routes (with filtering support)
- :heavy_check_mark: Automatic parameter destructuring
- :soon: Extendable Plugin architecture for new Protocols
- 📦 Dynamic Client-side routing file (stop hard-coding domain paths!)
- 📦 Isometric (Re-use the same code on both client and server)
- :tent: CommonJS, ES6, AMD builds available
- :tent: CLI tooling to create new Expressive projects with sane defaults

<br>

### Protocols implemented: ### 
#### Servers: ####
- Express
- Socket.io [In-Progress]
- mqtt [In-Progress]

#### Clients: ####
- React Native [In-Progress]

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

####  Custom CRUD-L terms: #### 

    const terms = {
      verbs: {
        create: 'post',
        read: 'get',
        update: 'put',
        delete: 'delete',
        list: 'options',
        
        auth: 'auth',
        
        // Partial terms are coming soon!
      }
    }

    const routes = {
      users: {
        post: createUser, // Function
        get: getUser, // Function
        ...
      }
    }
    
    const expressive = require('expressive')(routes, terms)
    expressive.start()

### Documentation ###

<br>

### License: ###
#### [MIT LICENSE](https://github.com/bugs181/Expressive/blob/master/LICENSE) ####
