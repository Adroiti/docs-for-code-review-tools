Pattern: Wrong include order

Issue: -

## Description

We want to ensure that headers appear in the right order:
	1) for foo.cc, foo.h  (preferred location)
	2) c system files
	3) cpp system files
	4) for foo.cc, foo.h  (deprecated location)
	5) other headers

We classify each include statement as one of those 5 types using a number of techniques. The include_state object keeps track of the highest type seen, and complains if we see a lower type after that.
