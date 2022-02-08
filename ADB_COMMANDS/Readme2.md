# ADB/ LINUX COMMANDS

1. Permission groups
   * For every file and directory in Linux, there are the sets of users for whom we specify permissions. They are:
      * Owners
      * Groups
      * Others
   * COMMAND : ```CHMOD XXX <FILE_NAME>```
   * READ(4), WRITE(2), EXECUTE(1)
   * R+W+E=7
   * EX: ```chmod 744 build.prop  --> change mode to _rwx_```

2. ### Native heap dump generating commands (<=os11)
      * ```adb shell setprop libc.debug.malloc.options backtrace```       // batch in 16
      * ```adb shell setprop libc.debug.malloc.program <selected package>```   // select package to config
      * ```adb shell setprop wrap.<package_name> 'LIBC_DEBUG_MALLOC_OPTIONS=backtrace logwrapper'```
      * ```adb shell setenforce 0```             // set permissible mode (SELINUX)
  
   #### TO CHECK CONFIGURED PROPERTIES
      * ```adb shell getprop libc.debug.malloc.options```
      * ```adb shell getprop libc.debug.malloc.program```
      * ```adb shell getenforce```
    
   1. ```adb shell stop``` //warm boot
   1. To generate dump.txt : ```adb shell am dumpheap -n <process_id> /data/local/tmp/Dump.txt```
   2. To pull dump file : ```adb pull /data/local/tmp/Dump.txt```
 
 3. #### Native heap dump generating commands (for OS 12)  update build.prop file
       * ```adb remount``` //to change read only mode to read write mode
       * ```echo "libc.debug.malloc.program=app_process">>/system/build.prop```
       * ```echo "libc.debug.malloc.options=backtrace" >>/system/build.prop```
       * ```echo "libc.debug.malloc.env_enabled=1" >>/system/build.prop```
       * ```echo "libc.debug.malloc=1" >>/system/build.prop```
       * ```adb reboot``` //cold boot
       * To generate dump.txt : ```adb shell am dumpheap -n <process_id> /data/local/tmp/Dump.txt```
       * To pull dump file : ```adb pull /data/local/tmp/Dump.txt```
  4. ### Dump.txt
     ```
     Android Native Heap Dump v1.2
       Build fingerprint : ...
       Total memory: 31736900
       Allocation records: 14530
       BackTrace size :16
       
       z0 sz 262144 num 1 bt 70bd3a0db0 70645db9 6dbbfac34c.................. 70bd3ad068 <---mem location
       z0
       z0
       ............. mem addr for sus leak
       
       6d9145b000-6d9145c000 r--p 00000000 fd:00 4684   /system/lib64/......./lib.so <---- .so file memory range
       ```
     
     * search memory addr in the given range.
    
  
