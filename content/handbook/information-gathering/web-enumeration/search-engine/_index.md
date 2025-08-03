---
title: Search Engine Discovery
type: handbook
weight: 5
---
---

### Cheat sheet

| Operator          | Operator Description                                | Example                                                    | Example Description                                                              |
|-------------------|-----------------------------------------------------|-------------------------------------------------------------|----------------------------------------------------------------------------------|
| site:             | Limits results to a specific website or domain.     | site:example.com                                            | Find all publicly accessible pages on example.com.                              |
| inurl:            | Finds pages with a specific term in the URL.        | inurl:login                                                 | Search for login pages on any website.                                          |
| filetype:         | Searches for files of a particular type.            | filetype:pdf                                                | Find downloadable PDF documents.                                                |
| intitle:          | Finds pages with a specific term in the title.      | intitle:"confidential report"                               | Look for documents titled "confidential report".                                |
| intext: / inbody: | Searches for a term within the body text of pages.  | intext:"password reset"                                     | Identify webpages containing the term “password reset”.                         |
| cache:            | Displays the cached version of a webpage.           | cache:example.com                                           | View the cached version of example.com.                                         |
| link:             | Finds pages that link to a specific webpage.        | link:example.com                                            | Identify websites linking to example.com.                                       |
| related:          | Finds websites related to a specific webpage.       | related:example.com                                         | Discover websites similar to example.com.                                       |
| info:             | Provides info about a webpage.                      | info:example.com                                            | Get basic details about example.com.                                            |
| define:           | Provides definitions of a word or phrase.           | define:phishing                                             | Get a definition of "phishing".                                                 |
| numrange:         | Searches for numbers within a range.                | site:example.com numrange:1000-2000                         | Find pages containing numbers between 1000 and 2000.                            |
| allintext:        | Finds pages with all terms in the body text.        | allintext:admin password reset                              | Search for pages with both "admin" and "password reset".                        |
| allinurl:         | Finds pages with all terms in the URL.              | allinurl:admin panel                                        | Look for pages with "admin" and "panel" in the URL.                             |
| allintitle:       | Finds pages with all terms in the title.            | allintitle:confidential report 2023                         | Search for titles with "confidential," "report," and "2023".                    |
| AND               | Requires all terms to be present.                   | site:example.com AND (inurl:admin OR inurl:login)           | Find admin or login pages on example.com.                                       |
| OR                | Includes pages with any of the terms.               | "linux" OR "ubuntu" OR "debian"                             | Search for pages mentioning Linux, Ubuntu, or Debian.                           |
| NOT               | Excludes pages with the term.                       | site:bank.com NOT inurl:login                               | Find pages on bank.com excluding login pages.                                   |
| * (wildcard)      | Represents any character or word.                   | site:social.com filetype:pdf user* manual                   | Search for user guides like "user manual", "user handbook", etc.                |
| .. (range)        | Numerical range filter.                             | site:ecommerce.com "price" 100..500                         | Find products priced between 100 and 500.                                       |
| " "               | Exact phrase match.                                 | "information security policy"                               | Find documents with that exact phrase.                                          |
| - (minus)         | Exclude specific terms.                             | site:news.com -inurl:sports                                 | Search news.com but exclude sports pages.                                       |
