# .editorconfig for C\#

This document describes the standard `.editorconfig` settings for C# files, which are extracted info [`files/.editorconfig`](files/.editorconfig) file via [`files/UpdateEditorConfig.ps1`](files/UpdateEditorConfig.ps1).

The standard settings for `charset`, `end_of_line`, `insert_final_newline`, and `trim_trailing_whitespace` should be inherited from [the `[*]` section](../editorconfig.md).

```editorconfig
[*.cs]
indent_size = tab
indent_style = tab
tab_width = 4
```

We have always used tabs of width 4 for C#.

```editorconfig
dotnet_analyzer_diagnostic.severity = warning
```

Enable code style enforcement (`IDE????` rules). These rules do not respect the `value : severity` syntax (e.g. `true : suggestion`), so `dotnet_diagnostic.IDE????.severity` rules immediately follow their corresponding settings, when possible.

## [Style: Language and Unnecessary Code Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/language-rules)

```editorconfig
dotnet_style_qualification_for_field = false : warning
dotnet_style_qualification_for_property = false : warning
dotnet_style_qualification_for_method = false : warning
dotnet_style_qualification_for_event = false : warning
dotnet_diagnostic.IDE0003.severity = warning
dotnet_diagnostic.IDE0009.severity = warning
```

Never use `this.` qualifier.

```editorconfig
dotnet_style_predefined_type_for_locals_parameters_members = true : warning
dotnet_style_predefined_type_for_member_access = true : warning
dotnet_diagnostic.IDE0049.severity = warning
```

Always use language keywords (e.g. `int`) instead of framework type names (e.g. `Int32`).

```editorconfig
csharp_preferred_modifier_order = public, private, protected, internal, new, abstract, virtual, sealed, override, static, readonly, extern, unsafe, volatile, async : warning
dotnet_diagnostic.IDE0036.severity = warning
dotnet_style_require_accessibility_modifiers = for_non_interface_members : warning
dotnet_diagnostic.IDE0040.severity = warning
dotnet_style_readonly_field = true : warning
dotnet_diagnostic.IDE0044.severity = warning
csharp_prefer_static_local_function = true : suggestion
dotnet_diagnostic.IDE0062.severity = suggestion
```

Always use modifiers, in the preferred order. Use `readonly` when possible. Suggest `static` on local functions.

```editorconfig
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity : none
dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary : suggestion
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity : none
dotnet_style_parentheses_in_other_operators = never_if_unnecessary : suggestion
dotnet_diagnostic.IDE0047.severity = suggestion
dotnet_diagnostic.IDE0048.severity = suggestion
```

Allow the developer to decide when parentheses around certain arithmetic and Boolean operators improve clarity.

