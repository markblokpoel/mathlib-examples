<img src="notebooks/mathlib-logo-full.png" alt="MATHLIB logo" title="MATHLIB" style="width: 100%; max-width: 400px;" />


[![mathlib Scala version support](https://index.scala-lang.org/markblokpoel/mathlib/mathlib/latest.svg)](https://index.scala-lang.org/markblokpoel/mathlib/mathlib)
[![license](https://img.shields.io/badge/license-%20GPL--3.0-blue)](https://github.com/markblokpoel/mathlib/blob/master/LICENSE)
[![Website](https://img.shields.io/website?url=https%3A%2F%2Fwww.markblokpoel.com%2Fmathlib)](https://www.markblokpoel.com/mathlib)
![Maven Central](https://img.shields.io/maven-central/v/com.markblokpoel/mathlib_2.13)
[![Scaladoc](https://img.shields.io/maven-central/v/com.markblokpoel/mathlib_2.13?label=scaladoc)](https://markblokpoel.com/mathlib/scaladoc/mathlib/)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](notebooks/code_of_conduct.md)

```mathlib``` is a library for Scala supporting functional programming that resembles
mathematical expressions such as set theory, graph theory and probability theory.
This library was developed to complement the theory development method outlined
in the open education book [Theoretical modeling for cognitive science and psychology by
Blokpoel and van Rooij (2021)](https://computationalcognitivescience.github.io/lovelace/).

The goal of this library is to facilitate users to implement simulations of their formal theories. ```mathlib``` and
Scala code is:

* 👓 easy to **read**, because ```mathlib``` syntax closely resembles mathematical notation
* ✅ easy to **verify**, by proving that the code exactly implements the theoretical model (or not)
* ❤️ easy to **sustain**, older versions of Scala and mathlib can easily be run on newer machines

The ```mathlib``` library github page is [https://github.com/markblokpoel/mathlib](https://github.com/markblokpoel/mathlib) and the companion website can be found at [https://www.markblokpoel.com/mathlib](https://www.markblokpoel.com/mathlib).

## Contents

* ```examples/```
  * [```coherence.ipynb```](examples/coherence.ipynb) Coherence
  * <span style="opacity: 0.2;">[```selecting-invitees.ipynb```](examples/selecting-invitees.ipynb) Not yet available.</span>
  * <span style="opacity: 0.2;">[```subset-choice.ipynb```](examples/subset-choice.ipynb) Not yet available.</span>
  * <span style="opacity: 0.2;">[```vertex-cover.ipynb```](examples/vertex-cover.ipynb) Not yet available.</span>
* ```tutorial/```
  * [```00.00-scala_preface.ipynb```](tutorial/00.00-scala_preface.ipynb) Preface
  * [```01.[01-06]-scala_introduction.ipynb```](tutorial/01.01-scala_introduction-values_functions_and_types.ipynb) Introduction to Scala
  * [```00.[01-02]-set_theory.ipynb```](tutorial/02.01-set_theory-core_set_theory.ipynb) Coding set theory with ```mathlib```

## Running these notebooks

We document two options to run the examples and tutorial: the mybinder service and a local installation on your computer.

### Free mybinder service

You can create an interactive Jupyter lab instance of this repository for free on mybinder.org by clicking [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/markblokpoel/mathlib-examples/main?urlpath=lab/tree/notebooks/welcome.ipynb). Please note that this service might at times be slow.

### Installation instructions

If you want to install Jupyter lab with Scala support on your own machine, you can follow the instructions below. Please note that some instructions will vary for different operating systems (e.g., Windows, macOS or Linux). We assume you have installation rights on your machine and are familiar with the Terminal (macOS and Linux) or Powershell (Windows).

**Step 1**

First check if you already have Python 3 installed on your machine. Open up a Terminal or Powershell and run the following command.

```
python3 --version
```

You should see the version of Python as output, if not then go to [https://www.python.org/downloads/](https://www.python.org/downloads/) and download and install the latest version of Python 3.

You will also need ```pip``` to install Jupyter. Check if you have it installed with:

```
pip --version
```

```pip``` should come by default with the official Python release. If you have installed Python in a different way, please refer to your installation method to also install ```pip```.

**Step 2**

Install Jupyter Lab following by running the following command in a terminal (macOS and Linux) or the Powershell (Windows).

```
pip install jupyterlab
```

Note: If you are using a macOS version that comes with Python 2, run ```pip3``` instead of ```pip```.


Test the if the installation is working properly by running this command and check if you get some output.

```
jupyter --version
```

**Step 3**

Install the Almond kernel version 0.13.1 with Scala 2.13.8 support (so you can use Scala in Jupyter). The versions are important! For the original instructions see [https://almond.sh/docs/quick-start-install](https://almond.sh/docs/quick-start-install).

First, install a Java Virtual Machine (JVM) needs to on your system. You can check if a JVM is installed by running from a Terminal or Powershell.

```
java -version
```

It should output something like this:

```
java version "1.8.0_121"
Java(TM) SE Runtime Environment (build 1.8.0_121-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.121-b13, mixed mode)
```

If you don't have a JVM yet, we recommend installing AdoptOpenJDK (https://adoptopenjdk.net/) version 8.

Then, the Almond kernel can (for macOS and Linux users) be fetched and installed with coursier:

```
curl -Lo coursier https://git.io/coursier-cli

chmod +x coursier

./coursier launch --fork almond:0.13.1 --scala 2.13.8 -- --install

rm -f coursier
```

If you receive the error: "Cannot find default main class. Specify one with -M or --main-class", run this command instead:

```
./coursier launch --fork almond:0.13.1 --scala 2.13.8  -M almond.ScalaKernel -- --install
```

If you use a Windows OS, use these lines of code instead
```
bitsadmin /transfer downloadCoursierCli https://git.io/coursier-cli "%cd%\coursier"

bitsadmin /transfer downloadCoursierBat https://git.io/coursier-bat "%cd%\coursier.bat"

.\coursier launch --fork almond:0.13.1 --scala 2.13.8 -- --install
```

**Step 4**

You can check that you have the kernel correctly installed by entering the following command. It should list Scala and a Python 3 version.

```
jupyter kernelspec list
```

**Step 5 (Optional)**

If you want to enable Plotly support for displaying graphs you need to install the Jupyterlab extension using the following Terminal command.

```
jupyter labextension install jupyterlab-plotly
```

You can check if the extension installed correctly using this command.

```
jupyter labextension list
```

**Step 6**

Finally, download a copy of the repository from the releases page and unpack the files. Then navigate to the folder that contains the Scala notebook(s) and run:

```
jupyter lab
```

## Licenses

- Scala is licensed under the [Apache License](https://www.apache.org/licenses/LICENSE-2.0), Version 2.0 (the “License”).
- Almond is [Copyright 2018 Alexandre Archambault](https://github.com/almond-sh/almond/blob/master/LICENSE).
- Plotly-scala is Liscenced under the [LGPL v3 license](https://www.gnu.org/licenses/lgpl-3.0.en.html).
- Plotly.js is free and open-source software, licensed under the [MIT license](https://github.com/plotly/plotly.js/blob/master/LICENSE).
- JupyterLab uses a shared copyright model that enables all contributors to maintain the copyright on their contributions. All code is licensed under the terms of the revised [BSD license](https://github.com/jupyterlab/jupyterlab/blob/master/LICENSE).
