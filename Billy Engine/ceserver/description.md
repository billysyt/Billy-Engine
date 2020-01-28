# ceserver

# Build

  - Linux:gcc
  - Android:Android Studio(ndk-build)

The following explanation is for ceserver only.
#### Linux
・gcc

```
ceserver
│  makefile
│
├─bin
├─include
│      api.h
│      ceserver.h
│      ceservertest.h
│      context.h
│      extensionfunctions.h
│      extensionloader.h
│      porthelp.h
│      symbols.h
│      threads.h
│
└─source
        api.c
        ceserver.c
        ceservertest.c
        context.c
        extensionfunctions.c
        extensionloader.c
        porthelp.c
        symbols.c
        threads.c
```
In the above state, move to the ceserver folder and execute the `make` command.


#### Android
・Android Studio(ndk-build)

```
EXECUTABLE
 └─jni
          Android.mk
          api.c
          api.h
          Application.mk
          ceserver.c
          ceserver.h
          ceservertest.c
          ceservertest.h
          context.c
          context.h
          extensionfunctions.c
          extensionfunctions.h
          extensionloader.c
          extensionloader.h
          porthelp.c
          porthelp.h
          symbols.c
          symbols.h
          threads.c
          threads.h
```

In the above state, move to the EXECUTABLE folder with Android Studio Terminal and execute `ndk-build`.

# Usage
### Linux
 - Start ceserver with administrator privileges.`sudo ./ceserver`
 - Start Billy Engine via Wine, or if you are running Linux on a virtual machine, start Billy Engine on the host OS.
 - Select the Network tab of the process list. In the Host field, enter localhost (via Wine) or Guest OS ip (on a virtual machine).

### Android
 - Execute `su` and start ceserver with root privileges.
 - Run the adb command on the PC.`adb forward tcp:52736 tcp:52736`
 - Start Billy Engine.
 - Select the Network tab of the process list. In the Host field, enter localhost (Android Emulator) or Android device ip address (real Android device).
 
### Execution options
 - `-a`
Perform module enumeration only for the specified process ID.
 - `-m` 
If `1` is specified, memory is read and written only with the ptrace privilege, not via the virtual file system.
 - `-p`
Listen on the specified port number instead of the default 52736.
 - `-t`
Start ceserver in test mode.