```editorconfig
dotnet_style_object_initializer = true : suggestion
dotnet_diagnostic.IDE0017.severity = suggestion
csharp_style_inlined_variable_declaration = true : suggestion
dotnet_diagnostic.IDE0018.severity = suggestion
dotnet_style_collection_initializer = true : suggestion
dotnet_diagnostic.IDE0028.severity = suggestion
dotnet_style_prefer_auto_properties = true : suggestion
dotnet_diagnostic.IDE0032.severity = suggestion
dotnet_style_explicit_tuple_names = true : warning
dotnet_diagnostic.IDE0033.severity = warning
csharp_prefer_simple_default_expression = true : suggestion
dotnet_diagnostic.IDE0034.severity = suggestion
dotnet_style_prefer_inferred_tuple_names = true : suggestion
dotnet_diagnostic.IDE0037.severity = suggestion
csharp_style_prefer_local_over_anonymous_function = true : suggestion
dotnet_diagnostic.IDE0039.severity = suggestion
csharp_style_deconstructed_variable_declaration = true : suggestion
dotnet_diagnostic.IDE0042.severity = suggestion
dotnet_style_prefer_conditional_expression_over_assignment = true : suggestion
dotnet_diagnostic.IDE0045.severity = suggestion
dotnet_style_prefer_conditional_expression_over_return = true : none
dotnet_diagnostic.IDE0046.severity = none
dotnet_style_prefer_compound_assignment = true : suggestion
dotnet_diagnostic.IDE0054.severity = suggestion
dotnet_diagnostic.IDE0074.severity = suggestion
csharp_style_prefer_index_operator = true : suggestion
dotnet_diagnostic.IDE0056.severity = suggestion
csharp_style_prefer_range_operator = true : suggestion
dotnet_diagnostic.IDE0057.severity = suggestion
dotnet_style_prefer_simplified_interpolation = true : suggestion
dotnet_diagnostic.IDE0071.severity = suggestion
dotnet_style_prefer_simplified_boolean_expressions = true : warning
dotnet_diagnostic.IDE0075.severity = warning
csharp_style_implicit_object_creation_when_type_is_apparent = true : suggestion
dotnet_diagnostic.IDE0090.severity = suggestion
csharp_style_prefer_tuple_swap = true : warning
dotnet_diagnostic.IDE0180.severity = warning
dotnet_style_prefer_inferred_anonymous_type_member_names = true : suggestion
```

Use modern expression syntax.

```editorconfig
dotnet_diagnostic.IDE0010.severity = suggestion
dotnet_diagnostic.IDE0072.severity = suggestion
```

Don't require missing cases to be added to switch statements/expressions.

```editorconfig
dotnet_diagnostic.IDE0070.severity = suggestion
```

Don't force `HashCode.Combine` to be used.

```editorconfig
dotnet_diagnostic.IDE0082.severity = warning
```

Require `nameof(T)` instead of `typeof(T).Name`.

```editorconfig
csharp_style_namespace_declarations = file_scoped : suggestion
dotnet_diagnostic.IDE0160.severity = suggestion
dotnet_diagnostic.IDE0161.severity = suggestion
```

Use file-scoped namespaces.

```editorconfig
csharp_style_throw_expression = true : suggestion
dotnet_diagnostic.IDE0016.severity = suggestion
dotnet_style_coalesce_expression = true : warning
dotnet_diagnostic.IDE0029.severity = warning
dotnet_diagnostic.IDE0030.severity = warning
dotnet_style_null_propagation = true : suggestion
dotnet_diagnostic.IDE0031.severity = suggestion
dotnet_style_prefer_is_null_check_over_reference_equality_method = true : suggestion
dotnet_diagnostic.IDE0041.severity = suggestion
csharp_style_prefer_null_check_over_type_check = true : suggestion
dotnet_diagnostic.IDE0150.severity = suggestion
csharp_style_conditional_delegate_call = true : suggestion
dotnet_diagnostic.IDE1005.severity = suggestion
```

Use modern null-checking syntax.

```editorconfig
csharp_style_var_elsewhere = true : suggestion
csharp_style_var_for_built_in_types = true : suggestion
csharp_style_var_when_type_is_apparent = true : suggestion
dotnet_diagnostic.IDE0007.severity = suggestion
dotnet_diagnostic.IDE0008.severity = suggestion
```

Use `var` everywhere.

```editorconfig
csharp_style_expression_bodied_constructors = false : suggestion
dotnet_diagnostic.IDE0021.severity = suggestion
csharp_style_expression_bodied_methods = true : suggestion
dotnet_diagnostic.IDE0022.severity = suggestion
csharp_style_expression_bodied_operators = true : suggestion
dotnet_diagnostic.IDE0023.severity = suggestion
dotnet_diagnostic.IDE0024.severity = suggestion
csharp_style_expression_bodied_properties = true : suggestion
dotnet_diagnostic.IDE0025.severity = suggestion
csharp_style_expression_bodied_indexers = true : suggestion
dotnet_diagnostic.IDE0026.severity = suggestion
csharp_style_expression_bodied_accessors = true : suggestion
dotnet_diagnostic.IDE0027.severity = suggestion
csharp_style_expression_bodied_lambdas = true : suggestion
dotnet_diagnostic.IDE0053.severity = suggestion
csharp_style_expression_bodied_local_functions = true : suggestion
dotnet_diagnostic.IDE0061.severity = suggestion
```

