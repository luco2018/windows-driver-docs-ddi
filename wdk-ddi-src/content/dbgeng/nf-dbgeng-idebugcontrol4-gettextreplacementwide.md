---
UID: NF:dbgeng.IDebugControl4.GetTextReplacementWide
title: IDebugControl4::GetTextReplacementWide
author: windows-driver-content
description: The GetTextReplacementWide method returns the value of a user-named alias or an automatic alias.
old-location: debugger\gettextreplacementwide.htm
old-project: debugger
ms.assetid: 39a609f3-8f79-4a8b-9d29-0cfe09070f2b
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetTextReplacementWide, GetTextReplacementWide method [Windows Debugging], GetTextReplacementWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetTextReplacementWide method, IDebugControl4.GetTextReplacementWide, IDebugControl4::GetTextReplacementWide, dbgeng/IDebugControl4::GetTextReplacementWide, debugger.gettextreplacementwide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.GetTextReplacementWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetTextReplacementWide


## -description


The <b>GetTextReplacementWide</b>  method returns the value of a user-named alias or an automatic alias.  


## -parameters




### -param SrcText [in, optional]

Specifies the name of the alias.  The engine first searches the user-named aliases for one with this name. Then, if no match is found, the automatic aliases are searched.  If <i>SrcText</i> is <b>NULL</b>, <i>Index</i> is used to specify the alias.


### -param Index [in]

Specifies the index of an alias.  The indexes of the user-named aliases come before the indexes of the automatic aliases.  <i>Index</i> is only used if <i>SrcText</i> is <b>NULL</b>.  <i>Index</i> can be used along with <a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a> to iterate over all the user-named and automatic aliases.


### -param SrcBuffer [out, optional]

Receives the name of the alias.  This is the name specified in <i>SrcText</i>, if <i>SrcText</i> is not <b>NULL</b>.  If <i>SrcBuffer</i> is <b>NULL</b>, this information is not returned.


### -param SrcBufferSize [in]

Specifies the size, in characters, of the <i>SrcBuffer</i> buffer.


### -param SrcSize [out, optional]

Receives the size, in characters, of the name of the alias.  If <i>SrcSize</i> is <b>NULL</b>, this information is not returned.


### -param DstBuffer [out, optional]

Receives the value of the alias specified by <i>SrcText</i> and <i>Index</i>.  If <i>DstBuffer</i> is <b>NULL</b>, this information is not returned.


### -param DstBufferSize [in]

Specifies the size, in characters, of the <i>DstBuffer</i> buffer.


### -param DstSize [out, optional]

Receives the size, in characters, of the value of the alias.  If <i>DstSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>SrcBuffer</i> with the value of the alias (specified by <i>DstBuffer</i>).

For an overview of aliases used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549270">GetTextMacro</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538014">al (List Aliases)</a>
 

 

