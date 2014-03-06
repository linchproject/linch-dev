#Linch Dev

Contains a class loader that loads classes and resources from source. It is
used, for example, within linch-servlet in development mode, where the classes
and resources are being reloaded on every request so there is no need to
restart the web server to see the changes made.

##DynamicClassLoader

Before a class is loaded, the class loader looks in src/main/java for a
matching .java file and compiles the class file into target/classes. Then the
created .class file will be read and loaded. When no file is found, the given
parent class loader is called.

If a root package is given, the class loader will only look for a source
file, if this package is the classes parent package or one of the ancestor
packages.

Resources are loaded directly from src/main/resources. When no file is found,
the given parent class loader is called.
