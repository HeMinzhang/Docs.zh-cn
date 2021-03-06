---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065125"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a>CA1417:P/Invoke 的字符串参数上的 OutAttribute

从 .NET 5.0 开始，默认启用 .NET 代码分析器规则 [CA1417](/visualstudio/code-quality/ca1417)。 它会为任何[平台调用 (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) 方法定义生成一个生成警告，该定义中 <xref:System.String> 参数按值传递并使用 <xref:System.Runtime.InteropServices.OutAttribute> 进行标记。

#### <a name="change-description"></a>更改说明

从 .NET 5.0 开始，.NET SDK 包括 [.NET 源代码分析器](../../../../docs/fundamentals/productivity/code-analysis.md)。 其中一些规则会默认启用，包括 [CA1417](/visualstudio/code-quality/ca1417)。 如果项目包含违反此规则的代码，并已被配置为将警告视为错误，则此更改可能会中断生成。

规则 CA1417 标记 [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) 方法定义，其中 <xref:System.String> 参数用 <xref:System.Runtime.InteropServices.OutAttribute> 属性进行标记并按值传递。 例如：

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

.NET 运行时维护称为内部池的表，该表包含对程序中每个唯一文本字符串的单一引用。 如果将使用 <xref:System.Runtime.InteropServices.OutAttribute> 标记的限定字符串按值传递给 P/Invoke 方法，则运行时可能会不稳定。 有关字符串限定的详细信息，请参阅 <xref:System.String.Intern(System.String)?displayProperty=nameWithType> 的备注。

#### <a name="version-introduced"></a>引入的版本

5.0 预览版 8

#### <a name="recommended-action"></a>建议操作

- 如果需要将修改后的字符串数据封送回调用方，请改为按引用传递字符串。

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- 如果不需要将修改后的字符串数据封送回调用方，只需删除 <xref:System.Runtime.InteropServices.OutAttribute>。

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  有关详细信息，请参阅 [CA1417](/visualstudio/code-quality/ca1417)。

- 若要完全禁用代码分析，请在项目文件中将 `EnableNETAnalyzers` 设置为 `false`。 有关详细信息，请参阅 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)。

#### <a name="category"></a>类别

代码分析

#### <a name="affected-apis"></a>受影响的 API

无法通过 API 分析检测到。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