Suggest expression-bodied members everywhere but constructors.

```editorconfig
csharp_style_pattern_matching_over_as_with_null_check = true : suggestion
dotnet_diagnostic.IDE0019.severity = suggestion
csharp_style_pattern_matching_over_is_with_cast_check = true : suggestion
dotnet_diagnostic.IDE0020.severity = suggestion
dotnet_diagnostic.IDE0038.severity = suggestion
csharp_style_prefer_switch_expression = true : suggestion
dotnet_diagnostic.IDE0066.severity = suggestion
csharp_style_prefer_pattern_matching = true : suggestion
dotnet_diagnostic.IDE0078.severity = suggestion
csharp_style_prefer_not_pattern = true : suggestion
dotnet_diagnostic.IDE0083.severity = suggestion
csharp_style_prefer_extended_property_pattern = true : suggestion
dotnet_diagnostic.IDE0170.severity = suggestion
```

Suggest pattern matching.

```editorconfig
csharp_prefer_braces = when_multiline : suggestion
dotnet_diagnostic.IDE0011.severity = suggestion
csharp_prefer_simple_using_statement = true : suggestion
dotnet_diagnostic.IDE0063.severity = suggestion
```

Don't use braces around single-line blocks. Suggest `using` statement.

```editorconfig
csharp_using_directive_placement = outside_namespace : warning
dotnet_diagnostic.IDE0065.severity = warning
```

Put `using` directives outside the namespace.

```editorconfig
dotnet_style_namespace_match_folder = true : warning
dotnet_diagnostic.IDE0130.severity = warning
```

Namespace names should match folder names.

```editorconfig
dotnet_diagnostic.IDE0001.severity = warning
dotnet_diagnostic.IDE0002.severity = warning
```

Remove unnecessary name qualification.

```editorconfig
dotnet_diagnostic.IDE0004.severity = warning
```

Remove unnecessary casts.

```editorconfig
dotnet_diagnostic.IDE0005.severity = warning
```

Remove unnecessary using directives.

```editorconfig
dotnet_diagnostic.IDE0035.severity = warning
```

Remove unreachable code.

```editorconfig
dotnet_diagnostic.IDE0051.severity = warning
dotnet_diagnostic.IDE0052.severity = warning
```

Remove unused private members.

```editorconfig
csharp_style_unused_value_expression_statement_preference = discard_variable : none
dotnet_diagnostic.IDE0058.severity = none
csharp_style_unused_value_assignment_preference = discard_variable : warning
dotnet_diagnostic.IDE0059.severity = warning
```

Don't require discard variables for unused return values, but prefer them to unused local variables.

```editorconfig
dotnet_code_quality_unused_parameters = all : suggestion
dotnet_diagnostic.IDE0060.severity = suggestion
```

Flag unused parameters.

```editorconfig
dotnet_diagnostic.IDE0080.severity = suggestion
```

Suggest removing unnecessary null-forgiving operator (`!`).

```editorconfig
dotnet_diagnostic.IDE0100.severity = warning
```

Don't use equality operators with `true` and `false`.

```editorconfig
dotnet_diagnostic.IDE0110.severity = warning
```

Don't use unnecessary discard patterns.

```editorconfig
csharp_style_prefer_primary_constructors = true : suggestion
dotnet_diagnostic.IDE0290.severity = suggestion
resharper_convert_to_primary_constructor_highlighting = hint
```

Primary constructors are not always appropriate.

## [Style: Formatting Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0055)

```editorconfig
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = false
```

Organize using directives.

