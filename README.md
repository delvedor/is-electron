# is-electron
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](http://standardjs.com/)

An 'is' utility for Electron.  
`is-electron` provides a set of isomorphic 'is' APIs, that you can use it both in main and renderer process.  
See <a href="#usage">usage</a> for more information.

## Install
```
$ npm install is-electron --save
```

## API

- **is.renderer()**  
Returns `true` if you are calling the function from the renderer process.

- **is.main()**  
Returns `true` if you are calling the function from the main process.

- **is.mac()**  
Returns `true` if your app is running under Mac OS.

- **is.windows()**  
Returns `true` if your app is running under Windows OS.

- **is.linux()**  
Returns `true` if your app is running under Linux OS.

- **is.ia32()**  
Returns `true` if you the architecture of the processor is `ia32`.

- **is.x64()**  
Returns `true` if you the architecture of the processor is `x64`.

- **is.production()**  
Returns `true` if you are running the app in a `production` environment.

- **is.dev()**  
Returns `true` if you are running the app in a `dev` environment.

- **is.all(args)**  
Returns `true` if all the 'is functions' passed as argument are true.  
example: `is.all(is.mac, is.x64)`

- **is.none(args)**  
Returns `true` if all the 'is functions' passed as argument are false.  
example: `is.none(is.windows, is.is32, is.main)`

<a name="usage"></a>
## Usage
- In Main process:
```javascript
// es6
import is from 'is-electron'
// es5
const is = require('is-electron')
console.log(is.main())
```
- In Renderer process:
```html
<script src="node_modules/is-electron/is.js"></script>
<script>
    console.log(is.renderer())
</script>
```
You can access `is` both from `window.is` and `window.isElectron`.  
(If `window.is` is already taken `is-electron` does not overwrite it.)

## Contributing
If you feel you can help in any way, be it with examples, extra testing, or new features please open a pull request or open an issue.

The code follows the Standard code style.  
[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)
______________________________________________________________________________________________________________________
## License
The code is released under the MIT license.

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and non infringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.
