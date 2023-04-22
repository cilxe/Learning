<h1>Regular Expression</h1>


- Match URLs
  ```
  # Start with  http:// or https://  and *.*
  /^(http|https):\/\/[^\s/$.?#].[^\s]*$/

  # With or without http:// or https:// begins.
  /^((http|https):\/\/)?[^\s/$.?#].[^\s]*$/
  ```


- Match Empty lines  
  ```
  ^\s*(?=\r?$)\n
  ```

- Remove duplicate lines (Match and replace)
  ```
  ^(.+)((?:\r?\n.*)*)(?:\r?\n\1)$
  $1$2
  ```