```editorconfig
csharp_new_line_before_open_brace = all
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

Braces on their own lines.

```editorconfig
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
```

We historically did not indent `switch` statement `case` labels, but we now [use the default style](https://github.com/Faithlife/CodingGuidelines/issues/12).

```editorconfig
csharp_indent_labels = one_less_than_current
csharp_indent_block_contents = true
csharp_indent_braces = false
csharp_indent_case_contents_when_block = false
```

Our standard indentation rules.

```editorconfig
csharp_space_after_cast = true
```

Non-standard but [still popular](https://github.com/Faithlife/CodingGuidelines/issues/13).

```editorconfig
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_parentheses = false
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_parameter_list_parentheses = false
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_declaration_name_and_open_parenthesis = false
csharp_space_between_method_call_parameter_list_parentheses = false
csharp_space_between_method_call_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_after_comma = true
csharp_space_before_comma = false
csharp_space_after_dot = false
csharp_space_before_dot = false
csharp_space_after_semicolon_in_for_statement = true
csharp_space_before_semicolon_in_for_statement = false
csharp_space_around_declaration_statements = false
csharp_space_before_open_square_brackets = false
csharp_space_between_empty_square_brackets = false
csharp_space_between_square_brackets = false
```

Spaces around keywords, around inheritance colons, around binary operators, and after commas and semicolons.

```editorconfig
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

Let the developer decide when and where to wrap lines.

## [Style: Naming Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/naming-rules)

```editorconfig
dotnet_naming_rule.local_functions_rule.severity = warning
dotnet_naming_rule.local_functions_rule.style = upper_camel_case_style
dotnet_naming_rule.local_functions_rule.symbols = local_functions_symbols
dotnet_naming_rule.private_constants_rule.severity = warning
dotnet_naming_rule.private_constants_rule.style = c_lower_camel_case_style
dotnet_naming_rule.private_constants_rule.symbols = private_constants_symbols
dotnet_naming_rule.private_instance_fields_rule.severity = warning
dotnet_naming_rule.private_instance_fields_rule.style = m_lower_camel_case_style
dotnet_naming_rule.private_instance_fields_rule.symbols = private_instance_fields_symbols
dotnet_naming_rule.private_static_fields_rule.severity = warning
dotnet_naming_rule.private_static_fields_rule.style = s_lower_camel_case_style
dotnet_naming_rule.private_static_fields_rule.symbols = private_static_fields_symbols
dotnet_naming_rule.private_static_readonly_rule.severity = warning
dotnet_naming_rule.private_static_readonly_rule.style = s_lower_camel_case_style
dotnet_naming_rule.private_static_readonly_rule.symbols = private_static_readonly_symbols
dotnet_naming_style.c_lower_camel_case_style.capitalization = camel_case
dotnet_naming_style.c_lower_camel_case_style.required_prefix = c_
dotnet_naming_style.m_lower_camel_case_style.capitalization = camel_case
dotnet_naming_style.m_lower_camel_case_style.required_prefix = m_
dotnet_naming_style.s_lower_camel_case_style.capitalization = camel_case
dotnet_naming_style.s_lower_camel_case_style.required_prefix = s_
dotnet_naming_style.upper_camel_case_style.capitalization = pascal_case
dotnet_naming_symbols.local_functions_symbols.applicable_accessibilities = *
dotnet_naming_symbols.local_functions_symbols.applicable_kinds = local_function
dotnet_naming_symbols.private_constants_symbols.applicable_accessibilities = private
dotnet_naming_symbols.private_constants_symbols.applicable_kinds = field
dotnet_naming_symbols.private_constants_symbols.required_modifiers = const
dotnet_naming_symbols.private_instance_fields_symbols.applicable_accessibilities = private
dotnet_naming_symbols.private_instance_fields_symbols.applicable_kinds = field
dotnet_naming_symbols.private_static_fields_symbols.applicable_accessibilities = private
dotnet_naming_symbols.private_static_fields_symbols.applicable_kinds = field
dotnet_naming_symbols.private_static_fields_symbols.required_modifiers = static
dotnet_naming_symbols.private_static_readonly_symbols.applicable_accessibilities = private
dotnet_naming_symbols.private_static_readonly_symbols.applicable_kinds = field
dotnet_naming_symbols.private_static_readonly_symbols.required_modifiers = static, readonly
```

