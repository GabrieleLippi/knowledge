In Elm we can create web apps in two different forms:

  1 returning and html that integrates in a document -> `Browser.element`
  2 returning and entire new document -> `Browser.document`

in case of multiple pages, this approach has some downwards like blank screens
when switching between pages and redundant code, the solution in this case is:

  3 create our progam with Browser.application

Touching the DOM is extraordinarily slow compared to the sort of computations that happen in a normal application. Always reach for **Html.Lazy** and **Html.Keyed** first.
Verify with profiling as much as possible.
