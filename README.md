# Expressive
Expressive is a new way to write applications without all the junk. 

Most notably, it can be used to write client and server applications with ease, using only a simple javascript object format. 

Expressive is highly configurable and can easily be extended in many facets using a simple plugin architecture. 
Framework developers provide a simple abstraction layer for things like loggers, protocols, data consumers, and even route transformations. 

To the end user (you!), none of that matters except getting to Express
your application the way you want. Expressive has a full-featured UI tool to help you create projects without writing a single line of code!

# Coming Very Soon! #
<br>

### Simple server example: ###

    const routes = {
      user: function(name, callback) {
        callback(null, `Username: ${name}`)
        or
        return await `Username: ${name}`
      },
    }
    
    const expressive = require('expressive')(routes)
    expressive.start()
    
<br>

### Simple client example: ###

    import Fetch from 'expressive-react-fetch'
    
    const routes = 'http://example.com/routes'
    const fetch = Fetch(routes)
    
    let user = await fetch.users.read(userId)
    // Do something with user 
    
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
- :heavy_check_mark: Highly Configurable
- :heavy_check_mark: Nested capable Object structure defines your routes
- :heavy_check_mark: CRUD-L (Create, Read, Update, Delete, List) routing syntax
- :heavy_check_mark: Custom CRUD-L verbiage terms
- :heavy_check_mark: Route functions lets you omit CRUD-L terms for quick single routes
- :warning: Route functions can be marked as private and only accessible to your business logic
- :heavy_check_mark: Auth/Validation routes run before your CRUD routes (with filtering support)
- :heavy_check_mark: Automatic parameter destructuring
- :heavy_check_mark: Context support for routes to access low-level Protocol API
- :heavy_check_mark: Simple Plugin architecture for new Protocols, just 3 methods!
- :heavy_check_mark: Simple Plugin architecture for logging Plugins
- :warning: Extend the route object syntax with Transpiler Plugins.
- :soon: Hot/Live reload Plugin architecture
- 📦 Dynamic Client-side routing file (No more hard-coding URL paths!)
- 📦 Isometric (Re-use the same code on both client and server)
- :tent: CommonJS, ES6, AMD builds available
- :warning: CLI tooling to create new Expressive projects with sane defaults
- :warning: UI tool to organize projects, quickly create routes. Full support for config, logging.
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

#### Middlewear: ####
- :heavy_check_mark: [expressive-middlewear](https://github.com/bugs181/expressive-middleware)

#### Clients: ####
- 📦 React Native Fetch
- :tent: React Native Socket.io
- :tent: React Native AMP

#### Loggers: ####
- :heavy_check_mark: [ANSI Console](https://github.com/TooTallNate/ansi.js) - [Plugin](https://github.com/bugs181/expressive-ansi-console)
- :tent: [Logstash](https://www.elastic.co/products/logstash)

<br>

### Install: ###
    cd myProject
    npm init -y
    npm install expressive --save
    npm start

### CLI tool Example: ###
    npm install expressive-cli -g
    expressive init myProject
    expressive install express
    expressive start

<br>
<br>

#### CRUD-L (Create, Read, Update, Delete, List) example: ####
    const routes = {
      users: {
        create: function(user, password, callback) {
          callback(null, 'Created user')
        },
    
        read: function(user, callback) {
          callback(null, 'Reading user')
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

### Documentation ###
- [Auth / Validation routes]()
<br>

### License: ###
#### [MIT LICENSE](https://github.com/bugs181/Expressive/blob/master/LICENSE) ####