Typical .NET naming and casing rules. Use `m_`, `s_`, and `c_` prefixes for private fields.

## [SYSLIB: Source-generated Code Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/naming-rules)

```editorconfig
dotnet_diagnostic.SYSLIB1045.severity = suggestion
dotnet_diagnostic.SYSLIB1054.severity = none
```

Don't require `GeneratedRegexAttribute` or `LibraryImportAttribute`.

## [StyleCop: Special Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/SpecialRules.md)

```editorconfig
dotnet_diagnostic.SA0001.severity = none
```

## [StyleCop: Spacing Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/SpacingRules.md)

```editorconfig
dotnet_diagnostic.SA1003.severity = none
dotnet_diagnostic.SA1008.severity = none
dotnet_diagnostic.SA1009.severity = none
```

These spacing rules don't work well with spaces after casts.

```editorconfig
dotnet_diagnostic.SA1011.severity = none
dotnet_diagnostic.SA1013.severity = none
```

These spacing rules don't work well with `!` suffixes.

```editorconfig
dotnet_diagnostic.SA1027.severity = none
```

We use tabs. This rule could be enabled with a `stylecop.json` that sets `settings.indentation.useTabs` to `true`.

## [StyleCop: Readability Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/ReadabilityRules.md)

```editorconfig
dotnet_diagnostic.SA1101.severity = none
dotnet_diagnostic.SX1101.severity = warning
```

We don't use `this.`.

```editorconfig
dotnet_diagnostic.SA1116.severity = none
dotnet_diagnostic.SA1117.severity = none
dotnet_diagnostic.SA1118.severity = none
```

The developer can decide how parameter lists are line wrapped.

```editorconfig
dotnet_diagnostic.SA1122.severity = none
```

We don't use `string.Empty`.

```editorconfig
dotnet_diagnostic.SA1133.severity = none
dotnet_diagnostic.SA1134.severity = none
```

The developer can decide how attributes are arranged.

## [StyleCop: Ordering Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/OrderingRules.md)

```editorconfig
dotnet_diagnostic.SA1200.severity = none
```

We put `using` directives outside the namespace. This rule could be enabled with a `stylecop.json` that sets `settings.orderingRules.usingDirectivesPlacement` to `outsideNamespace`.

```editorconfig
dotnet_diagnostic.SA1201.severity = none
dotnet_diagnostic.SA1202.severity = none
dotnet_diagnostic.SA1203.severity = none
dotnet_diagnostic.SA1204.severity = none
```

We aren't strict about the ordering of type elements.

```editorconfig
dotnet_diagnostic.SA1206.severity = none
```

We prefer to put `new` before `static`.

```editorconfig
dotnet_diagnostic.SA1214.severity = suggestion
```

We aren't strict about the ordering of `readonly` fields.

## [StyleCop: Naming Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/NamingRules.md)

```editorconfig
dotnet_diagnostic.SA1300.severity = none
```

This fails on `v1` in namespaces, which could be permitted via `stylecop.json`.

```editorconfig
dotnet_diagnostic.SA1303.severity = none
dotnet_diagnostic.SA1308.severity = none
dotnet_diagnostic.SA1310.severity = none
dotnet_diagnostic.SA1311.severity = none
```

We use `m_`, `s_`, and `c_` field prefixes.

## [StyleCop: Maintainability Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/MaintainabilityRules.md)

```editorconfig
dotnet_diagnostic.SA1407.severity = none
dotnet_diagnostic.SA1408.severity = none
```

