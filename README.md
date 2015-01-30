adbcores -- Report the usage of each CPU core for a FirefoxOS or Android device
connected via ADB

This is a very simple Python script (I'm a python novice -- pull requests welcome) 
that uses adb to communicate with
the FirefoxOS or Android device connected to your computer via USB
cable. It records the contents of /proc/stat, waits 5 seconds, and
then records the contents of that file again. By subtracting the first
set of numbers from the second set of numbers, it can determine how
busy each of the device CPU cores were during the wait period, and it
prints a CPU usage report the the console. This is useful, for
example, if you want to test an app to see how efficiently is is
utilizing the available cores on a given device.

If you want to wait for an interval other than 5 seconds, just specify
the number of seconds as an argument on the command line.

```
$ ./adbcores 10
measuring CPU usage over 10.0 seconds
CPU     BUSY%   IDLE%   WAIT%
0       59%     41%     0%
1       58%     42%     0%
2       37%     63%     0%
3       27%     73%     0%
```
