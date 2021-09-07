# ADB Commands
1. <code>adb kill-server</code> **to kill adb server.**
2. <code>adb start-server</code> **to start adb server.**
3. <code>adb shell ps</code> **list all the process running in the system with pid.**
4. <code>adb shell pidof -s <package_name/> </code>  **return pid of process/packagename.**
5. <code> adb shell</code> **to enter adb shell**, **to exit adb shell ctrl+d.**
6. <code>>>$ su</code>  *to enable super user mode (only for rooted devices)*, **#->super user.**
7.  <code># cat /proc/<pid_of_process>/maps |  grep "libnative-lib.so"</code> **check mapping of file into memory**, *grep->global regular expression*
8. <code>adb shell pm list packages</code> **display packages list.**
9. <code>adb connect <ip_address/> </code> **to connect to remote device.**
  10. <code>adb install -f -r -d -t <apk_file_name> </code> **to install apk.**
11. `adb shell dumpsys package <package-name> | grep "uid"` **return userid of package.**
12. `grep libxyz.so /proc/*/maps  : **lists all the proc mapping .so file.**
13. `adb pull /data/system/packages.xml` **pull packages.xml from connected  device.**
14. `adb push packages.xml /data/system` **push packages.xml from local machine to connected device.**
