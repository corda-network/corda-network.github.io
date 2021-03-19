# How to create a new page, route, navigation section and navigation page link together step by step

1. In the [project](https://github.com/corda-network/corda-network.github.io) repository, go to ```content``` folder. It is the folder where all the content lives.
2. If you want to add new **section**, simply add new folder at the corresponding level. It could be top level or nested inside other sections.

    Example: 
      ```4.foldername```
      ```4.foldername with additional words```

    2.1 Hidden sections should start with ```_``` and will not be part of the site.

    Example: 
        ```_foldername``` or ```_3.foldername```
3. If you want to create new **page**, add new ```.md``` file in the respective section's folder or even at root level. \
    3.1 Hidden files should start with ```_``` and will not be part of the site.

    Example: \
      ```_filename additional words.md``` \
      ```_1.filename additional words.md``` 
4. Everything on the site is automatically generated, no further steps required: \
    4.1 Site navigation \
    4.2 Site routing \
    4.3 Site pages
5. Notes \
    5.1. Sections and Pages should start with number, followed by dot and spaces between words. That way you can control the order in which they appear in the navigation, only hidden section or pages are exception may not follow this rule.

      Example for file name: 
      ```2.filename with multiple words.md```

      Example for folder name: 
      ```1.foldername with multiple words```

    5.3. In case we want the url name for folder or page to be different from the file name, we should add the route url alternative in brackets, with dashes between words, if not we should leave it: \
      Example for file name: 
      ```2.code of conduct (code-conduct).md```

      Example for folder name:
      ```5.business policy (policy)```

      Then the url for this those two examples will look like this:
      ```https://corda.network/policy/code-conduct```

    5.2. The ```home``` folder at the root level of the content folder is exception of all the rules above and should stays as it is. It holds the markdown files served for the home page.

    5.3. If we want to add new file and this file to be at the top of submenu list of pages, we can add negative sign in from og the file name

      Example:
      ```-1.filename.md```
      ```-2.filename.md```

    The samller the number is, it will be shown on the top of submenu list. So ```-2....``` will be on top of ```-1....``` and so on in the navigation menu.