# wikiparser

Wikiparser is a Wikipedia offline reader. It parses the xml and sql dumps
from Wikipedia in order to build a local sqlite database. The conversion
to html is done by libmwparser on which sqlite doesn't depend.

libmwparser intends to be compatible with mediawiki parser. It supports:
- formatting (lists, tables, headings, links, images, ...)
- magic words, namespaces
- builtin functions
- parser functions
- interwiki link (incomplete)
- tag extensions like gallery, math (converted to mathml by itex2MML)
- valid xml node as an output

libmwparser doesn't support (for now):
- translated magic words and parser function name
- some tag exentions used by Wikipedia, such as timeline and dynamicpagelist

libmwparser is not finished and should be mostly rewritten to correct the
code and to offer an usable api. Parsing is done in 2 phases:

1 - Expand template and parser function
  Works in most cases but sould support translated magic word and function 
  name and must finish (check limit and infinite loop)

2 - Render the consequent wiki code to xhtml
  Needs a massive cleanup and rewritting (i.e images and links) after finishing
	phase one.

See INSTALL for further instructions.