We don't require extra parentheses.

## [StyleCop: Layout Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/LayoutRules.md)

```editorconfig
dotnet_diagnostic.SA1503.severity = none
```

We don't require braces around single statements.

```editorconfig
dotnet_diagnostic.SA1504.severity = none
```

Using a single-line getter with a multi-line setter doesn't seem so bad, and it's hard to get automatic style formatters to respect it.

```editorconfig
dotnet_diagnostic.SA1513.severity = none
```

We don't require a blank line after braces.

```editorconfig
dotnet_diagnostic.SA1516.severity = none
```

Sometimes it's nice to omit the blank line between type elements.

## [StyleCop: Documentation Rules](https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/DocumentationRules.md)

```editorconfig
dotnet_diagnostic.SA1600.severity = none
dotnet_diagnostic.SA1601.severity = none
dotnet_diagnostic.SA1602.severity = none
dotnet_diagnostic.SA1604.severity = none
dotnet_diagnostic.SA1605.severity = none
dotnet_diagnostic.SA1611.severity = none
dotnet_diagnostic.SA1615.severity = none
dotnet_diagnostic.SA1618.severity = none
dotnet_diagnostic.SA1619.severity = none
dotnet_diagnostic.SA1623.severity = none
dotnet_diagnostic.SA1629.severity = none
dotnet_diagnostic.SA1633.severity = none
dotnet_diagnostic.SA1642.severity = none
dotnet_diagnostic.SA1643.severity = none
```

XML documentation is not required.

## [Quality: Design Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/design-warnings)

```editorconfig
dotnet_diagnostic.CA1014.severity = none
```

`CLSCompliantAttribute` is not necessary.

```editorconfig
dotnet_diagnostic.CA1030.severity = none
```

"Raise" doesn't always mean ".NET event."

```editorconfig
dotnet_diagnostic.CA1031.severity = suggestion
```

General exception types should not normally be caught, but sometimes it is appropriate.

```editorconfig
dotnet_diagnostic.CA1032.severity = suggestion
```

Custom exception types do not necessarily need the three standard constructors.

```editorconfig
dotnet_diagnostic.CA1054.severity = none
dotnet_diagnostic.CA1055.severity = none
dotnet_diagnostic.CA1056.severity = none
```

The `Uri` type is a pain.

```editorconfig
dotnet_diagnostic.CA1062.severity = suggestion
```

Consider enabling this if and when it is easier to throw `ArgumentNullException` on null parameters.

```editorconfig
dotnet_diagnostic.CA1063.severity = none
```

The full `Dispose` pattern is rarely needed because finalizers should never be used.

## [Quality: Globalization Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/globalization-warnings)

```editorconfig
dotnet_diagnostic.CA1303.severity = none
```

We don't localize exception messages.

```editorconfig
dotnet_diagnostic.CA1308.severity = suggestion
```

Case normalization is normally done on ASCII, so using lowercase is usually fine.

```editorconfig
dotnet_diagnostic.CA1309.severity = suggestion
```

This rule can trigger even when the string comparison is explicitly set, e.g. to `StringComparison.InvariantCulture`.

## [Quality: Maintainability Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/maintainability-warnings)

```editorconfig
dotnet_diagnostic.CA1508.severity = suggestion
```

Too many false positives for dead conditional code, at least for now.

## [Quality: Naming Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/naming-warnings)

```editorconfig
dotnet_diagnostic.CA1707.severity = none
```

Underscores are frequently used in test method names.

```editorconfig
dotnet_diagnostic.CA1716.severity = none
```

We don't worry about conflicts with Visual Basic keywords.

```editorconfig
dotnet_diagnostic.CA1720.severity = suggestion
```

Using `Float` as a enum value isn't a problem.

## [Quality: Performance Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/performance-warnings)

```editorconfig
dotnet_diagnostic.CA1812.severity = none
```

Types are often created only by reflection.

