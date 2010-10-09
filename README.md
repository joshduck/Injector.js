Injector.js 
===========

About
-----

Injector.js is a helper library to easy the pain of mixing asynchronous 
JavaScript and dynamic content building with third party scripts which insist 
`document.write` is still a good idea.

Usage
-----

See `examples/index.html` for usage.

Methods
-------

* `Injector(options)`
  Constructor.

* `Injector.setContainer(element)` 
  Set the parent container that HTML should be injected into.
  Can also be set via options.container.
  
* `Injector.setSibling(element)`
  Set the node which HTML should be injected *before*.
  Can also be set via options.sibling.
  
* `Injector.eval(script)`
  Evaluate inline script, `document.write` calls will be captured and output 
  will be injected either at current position.
  
* `Injector.insert(html)`
  Insert HTML at current position, evaluating scripts manually and overriding 
  `document.write` calls.
  
* `Injector.onComplete(callback)`
  Callback to execute after `insert()` or `eval()`
  
Issues
------

* Calling `Injector.insert()` or `Injector.eval()` while scripts are still 
  being inserted will cause issues.

Todo
----

* Cross browser testing.

* Convert to standalone module rather than class instance.

* Add queue, so that `insert()` and `eval()` can be called at any time without 
  side effects.
  
Thanks
------

Inspired and seeded from code shared by John Resig: http://ejohn.org/blog/xhtml-documentwrite-and-adsense/