---
title: Data transformation functions for strings
description: A reference document listing built-in convenience functions to support data transformation in expressions for strings.
---

# Strings

A reference document listing built-in convenience functions to support data transformation in expressions for strings.

!!! note "JavaScript in expressions"
		You can use any JavaScript in expressions. Refer to [Expressions](/code-examples/expressions/) for more information.

[[% import "_macros/data-functions.html" as dataFunctions %]]

[[% for func in df_string %]]
[[ dataFunctions.dataFunctions("string", func.funcName, func.returns, func.description, func.args, func.examples ) ]]
[[% endfor %]]
