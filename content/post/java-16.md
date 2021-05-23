+++

author = "Jacob Hell"
title = "What's New in Java 16"
date = "2021-03-08"
description = "Java 16"
tags = [
    "java"

]

+++

<!--more-->


## Vector API (Incubator)

The Vector API has been added to the [incubator module](https://openjdk.java.net/jeps/11).

The Vector API adds vector computations that reliably compile at runtime to optimal vector hardware instructions.

Here is an example:

```java
static final VectorSpecies<Float> SPECIES = FloatVector.SPECIES_256;

void vectorComputation(float[] a, float[] b, float[] c) {
    int i = 0;
    int upperBound = SPECIES.loopBound(a.length);
    for (; i < upperBound; i += SPECIES.length()) {
        // FloatVector va, vb, vc;
        var va = FloatVector.fromArray(SPECIES, a, i);
        var vb = FloatVector.fromArray(SPECIES, b, i);
        var vc = va.mul(va).
                    add(vb.mul(vb)).
                    neg();
        vc.intoArray(c, i);
    }

    for (; i < a.length; i++) {
        c[i] = (a[i] * a[i] + b[i] * b[i]) * -1.0f;
    }
}
```

Based on my research, this won't be useful for most developers right away. It fits a niche used for low level processing and matrix multiplication.

## Enable C++14 Language Features

Allows the use of C++14 language features in JDK C++ source code. This won't be relevant to someone using Java to write code. But we might see performance improvements.

## Migrate from Mercurial to Git and Migrate to GitHub

Move the JDK repository to GitHub. I think this is a good change. Git is definitely the most widely used source control software. And GitHub is the easiest to use git hosting software.

## ZGC: Concurrent Thread-Stack Processing

Move ZGC thread-stack processing from safepoints to a concurrent phase. This improves scalability and performance of the garbage collector. Not something a developer would notice immediately.

## Unix-Domain Socket Channels

Add Unix-domain (`AF_UNIX`) socket support to the [socket channel](https://docs.oracle.com/en/java/javase/15/docs/api/java.base/java/nio/channels/SocketChannel.html) and [server-socket channel](https://docs.oracle.com/en/java/javase/15/docs/api/java.base/java/nio/channels/ServerSocketChannel.html) APIs. A [Unix domain socket](https://en.wikipedia.org/wiki/Unix_domain_socket) is a data [communications endpoint](https://en.wikipedia.org/wiki/Communication_endpoint) for exchanging data between processes executing on the same host operating system.

Databases like Postgres and MySQL have Unix domain socket communication options. I've never used them, but I'm sure it will be useful for developers who regularly work with them.

## Alpine Linux Port

Port the JDK to Alpine Linux, and to other Linux distributions that use musl as their primary C library.

This will be helpful for getting services like Tomcat, Jetty, and Spring to work on Alpine linux based Docker images.

## Elastic Metaspace

Return unused HotSpot class-metadata (i.e., *metaspace*) memory to the operating system more promptly. Not something a developer would notice immediately.

## Windows/AArch64 Port

Port the JDK to Windows/AArch64.

## Foreign Linker API (Incubator)

Introduce an API that offers statically-typed, pure-Java access to native code.

Native code is code written in other languages like C, C++, and assembly. The Java  Native Interface (JNI) is the framework that allows this currently. The Foreign Linker API and Project Panama seek to offer an alternative to the cumbersome JNI options.

## Warnings for Value-Based Classes

Designate the primitive wrapper classes as *value-based* and deprecate their constructors for removal.

A value based class has the following properties:

- are final and immutable (though may contain references to mutable objects);
- have implementations of `equals`, `hashCode`, and `toString` which are computed solely from the instance's state and not from its identity or the state of any other object or variable;
- make no use of identity-sensitive operations such as reference equality (`==`) between instances, identity hash code of instances, or synchronization on an instances's intrinsic lock;
- are considered equal solely based on `equals()`, not based on reference equality (`==`);
- do not have accessible constructors, but are instead instantiated through factory methods which make no committment as to the identity of returned instances;
- are *freely substitutable* when equal, meaning that interchanging any two instances `x` and `y` that are equal according to `equals()` in any computation or method invocation should produce no visible change in behavior.

Two examples of Value based classes are Optional and LocalDateTime.

This update isn't very exciting, but it shows progress toward increasing adoption of Value Based classes.

## Packaging Tool

Provide the `jpackage` tool, for packaging self-contained Java applications. `jpackage` makes it easy to install and uninstall java applications. You can create installers for the desired machine (exe, dmg, and deb for example). 

For destination machines, you don't even have to install the JRE.

## Foreign-Memory Access API (Third Incubator)

Introduce an API to allow Java programs to safely and efficiently access foreign memory outside of the Java heap. This looks helpful for JVM developers.

## Pattern Matching for instanceof

Enhance the Java programming language with *pattern matching* for the `instanceof` operator.

This change is very useful when using `instanceof`.

For example:

```java
if (obj instanceof String s && s.contains("foo")) {
    // s contains foo!
}
```

## Records

Enhance the Java programming language with [records](https://cr.openjdk.java.net/~briangoetz/amber/datum.html). 

I'm excited for this update. Records make Java less verbose. Something that Project Lombok tries to solve as well.

For example, you can type:

```java
record Point(int x, int y) { }
```

Which would create a class called `Point` with a constructor with `int x, int y`. You would also have accessor methods generated. Records are `final` so you can't edit them once created.

## Strongly Encapsulate JDK Internals by Default

Strongly encapsulate all internal elements of the JDK by default. This update is to improve security and maintainability of the JDK. 

## Sealed Classes (Second Preview)

A `sealed` class only allows extension or implementation by other classes that it allows.

For example:

```java
public abstract sealed class Shape
    permits Circle, Rectangle, Square
```

Can only be extended by the classes Circle, Rectangle, and Square.

I'm not sure what I would use this for, but it's good to know it exists.