```editorconfig
dotnet_diagnostic.CA1815.severity = suggestion
```

Only implement efficient equality for value types if it is used.

```editorconfig
dotnet_diagnostic.CA1816.severity = none
```

Don't bother supressing finalization, since finalizers should never be used.

```editorconfig
dotnet_diagnostic.CA1819.severity = suggestion
```

Byte array properties are fine for DTOs, which are common.

```editorconfig
dotnet_diagnostic.CA1822.severity = suggestion
```

Just because a property could be static doesn't mean it should be.

```editorconfig
dotnet_diagnostic.CA1826.severity = suggestion
```

`First`, `Last`, etc. can be more clear than indexers.

```editorconfig
dotnet_diagnostic.CA1848.severity = suggestion
```

The `LoggerMessage` pattern is overkill for most projects.

## [Quality: Reliability Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/reliability-warnings)

```editorconfig
dotnet_diagnostic.CA2000.severity = none
```

Ownership of Disposable objects is frequently transferred.

## [Quality: Security Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/security-warnings)

```editorconfig
dotnet_diagnostic.CA5351.severity = none
```

Trust that older cryptographic algorithms are being used safely.

## [Quality: Usage Rules](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/usage-warnings)

```editorconfig
dotnet_diagnostic.CA2227.severity = none
```

Read-write collection properties are fine for DTOs, which are common.

```editorconfig
dotnet_diagnostic.CA2234.severity = none
```

`System.Uri` isn't always the nicest way to store a URI.

```editorconfig
dotnet_diagnostic.CA2237.severity = none
```

We don't worry about `ISerializable`.

```editorconfig
dotnet_diagnostic.CA2254.severity = none
```

Don't require placeholder logging.

## [ReSharper: Generalized EditorConfig Properties](https://www.jetbrains.com/help/resharper/EditorConfig_Generalized.html)

```editorconfig
resharper_csharp_int_align = false
```

Don't align things.

```editorconfig
resharper_csharp_keep_existing_arrangement = true
resharper_csharp_wrap_lines = false
```

Trust the developer to wrap lines.

```editorconfig
resharper_apply_auto_detected_rules = false
```

We want to enforce our rules, not guess what they are by looking at existing code.

## [ReSharper: Blank Lines](https://www.jetbrains.com/help/resharper/EditorConfig_CSHARP_BlankLinesPageScheme.html)

```editorconfig
resharper_csharp_blank_lines_after_block_statements = 0
```

Don't force a blank line after every block.

## [ReSharper: Code Style](https://www.jetbrains.com/help/resharper/EditorConfig_CSHARP_CSharpCodeStylePageImplSchema.html)

```editorconfig
resharper_csharp_parentheses_group_non_obvious_operations = conditional
resharper_csharp_parentheses_non_obvious_operations = shift, bitwise
resharper_csharp_parentheses_redundancy_style = remove_if_not_clarifies_precedence
```

Use clarifying parentheses with these binary operators: `<<`, `>>`, `&`, `|`, `^`, `&&`, `||`.

```editorconfig
resharper_csharp_trailing_comma_in_multiline_lists = true
resharper_arrange_trailing_comma_in_multiline_lists_highlighting = warning
```

Use trailing commas with multiline lists.

## [ReSharper: Tabs, Indents, Alignment](https://www.jetbrains.com/help/resharper/EditorConfig_CSHARP_CSharpIndentStylePageSchema.html)

```editorconfig
resharper_csharp_indent_nested_for_stmt = true
resharper_csharp_indent_nested_foreach_stmt = true
resharper_csharp_indent_nested_while_stmt = true
```

Don't stack loop statements.

