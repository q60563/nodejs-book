# Table of Contents

- Child Process
  - Asynchronous Process Creation
    - Spawning .bat and .cmd files on Windows
    - child_process.exec(command[, options][, callback])
    - child_process.execFile(file[, args][, options][, callback])
    - child_process.fork(modulePath[, args][, options])
    - child_process.spawn(command[, args][, options])
      - options.detached
      - options.stdio
  - Synchronous Process Creation
    - child_process.execFileSync(file[, args][, options])
    - child_process.execSync(command[, options])
    - child_process.spawnSync(command[, args][, options])
  - Class: ChildProcess
    - Event: 'close'
    - Event: 'disconnect'
    - Event: 'error'
    - Event: 'exit'
    - Event: 'message'
    - child.connected
    - child.disconnect()
    - child.kill([signal])
    - child.pid
    - child.send(message[, sendHandle[, options]][, callback])
      - Example: sending a server object
      - Example: sending a socket object
    - child.stderr
    - child.stdin
    - child.stdio
    - child.stdout
  - maxBuffer and Unicode


# Child Process
# Asynchronous Process Creation
### Spawning .bat and .cmd files on Windows
### child_process.exec(command[, options][, callback])
### child_process.execFile(file[, args][, options][, callback])
### child_process.fork(modulePath[, args][, options])
### child_process.spawn(command[, args][, options])
###### options.detached
###### options.stdio
# Synchronous Process Creation
### child_process.execFileSync(file[, args][, options])
### child_process.execSync(command[, options])
### child_process.spawnSync(command[, args][, options])
# Class: ChildProcess
### Event: 'close'
### Event: 'disconnect'
### Event: 'error'
### Event: 'exit'
### Event: 'message'
### child.connected
### child.disconnect()
### child.kill([signal])
### child.pid
### child.send(message[, sendHandle[, options]][, callback])
###### Example: sending a server object
###### Example: sending a socket object
### child.stderr
### child.stdin
### child.stdio
### child.stdout
# maxBuffer and Unicode