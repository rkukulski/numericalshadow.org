References
==========

On this page you can define commonly used notes for [RefNotes
plugin](https://www.dokuwiki.org/plugin:refnotes). Every note is defined
as collection of data *fields*. There are number of ways to organize the
note definitions:

-   Group a number of notes into single data table (*sheet*). The first
    row of the table is used to specify which field the corresponding
    column contains.
-   Use separate table for each note (*card*). The table should have two
    columns where the first column is used to specify the field names.
-   Define notes using [BibTeX](https://en.wikipedia.org/wiki/BibTeX)
    syntax. BibTeX entries have to be wrapped into a
    \'\'`'' section. The key of BibTeX entry serves as name of the note. The namespace can be either specified as part of the key or in a separate comment (see example below) for all entries that follow.
      * Store one note per page as [[doku>plugin:data|Data plugin]] entry. This way the notes are stored in a database, which allows to make queries against the bibliography data, for example, see all books of a certain author. Unfortunately Data plugin allows only one ''dataentry'' section per page.

    For sheets and cards plugin does not make a distinction between normal table cells and header cells. The field name cells are identified only based on their content. The names are case insensitive and can also be specified using locale-specific labels. BibTeX and ''dataentry'' sections support only field names. The full list of field names is provided in [[doku>plugin:refnotes:refdb|reference database documentation]].


    ===== Note sheet example =====

    ^  Note name  ^  Note text  ^
    ^ :ref:sample1 | A sample reference. |
    ^ :ref:sample2 | A sample reference with //some// **formatting**. |
    ^ :ref:sample3 | A sample reference with a [[http://www.dokuwiki.org/|link.]] |


    ===== Note card example =====

    ^ Note name ^  :ref:knuth-aop-2  ^
    ^ Author    | Donald Knuth |
    ^ Title     | The Art of Computer Programming, Volume 2: Seminumerical Algorithms |
    ^ Edition   | Third Edition |
    ^ Published | 1997 |
    ^ Publisher | Addison-Wesley |
    ^ Pages     | xiv + 762 pp. |
    ^ ISBN      | 0-201-89684-2 |
    ^ URL       | http://en.wikipedia.org/wiki/The_Art_of_Computer_Programming |


    ===== BibTeX example =====

    <code bibtex>
    @Comment{refnotes,
      namespace = "ref:prog"
    }

    @Book{GangOfFour,
      author     = "Erich {Gamma} and Richard {Helm} and Ralph {Johnson} and John {Vlissides}",
      author-ref = "Gamma, et al.",
      title      = "Design Patterns: Elements of Reusable Object-Oriented Software",
      publisher  = "Addison-Wesley",
      year       = 1994,
      address    = "Reading, Mass.",
      pages      = 395,
      isbn       = "0-201-63361-2",
      url        = "http://en.wikipedia.org/wiki/Design_Patterns"
    }

    @Article{:ref:Knuth-LCE-1985,
      author    = "Donald Knuth",
      title     = "Deciphering a linear congruential encryption",
      journal   = "IEEE Transactions on Information Theory",
      volume    = "31(1)",
      year      = 1985,
      month     = "Jan",
      publisher = "IEEE",
      pages     = "49-52",
      issn      = "0018-9448",
      url       = "http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=1056997"
    }
    `

Dataentry example
-----------------

The dataentry below is wrapped into
\'\'`'' section to be properly presented in absence of [[doku>plugin:data|Data plugin]].

<code>
---- dataentry refnotes ----
note-name : :ref:prog:Hunt&Thomas(1999)
authors   : Andrew Hunt, David Thomas
title     : The Pragmatic Programmer: From Journeyman to Master
published : 1999
publisher : Addison-Wesley Professional
pages     : 352
isbn      : 0-201-61622-X
url       : http://en.wikipedia.org/wiki/The_Pragmatic_Programmer
----
`
