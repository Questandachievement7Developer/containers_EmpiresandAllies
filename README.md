# container_Empires and allies
Setup old empires and allies server in just couple of code using unifiedContainer Technology <br>
https://github.com/Questandachievement7Developer/UnifiedContainer

## Container Blueprint
container Blueprint


core Requirements
package arm = 

package x86_64 = pepper-flash
electron@4.0
5> above compositor will crash due to enforced gpu process containerization

launch param
<br>
arm
electron . --no-sandbox --disable-dev-shm-usage --ppapi-flash-path=/opt/google/chrome/libpepflashplayer.so --disable-gpu --disable-gpu-appcontainer --disable-gpu-sandbox --disable-accelerated-compositing --debug-print --enable-gpu-debugging

<br>
x86_64
electron . --no-sandbox --disable-dev-shm-usage --ppapi-flash-path=/usr/lib/PepperFlash/libpepflashplayer.so --disable-gpu --disable-gpu-appcontainer --disable-gpu-sandbox --disable-accelerated-compositing --debug-print --enable-gpu-debugging <br>


novnc <br>
export DISPLAY=:69
vncserver -SecurityTypes none :69
./utils/launch.sh --vnc localhost:5901
for empires-server
python empires-server.py --port 2495

https://github.com/AcidCaos/raisetheempires
"https://github.com/novnc/noVNC"
https://github.com/electron/electron-quick-start




inject main.js >

```
// Modules to control application life and create native browser window
const {app, BrowserWindow} = require('electron')
const path = require('path')
//const urls = "https://www.google.com"
const urls = "http://127.0.0.1:2495"

function createWindow () {
  // Create the browser window.
  const mainWindow = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      preload: path.join(__dirname, 'preload.js')
    }
  })

  // and load the index.html of the app.
  //mainWindow.loadFile('index.html')
  mainWindow.loadURL(urls)
  // Open the DevTools.
  // mainWindow.webContents.openDevTools()
}

// This method will be called when Electron has finished
// initialization and is ready to create browser windows.
// Some APIs can only be used after this event occurs.
app.on('ready', createWindow)

// Quit when all windows are closed.
app.on('window-all-closed', function () {
  // On macOS it is common for applications and their menu bar
  // to stay active until the user quits explicitly with Cmd + Q
  if (process.platform !== 'darwin') app.quit()
})

app.on('activate', function () {
  // On macOS it's common to re-create a window in the app when the
  // dock icon is clicked and there are no other windows open.
  if (BrowserWindow.getAllWindows().length === 0) createWindow()
})

// In this file you can include the rest of your app's specific main process
// code. You can also put them in separate files and require them here.
```

Port mapping 
empires-server.py=2495
noVNC chromium/electron = 5005~5010 ( 5 users )
port forwarded using localhost.run reverse ssh tunelling port 80
