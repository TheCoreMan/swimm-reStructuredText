===============
Displaying Code
===============

Since ReStructuredText is used quite often by programmers, there are a few ways to display code!

Quick n' Dirty: Literal Block
=============================

This is the easiest way to include code. Use a double column ``::`` and indent the literal block:

::

    def hello():
        print("Hello world!")

For Control Freaks: Code Block Directive
========================================

By default, when using a literal block, the language is Python. When displaying code, sometimes we want
more control: which language is it in? Do we want to display line numbers? etc. For that, the ``code-block``
directive comes to the rescue!

First, you can choose the language of the code example. Here we're using *Rust*, not Python:

.. code-block:: rust
   
   fn main() {
       println!("Hello World!");
   }

To display line numbers as well, use the ``:linenos:`` option (this example is in *go*):

.. code-block:: go
   :linenos:

   func main() {
       fmt.Println("Hello World!")
   }

You can also emphasize specific lines using the ``:emphasize-lines:`` directive. In this example, we'll emphasize the fourth and fifth lines (and just for fun - let's use *Clojure*, this time):

.. code-block:: clojure
   :emphasize-lines: 4,5

   (ns clojure.examples.hello
      (:gen-class))
   (defn hello-world []
      (println "Hello World"))
   (hello-world)

Another cool thing to do is caption the code example using the ``caption`` option:

.. code-block:: cpp
   :caption: Hello world in C++

   #include <iostream>

   int main() {
       std::cout << "Hello World!";
       return 0;
   }

And of course, you can combine all the options (and there are a lot more)!

.. code-block:: C
   :caption: Hello world in C
   :emphasize-lines: 4
   :linenos:
   
   #include <stdio.h>

   int main() {
      printf("Hello, World!");
      return 0;
   }

For External Files: Literal Include
===================================

If you want to include another code file and display it in the documentation (useful for long texts), you can do so using the ``literalinclude`` directive. Here we'll include the ``example_code.py`` file:

.. literalinclude:: example_code.py

