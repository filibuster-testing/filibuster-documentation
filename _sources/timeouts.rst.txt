.. |br| raw:: html

      <br>

Timeout Testing
===============

Filibuster supports testing timeouts in a variety of ways.  With our Python
driver for Python's ``requests`` library, if a timeout is specified at the
callsite of a remote call, Filibuster can either throw the timeout exception
immediately, wait the timeout period and then throw, or conditionally -- through
the analysis file -- a custom timeout can be specified that can be specified
programatically, allowing the developer to wait either slightly before the
timeout duration or wait slightly past the timeout duration.  This is useful in
detecting cascading timeout failures.  

For more information, see our Netflix example in the corpus, which contains a
misconfigured set of nested timeouts: an outer timeout which is shorter than the
inner timeout.