
# Getting started guide
## Importing framework (IntelliJ guide)
- Create new Maven IntelliJ project.
- Then select File -> New -> Module from existing sources
- Select file to import: [pom.xml](pom.xml) file inside HTML framework for java
- Add dependency (see under for Maven guide)
## Using the Framework
The framework builds on the concept of having a series of objects that represents HTML
tags. Some tags depends on each other tags, and we will use everything to create a
page/HTML file, and using the builder pattern to create CSS brackets that are added
together in CSS to create a CSS file
HEADER
To use the framework to create a HTML page, the first thing is to create a new header object
using the generate method in this class. This needs to contain a title, optional is a navigation
list in the form of a nav object and or just an optional paragraph. The generator will detect
and create the object based on what we give
Example of just title, and with a paragraph
Examples:
Header header1= Header.generate("This is title");
Header header2= Header.generate("This is title", genericParagraph);
Example with just nav and nav and paragraph, we will show how to generate nav and
paragraph under:
Header header3= Header.generate("This is title", nav);
Header header4= Header.generate("This is title", genericParagraph, nav);
NAVIGATION
If we want with a navigation we first need to create a nav object, to do this we need 2 arrays
of strings, one with the link URL and the other for the link text:
private static String[] linksList = new String[]{"www.google.com",
"www.amazon.com", "www.pottermore.com"};
private static String[] linksTextList = new String[]{"google", "amazon",
"pottermore"};
We then generate a navigation with the nav.generate method, including the link list, the link
text list, what the ID identifier and the class identifier will be
Nav nav = Nav.generate(linksList, linksTextList, "mainNav",
"navClass");
MAINTAG
After we have created a header we need to create a main tag object. This can either be
created from a string, an array of strings or a section, or an array of sections. We will once
again use the generate method on this class. Example of how to create section will be below
Example of array of string
String[] arrayString = new String[]{"<div> <p>manuall insertion </p>
</div>",
"<div> <p>lorem ipsum insertion </p> </div>" };
Example of array of Sections
Section[] sectionsArray = new Section[]{section1, section2};
Examples of main tag:
MainTag mainTag1 = MainTag.generate("<div> <p>manuall insertion </p>
</div>");
MainTag mainTag2 = MainTag.generate(arrayString);
MainTag mainTag3 = MainTag.generate(section);
MainTag mainTag4 = MainTag.generate(sectionsArray);
ARTICLES
To create a section we need an array of articles, so we will be looking at creating an article
first.
We have have different kinds of articles to create they contain, examples on forms will be
further down
Title paragraphString, article ID, group identifier
Title Paragraph, ArtcileID, group identifier
Title paragraph, form, article ID, class identifier
title, paragraph string, form, article ID, group identifier
Example of making the articles
Article article1 = Article.generate("Article", "<p> stuff </p>",
"article1", "articleclass");
Article article2 = Article.generate("Article", genericParagraph,
"article2", "articleclass");
Article article3 = Article.generate("Article", genericParagraph, form,
"article3", "articleclass");
Article article4 = Article.generate("Article", "<p> stuff </p>", form,
"article4", "articleclass");

