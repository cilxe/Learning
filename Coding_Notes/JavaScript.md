# JS Basis

# JS Objects

# JS Functions

# JS Document Object Mode (DOM)

# JS Browser Object Model (BOM)

## Window
##### Properties
  - window.innerHeight : (current window showing height)
  - window.innerWidth : (current window showing width)
  - document.documentElement.clientHeight : (without tools and scroll bar)
  - document.documentElement.clientWidth : (without tools and scroll bar)
  - document.body.clientHeight : (max scrolled size)
  - document.body.clientWidth : (max scrolled size)

##### Window Methods
  - window.open()
  - window.close()
  - window.moveTo()
  - window.resizeTo()

#### Window Screen (JS with Screen)
##### Properties
  - screen.width
  - screen.height
  - screen.availWidth
  - screen.availHeight
  - screen.colorDepth
  - screen.pixelDepth

#### Window Location (JS with URL)
##### Properties
  - window.location.href : current URL
  - window.location.hash : contents after URL's hash(#)
  - window.location.host : current URL hostname and port (hostname:port)
  - window.location.hostname : current URL hostname
  - window.location.port : current URL host port
  - window.location.pathname : current URL pathname
  - window.location.protocal : current URL web protocal (http: / https:)
  - window.location.search : 
##### Functions
  - window.location.replace(url)
  - window.location.reload()
  - window.location.assign(url): load new URL
#### Window History
##### Methods
  - history.back() - same as clicking back in the browser
  - history.forward() - same as clicking forward in the browser
  - history.go()
  - history.pushState(stateObj, unused, url) - replace session history stack
  - history.replaceState()

###### History.pushState()
```
pushState(state, unused)
pushState(state, unused, url)

// Most browsers prevent cross site URL push request
pushState({}, "Replace", "https://w3.org")
```
# JS AJAX

# JS JSON

# JS Async

# JS Class (Introduced with ECMAScript 2015 (ES6))

# JS RegExp (Regular Expressions)