```editorconfig
resharper_csharp_align_multiline_parameter = false
resharper_csharp_align_multiline_extends_list = false
resharper_csharp_align_linq_query = false
resharper_csharp_align_multiline_binary_expressions_chain = false
resharper_csharp_align_multiline_calls_chain = false
resharper_csharp_align_multiline_array_and_object_initializer = false
resharper_csharp_align_multiline_switch_expression = false
resharper_csharp_indent_anonymous_method_block = false
resharper_csharp_align_first_arg_by_paren = false
resharper_csharp_align_multiline_argument = false
resharper_csharp_align_tuple_components = false
resharper_csharp_align_multiline_expression = false
resharper_csharp_align_multiline_for_stmt = false
resharper_csharp_align_multiple_declaration = false
resharper_csharp_align_multline_type_parameter_list = false
resharper_csharp_align_multline_type_parameter_constrains = false
resharper_csharp_align_multiline_statement_conditions = false
```

Don't align things.

## [ReSharper: Line Breaks](https://www.jetbrains.com/help/resharper/EditorConfig_CSHARP_LineBreaksPageSchema.html)

```editorconfig
resharper_csharp_wrap_before_ternary_opsigns = true
resharper_csharp_wrap_ternary_expr_style = wrap_if_long
resharper_csharp_nested_ternary_style = simple_wrap
```

Don't rewrap ternary expressions.

```editorconfig
resharper_csharp_new_line_before_while = true
```

Put the `while` in `do...while` on its own line.

## [ReSharper: Spaces](https://www.jetbrains.com/help/rider/EditorConfig_CSHARP_SpacesPageSchema.html)

```editorconfig
resharper_csharp_space_within_single_line_array_initializer_braces = true
```

## [ReSharper: Formatting](https://www.jetbrains.com/help/resharper/Reference__Code_Inspections_CSHARP.html#FormattingIssues)

```editorconfig
resharper_invert_if_highlighting = none
```

## [ReSharper: Potential Code Quality Issues](https://www.jetbrains.com/help/resharper/Reference__Code_Inspections_CSHARP.html#CodeSmell)

```editorconfig
resharper_access_to_disposed_closure_highlighting = none
resharper_access_to_modified_closure_highlighting = none
```

This happens legitimately too frequently to highlight.

```editorconfig
resharper_is_expression_always_true_highlighting = hint
```

We often use `is object` instead of `!= null`. Consider bumping this to a suggestion when we start using `is not null`.

```editorconfig
resharper_pattern_always_of_type_highlighting = none
```

We often use `is string value` to introduce a new variable while confirming it is not null.

```editorconfig
resharper_compare_of_floats_by_equality_operator_highlighting = suggestion
```

Floating-point equality is too often legitimate for a warning, but a suggestion seems reasonable.

```editorconfig
resharper_localizable_element_highlighting = none
```

We don't localize exception messages.

## [ReSharper: Redundancies in Symbol Declarations](https://www.jetbrains.com/help/resharper/Reference__Code_Inspections_CSHARP.html#DeclarationRedundancy)

```editorconfig
resharper_unused_member_global_highlighting = none
resharper_unused_member_local_highlighting = suggestion
resharper_unused_auto_property_accessor_global_highlighting = none
resharper_unused_auto_property_accessor_local_highlighting = suggestion
```

Members are frequently unused in libraries, unit tests, etc.

## [ReSharper: Spelling Issues](https://www.jetbrains.com/help/resharper/Reference__Code_Inspections_CSHARP.html#Spelling)

```editorconfig
resharper_comment_typo_highlighting = none
resharper_identifier_typo_highlighting = none
resharper_string_literal_typo_highlighting = none
```

## [ReSharper: Syntax Style](https://www.jetbrains.com/help/resharper/Reference__Code_Inspections_CSHARP.html#CodeStyleIssues)

```editorconfig
resharper_arrange_missing_parentheses_highlighting = hint
```

Sometimes it is nice to add clarifying parentheses.

```editorconfig
resharper_arrange_constructor_or_destructor_body_highlighting = hint
resharper_arrange_method_or_operator_body_highlighting = hint
```

Whether a method should use an expression body is subjective.
