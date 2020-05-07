# HTML

An HTML _document_ is defined by a _tree_
Each _tree node_ can be:
- _Element_ - defines the document structure
- _Text node_ - defines the document visible text

# Programmatic HTML generation

```
// Option 1

System.out.println("<html><head><title>The title</title></head><body>")

System.out.println("<html><head><title>")
System.out.println("The title")
System.out.println("</title></head>")

// Option 2

Element html = new Element("html")
Element head = new Element("head")
Element title = new Element("title")
Text titleText = new Text("The title")
html.addChild(head)
head.addChild(title)
title.addChild(titleText)

html.printTo(System.out)

// Option 3

element("html").with(
    element("head").with(
        element("title").with("the title")
    )
)

html().with(
  head().with(
    title().with("the title")
  )
)

// Domain specific language (DSL)
// Internal DSL
// - Internal because it uses another language (Java in this case)
// to define the DSL
// - Domain specific because it is used with a single purpose

Element commandResult = someFunction;

Element html = 
  html(
    head(
      title("the title")
    ),
    body(
      h1("This is a section"),
      commandResult,
    )
  );

```
