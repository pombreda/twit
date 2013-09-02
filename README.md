twit
====
[*the slightly less stupid content tracker*](git/git)

what?
-----
An implementation of git in golang.

Initially this will be a read-only implementation, but eventually should evolve
into a fully read-write implementation.

why?
----
Because.

More specifically, I felt like there are were some significant improvements
which could be made in:
  * Speed (there are many embarassingly parallel tasks in git which are not
    parallel in the C implementation due to potential implementation complexity,
    but which are trivial to parallelize efficiently in go).
  * Cross-platform support (git's windows implementation is quite slow and is
    a second-class citizen).
  * [Library support](riannucci/libtwit). libgit wasn't so hot, and libgit2
    seems to be a pretty straightforward port of git to a library (meaning that
    many of the non-parallelized/non-threadsafe design decisions are carried
    over from git).

how? (a.k.a. installation)
--------------------------

  1. set up your [go environment](http://golang.org/doc/install#install).
  1. `go get github.com/riannucci/twit`
  1. there is no step #3

Access documentation the same way that you do with git (`twit help <topic>`).
