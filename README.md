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

<br>
<br>

### Icon Key: ###
:heavy_check_mark: Complete <br>
:soon: Almost done <br>
📦 Work in Progress <br>
:tent: Not started yet <br>
:warning: Pending other features <br>
:speech_balloon: Proposal <br>
:no_entry_sign: Rejected <br>

<br>

### Features: ### 
- :heavy_check_mark: Configurable
- :heavy_check_mark: Nested capable Object structure defines your routes
- :heavy_check_mark: CRUD-L (Create, Read, Update, Delete, List) routing capabilities
- :heavy_check_mark: Custom CRUD-L verbiage terms
- :heavy_check_mark: Auth/Validation routes run before your CRUD routes (with filtering support)
- :heavy_check_mark: Automatic parameter destructuring
- :soon: Extendable Plugin architecture for new Protocols
- 📦 Dynamic Client-side routing file (No more hard-coding URL paths!)
- 📦 Isometric (Re-use the same code on both client and server)
- :tent: CommonJS, ES6, AMD builds available
- :warning: CLI tooling to create new Expressive projects with sane defaults
- :speech_balloon: Custom 404 routes
- :speech_balloon: Route specific verb terms
- :speech_balloon: Async/Await support for route functions
- :speech_balloon: Port to TypeScript

<br>

### Protocols implemented: ### 
#### Servers: ####
- :heavy_check_mark: [Express](https://expressjs.com) ([Github](https://github.com/expressjs/express)) - [Plugin](https://github.com/bugs181/expressive-express)
- 📦 Socket.io
- 📦 [Axon](https://github.com/tj/axon) ([AMP](https://github.com/tj/node-amp-message))
- :tent: mqtt

#### Clients: ####
- 📦 React Native Fetch
- :tent: React Native Socket.io
- :tent: React Native AMP

<br>

### Install: ###
    npm install expressive --save

### CLI tool Example: ###
    npm install expressive-cli -g
    expressive init myProject
    expressive install express
    expressive start

<br>
<br>

### Documentation ###
- [Auth / Validation routes]()
<br>

### License: ###
#### [MIT LICENSE](https://github.com/bugs181/Expressive/blob/master/LICENSE) ####
