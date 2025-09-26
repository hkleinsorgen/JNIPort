# Accessing running JVMs

The class JVM keeps track of all its running instances. To ask for a list of running JVMs, send `runningInstances` to the class:

```Smalltalk
runningJVMs := JVM runningInstances.
```

To ask for the number of running JVMs, send instancesStarted to the class:

```Smalltalk
numberOfJVMs:= JVM instancesStarted.
```

Due to limitations in the Java implementation, you can effectively start only one Java VM per operating system process. Other implementations may not have this limitation, although I don't know if there is any which actually support starting more than one VM per process.

The consequence is that it is usually sufficient to access the one and only JVM instance by sending current to the class JVM, which will answer the first of the running JVMs:

```Smalltalk
jvm := JVM current.
```