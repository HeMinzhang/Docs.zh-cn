---
title: UriTemplate 示例
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: fb956882ae653f584026fefb20e261c90010ca9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591054"
---
# <a name="uritemplate-sample"></a>UriTemplate 示例
<xref:System.UriTemplate> 类提供了用于处理共享公共结构的 URI 组的方法。 此示例演示与 `UriTemplate` 相关的以下关键概念：  
  
- 创建模板的语法。  
  
- 使用 `UriTemplate` 和 <xref:System.UriTemplate.BindByName%2A> 实例化 <xref:System.UriTemplate.BindByPosition%2A> 中的 URI。  
  
- 作为 <xref:System.UriTemplateTable.Match%2A> 和 `BindByName` 的反向操作的 `BindByPosition`。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](building-the-samples.md)中的说明进行操作。  
  
2. 若要以单机配置或跨计算机配置来运行示例，请按照[运行 Windows Communication Foundation 示例](running-the-samples.md)中的说明进行操作。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a>另请参阅

- [UriTemplate 表](uritemplate-table-sample.md)
- [UriTemplate 表调度程序](uritemplate-table-dispatcher-sample.md)
