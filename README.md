# jrt-extractor
Extract Java 9+ JRT images to a normal Jar

In previous versions of Java, the standard library was contained in an ordinary jar named rt.jar within the JDK or JRE. However, in Java 9, this was changed to use a custom undocumented format. This tool extracts the new JRT to an ordinary jar file, so it can be used by tools that expect jar files and by non-Java tools.

# Usage
This tool is just one class. You can compile and run it as follows, or use the build system of your choice

```
javac JRTExtractor.java && java -ea JRTExtractor
```


This will produce a file named "rt.jar" in the current directory which contains every classfile and module file found. Classfiles appear at paths such as `java/lang/String.class` as before while module files appear in a directory named after the module, such as `java.base/module-info.class`.

