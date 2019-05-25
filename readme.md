# Newfirm - Design and development guides


## Contents

+ [General](#General)
+ [Styling](#styling)
  + [css](#css)

+ [Markup](#markup)
  + [HTML](#html)

+ [Programming languages](#programming-languages)
  + [C#](#c-2)
  + [Go](#go)
  + [TypeScript](#TypeScript)
  + [JavaScript](#JavaScript)
  + [Python](#python)

+ [Frameworks](#frameworks)
  + [AngularJS](#AngularJS)
  + [Node.js](#Node.js)
  + [RavenDB](#RavenDb)

+ [Other](#other)
  + [API](#api)
  + [Deployment](#deployment)
  + [Git](#git)
  + [Security](#security)

## General

In general when coding, the following should allways be considered:
* Allways create easy understandable, readable code. This is key.
* Allways consider the next developer taking over your project when you are writing code.
* Allways evaluate every library you import:
  * This will become blackbox code
  * Would i want to extend this and any point, and is the library extendable
  * What benefit will this give me in the long run, compared to developing it myself
  * Is the performance and features of the library satisfying.
* Code should allways be written so its isolated, and easy modular/reusable.
* Logging is crusual. 
  * A program without logging is not a production ready program.
  * Logging and tracability should be one of the bases of any applications we make.

## Styling

### CSS
We use the principles of BEM in our CSS structure.

#### Inspiration
+ [BEM CSS Style Guide](http://getbem.com/introduction/)
+ [Principles of writing consistent, idiomatic CSS](https://github.com/necolas/idiomatic-css#readme)

### HTML

#### Inspiration
+ [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html)

## Programming languages

### C&#35;
+ [Our C# Coding Conventions](./c%23/readme.md)

#### Inspiration
+ [Official C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions)

### Go

#### Inspiration
+ [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)

### TypeScript
For now, typescript and javascript share the designguide.
+ [Our designguide for TypeScript](./js/readme.md)

### JavaScript
+ [Our designguide for Javascript](./js/readme.md)

#### Inspiration
+ [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
+ [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript#readme)
+ [JavaScript: The Right Way](http://jstherightway.org/)

### Python

#### Inspiration
+ [PEP 8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)
+ [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)


### Shell

#### Inspiration
+ [Google Shell Style Guide](https://google.github.io/styleguide/shell.xml)
+ [Scripting with style](https://wiki.bash-hackers.org/scripting/style)


## Frameworks

### AngularJS

#### Inspiration
+ [AngularJS Style Guide](https://github.com/johnpapa/angular-styleguide#readme)
+ [An AngularJS Style Guide for Closure Users at Google](https://google.github.io/styleguide/angularjs-google-style.html)


### Node.js

#### Inspiration
+ [Node.js Style Guide](https://github.com/felixge/node-style-guide#readme)
+ [Node.js Best Practices](https://github.com/i0natan/nodebestpractices#readme)

### RavenDB

#### Inspiration
+ [Security Principles](https://infosec.mozilla.org/fundamentals/security_principles.html)
## Other

### API

#### Inspiration
+ [HTTP API Design Guide](https://github.com/interagent/http-api-design#readme)
+ [Principles of good RESTful API Design](https://codeplanet.io/principles-good-restful-api-design/)
+ [Microsoft REST API Guidelines](https://github.com/Microsoft/api-guidelines/blob/vNext/Guidelines.md#readme)
+ [Building JSON-LD APIs: Best Practices](https://json-ld.org/spec/latest/json-ld-api-best-practices/)


### Deployment

#### Inspiration
+ [Deployments Best Practices](http://guides.beanstalkapp.com/deployments/best-practices.html)


### Git

#### Inspiration
+ [Git Style Guide](https://github.com/agis/git-style-guide#readme)
+ [Commit messages guide](https://github.com/RomuloOliveira/commit-messages-guide#readme)


### Security

#### Inspiration
+ [Security Principles](https://infosec.mozilla.org/fundamentals/security_principles.html)
+ [Web Security Guidelines](https://infosec.mozilla.org/guidelines/web_security)
+ [WebAppSec/Secure Coding Guidelines](https://wiki.mozilla.org/WebAppSec/Secure_Coding_Guidelines)
+ [Web Application Security Guide/Checklist](https://en.wikibooks.org/wiki/Web_Application_Security_Guide/Checklist)

