---
title: Running SparkMLib with native LAPACK and BLAS
author: oweissbarth
date: 2016-06-24T10:37:19+00:00
url: /running-sparkmlib-with-native-lapack-and-blas/
featured_image: /images/articles/sparkmlib/sparkmlib-feature.png
categories:
  - Uncategorized

---
When getting started with the Spark maschine learning library MLib you probably saw this warning in your console:
{{< highlight bash >}}
WARN BLAS: Failed to load implementation from: com.github.fommil.netlib.NativeSystemBLAS
WARN BLAS: Failed to load implementation from: com.github.fommil.netlib.NativeRefBLAS
WARN LAPACK: Failed to load implementation from: com.github.fommil.netlib.NativeSystemLAPACK
WARN LAPACK: Failed to load implementation from: com.github.fommil.netlib.NativeRefLAPACK{{< /highlight>}}
It gets thrown by “netlib-java”, a wrapper for the low level linear algebra libraries. Netlib-java provides an interface to those native libraries and a pure jvm-fallback.

## Installing BLAS and LAPACK

To get rid of this warning i first installed BLAS and LAPACK through my system’s package-manager.  
If you are on Ubuntu or Debian you can run:

{{< highlight bash >}}sudo apt-get install libatlas3-base libopenblas-base{{< /highlight>}}

I’m on Archlinux so i ran

{{< highlight bash >}}yaourt -S openblas-lapack {{< /highlight>}}

Unfortunately that does not solve the problem. The warning stays.

## Link your java or scala code to the native library

The netlib-java README file is not very helpful here. So i started looking through the maven repository and found that only netlib-java-core is a dependency of spark-mllib. To link to the native libraries you need to netlib-native_system-… for your system. The easiest way to do that is adding the netlib-all package to your project dependencies.  

Maven:  
{{< highlight bash >}}
com.github.fommil.netlib
all
1.1.2
pom {{< /highlight>}}

SBT:
{{< highlight bash >}}
// https://mvnrepository.com/artifact/com.github.fommil.netlib/all
libraryDependencies += "com.github.fommil.netlib" % "all" % "1.1.2" pomOnly() {{< /highlight>}}

&nbsp;  
This will add the netlib-native packages for all supported operating systems and architectures. Netlib will automatically go through all available versions and select the best one.  
As a result if you now rebuild your project the warnings should disappear.

## Adding netlib-native only for a specific os and arch

If you know your project will only be used on the specific os and architecture you might not want to add netlib-native for all the other ones.  
For example to add only add natives for linux x86_64 add the following to your projects dependencies:  

Maven:  
{{< highlight bash >}}
net.sourceforge.f2j
arpack_combined_all
0.1
com.github.fommil.netlib
netlib-native_ref-linux-x86_64
1.1
natives
com.github.fommil.netlib
netlib-native_system-linux-x86_64
1.1
natives 
{{< /highlight>}}
  
SBT:
{{< highlight bash >}}libraryDependencies += "net.sourceforge.f2j" % "arpack_combined_all" % "0.1"<br> libraryDependencies += "com.github.fommil.netlib" % "netlib-native_ref-linux-x86_64" % "1.1" classifier "natives"<br> libraryDependencies += "com.github.fommil.netlib" % "netlib-native_system-linux-x86_64" % "1.1" classifier "natives" {{< /highlight>}}


Where netlib-native\_ref is a provided reference implementation. And netlib-native\_system is the one we installed earlier.  
I hope this works for you.