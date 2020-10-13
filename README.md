# Golang QuickTemplate

QuickTemplate syntax highlighting and code competition

## Features

- QuickTemplate Snippets
- Code Completion:
  - Go
  - Html
  - CSS
- Syntax Highlighting
  - QuickTemplate
  - Go
  - Html
  - CSS
  - JavaScript

## Snippets

Note: From snippets/qtpl.json file [^regex]

| Prefix | Body | Notes |
| ----------- | ----------- | ----------- |
| {%  | "{% $0 %}" | Doesn't really work ( auto closes w/ autoClosingPairs) |
| cat | "{% cat \"${0:path}\" %}" |
| code | ["{% code","$0","%}"] |
| collapsespace | ["{% collapsespace %}", "\t$0", "{% endcollapsespace %}"] |
| comment | ["{% comment %}", "\t$0", "{% endcomment %}"] |
| else | "{% else %}$0" |
| elseif | "{% elseif $1 %}$0" |
| for | ["{% for ${1:i} := ${2:0}; $1 < ${3:n}; $1++ %}", "\t$0", "{% endfor %}"] |
| func | ["{% func $1($2) %}", "\t$0", "{% endfunc %}"] |
| if | ["{% if $1 %}", "\t$0", "{% endif %}"] |
| ifelse | ["{% if $1 %}", "\t$2", "{% else %}", "$0", "{% endif %}"] |
| import | "{% import \"$0\" %}" |
| interface | ["{% interface ${1:name} {", "\t$0", "} %}"] |
| switch | ["{% switch $1 %}", "{% case $2 %}","$0","${3:{% default %\\}\n}","{% endswitch %}"] |
| stripspace | ["{% stripspace %}", "\t$0", "{% stripspace %}"] |

## Known Issues

No javascript completion

Html & CSS code completion is copied from [vscode-extension-samples](https://github.com/microsoft/vscode-extension-samples)/[lsp-embedded-language-service](https://github.com/microsoft/vscode-extension-samples/tree/master/lsp-embedded-language-service)

----

### Release Notes

#### 0.0.1

Initial release of qtpl

[^regex]: Regex: /^ +("([A-z ]+)": {\n) +("prefix": "([A-z0-9\{% ]+)",\n) +("body": (.*)\n) +(},?)/gm
  Replacer: | $4 | $6 |
