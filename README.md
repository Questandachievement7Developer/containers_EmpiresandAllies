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
<!DOCTYPE html>
<html>
   <head>
      <title>HTML Meta Tag</title>
      <meta http-equiv = "refresh" content = "2; url = 127.0.0.1:2495" />
   </head>
   <body>
      <p>Hello EAL novnc piping</p>
   </body>
</html>

```

Port mapping 
empires-server.py=2495
noVNC chromium/electron = 5005~5010 ( 5 users )
port forwarded using localhost.run reverse ssh tunelling port 80
