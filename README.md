weka-ikvm-performance-test
==========================

Basic project to evaluate the performance of [http://www.cs.waikato.ac.nz/ml/weka/](Weka) running under the JVM versus under the CLR(using IKVM).  This code is designed to run on 

## Setup - Java

You will need to have the Weka Jar somewhere on your system already. If using Eclipse, update the .classpath accordingly for the jar location.  Otherwise, update the classpath in compile.bat and run.bat.

## Running - Java

After updating the classpath, you can use run.bat to run the Weka on the JVM.  This is an implementation of the code in the [IKVM Tutorial](http://weka.wikispaces.com/IKVM+with+Weka+tutorial) with some additional timing calls.  The code will print average times for the training/classification stages and dump the times to CSVs for more advanced analysis.

## Setup - IKVM/CLR
  You will need to download [IKVM](http://sourceforge.net/projects/ikvm/files/) and run it on the Weka Jar from your Weka installation.

For example:
ikvmc -target:library "c:\Program Files\Weka-3-6\weka.jar" -out:weka.dll


## Results

Testing was done on a Core i7-2600 - 3.4 GHz machine running Windows 7 and Java 1.7.0 - 64 bit.

### Java Performance

The Weka Java implementation completes the training phase in ~9.6 seconds and the classification phase in ~7.0 ms

### IKVM/CLR Performance

Hasn't been run yet