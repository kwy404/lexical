---
'@lexical/markdown': patch
---

[fix] Markdown import reads a code fence language that holds `+` or `#`, such as ```` ```c++ ````, ```` ```c# ```` or ```` ```f# ````, as that whole language instead of `c` or `f` with the rest kept as metadata, and typing ```` ```c++ ```` and a space now starts a code block

Verify: import ```` ```c++ ```` or ```` ```c# ```` fences and check the code block's language, and that `$convertToMarkdownString` writes the fence back unchanged (it wrote ```` ```c ++ ```` before).
