# **Electron Start**

### **Basic Setup**
Node.js LTS Version: 18.12.1 (includes npm 8.19.2)

#### **Initializing a npm project**
```
# Initialize the folder (entry point: main.js)
npm init

# Add electron dependency to package.json
  "devDependencies": {
    "electron": "19.0.0"
  }
```

#### **Install Electron** 

#### Create <package.json> file
```
package.json
——————————————————————————————————
{
  "name": "my-electron-app",
  "version": "1.0.0",
  "description": "Hello World!",
  "main": "main.js",
  "author": "Author",
  "license": "MIT",
  "devDependencies": {
    "electron": "^19.1.9"
  }
}
```
```
main.js
——————————————————————————————————
const { app, BrowserWindow } = require('electron');

const createWindow = () => {
  const win = new BrowserWindow({
    width: 800,
    height: 600,
  });

  win.loadFile('index.html');
};

app.whenReady().then(() => {
  createWindow();

  app.on('activate', () => {
    if (BrowserWindow.getAllWindows().length === 0) {
      createWindow();
    }
  });
});

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') {
    app.quit();
  }
});
```
#### Install Electron from npm
```
npm install electron --save-dev

# Download node modules using mirrors (Option 1)
npm config set registry https://registry.npmmirror.com/
npm config set ELECTRON_MIRROR https://registry.npmmirror.com/binary.html?path=electron/

# Add System environment (Windows) ELECTRON_MIRROR to {path} (Option 2)
ELECTRON_MIRROR https://registry.npmmirror.com/binary.html?path=electron/
```
#### Running the app
```
npm run start
```

#### **Extend Options**
#### Using Preload Scripts
```
preload.js
——————————————————————————————————
const { contextBridge } = require('electron')

contextBridge.exposeInMainWorld('versions', {
  node: () => process.versions.node,
  firefox: () => process.versions.firefox,
  electron: () => process.versions.electron,
})
```
#### Keep Running app Up-to-date
```
# install nodemon
npm i nodemon --D

# start app with nodemon (modify at package,json)
"start": "nodemon --watch index.js --exec electron ."
```


### **Packaging Your Application (Electron Forge)**
#### **Importing a projects into Forge**
This will auto add a few scripts to package.json
```
npm install --save-dev @electron-forge/cli
npx electron-forge import
```
#### **Creating a distributable**
```
npm run make
```
Output folder: ${Project_Folder}/out

### [IPC (Inter-Process Communication)](https://www.electronjs.org/docs/latest/tutorial/ipc)


### [Native File Drag & Drop](https://www.electronjs.org/docs/latest/tutorial/native-file-drag-drop)
<webContents.startDrag(item)>

### Code Style
- End files with a newline.
- Place requires in the following order:
  - Built in Node Modules (such as path)
  - Built in Electron Modules (such as ipc, app)
  - Local Modules (using relative paths)
- Place class properties in the following order:
  - Class methods and properties (methods starting with a @)
  - Instance methods and properties
- Avoid platform-dependent code:
  - Use path.join() to concatenate filenames.
  - Use os.tmpdir() rather than /tmp when you need to reference the temporary directory.
- app.getAppPath(name) can request the following paths by the name:
  - {home} User's home directory.
  - {appData}  
    - %APPDATA% on Window
    - $XDG_CONFIG_HOME or ~/.config on Linux
    - ~/Library/Application Support on macOS
  - etc... 
  - view at [Electron API document](https://www.electronjs.org/docs/latest/api/app#appgetpathname)




### Issue tracker
 - shell.openPath() get non-current folder files 
   - Resolve: [Stackoverflow](https://stackoverflow.com/questions/65918494/how-do-i-open-a-file-saved-in-the-user-directory-using-electrons-shell-api)
 - 