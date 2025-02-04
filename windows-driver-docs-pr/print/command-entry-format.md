---
title: Command Entry Format
description: Command Entry Format
keywords:
- printer commands WDK Unidrv , entry format
- formats WDK printer commands
ms.date: 01/26/2023
---

# Command Entry Format

[!include[Print Support Apps](../includes/print-support-apps.md)]

To specify a printer command entry in a GPD file, use the following format:

<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>*Command</strong>: <em>CommandName</em> {<em>CommandAttributes</em>}</p></td>
</tr>
</tbody>
</table>

where *CommandName* is one of the predefined [command names](command-names.md), and *CommandAttributes* is a set of [command attributes](command-attributes.md).

For example, a GPD file might contain the following specification of the CmdStartPage command, which initializes a page for printing.

```cpp
*Command: CmdStartPage
{
    *Order: PAGE_SETUP.100
    *Cmd: "<0D>"
}
```

If, for a particular *CommandName* value, you only need to specify the \*Cmd attribute, you can use a shortened version of the command entry format, as follows:

<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>*Command</strong>: <em>CommandName</em>: <em>CommandString</em></p></td>
</tr>
</tbody>
</table>

where *CommandString* is a text string representing a printer command escape sequence. For more information about specifying escape sequences, see [Command String Format](command-string-format.md).

For example, a GPD file might contain the following specification of the CmdBoldOn command, which turns on bold text:

```cpp
*Command: CmdBoldOn: "<1B>(s3B"
```
