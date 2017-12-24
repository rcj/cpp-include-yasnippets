# C++ include yasnippets #

[YASnippets](https://github.com/joaotavora/yasnippet) for all standard includes
in the C++ standard.

## Installation ##

Either add the location of the snippet directory to **yas-snippet-dirs** or place
the directory inside a directory in this path.

    (add-to-list 'yas-snippet-dirs "<snippets_directory>")

The snippets will be active for **c++-mode** and will be added to the **includes**
sub-group (assuming you named the directory **includes**).

As I work with different standard library implementations which don't all use
the **std** namespace, I have a function that returns the appropriate include
path for the current file. If you are only using a standard library
implementation provided by your compiler vendor either just return
**"<__include-path__>"** from the function or replace the call in the snippets.

### Add include directive function ###

Add the following function to your configuration:

    (defun rcj-cc-mode-std-include-directive-for-file (include-path) (concat "<" include-path ">"))

### Replace the function call with std include ###

    cd <snippet-directory> && sed -i 's/`(rcj-cc-mode-std-include-directive-for-file "\(.*\?\)")`/<\1>/'
