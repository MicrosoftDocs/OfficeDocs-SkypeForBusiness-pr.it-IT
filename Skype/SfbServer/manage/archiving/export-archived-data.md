---
title: Esportare dati archiviati in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Riepilogo: informazioni su come esportare i dati archiviati per Skype for Business Server.'
ms.openlocfilehash: 12ba59ff11a988fd95eb2207cd826a4399db2779
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818908"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Esportare dati archiviati in Skype for Business Server

**Riepilogo:** Informazioni su come esportare i dati archiviati per Skype for Business Server.
  
I dati archiviati nei database di archiviazione non sono ricercabili o in formato leggibile, ma è possibile usare il cmdlet **Export-CsArchivingData** per estrarre i record dal database e salvarli come file di posta elettronica di Outlook (EML).
  
Se si Abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati negli archivi di Exchange. I dati archiviati in Exchange sono ricercabili ed individuabili. Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la documentazione di Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Esportazione dei dati di archiviazione tramite i cmdlet di Windows PowerShell

È possibile esportare i dati archiviati usando il cmdlet Export-CSArchivingData. 
  
Il comando seguente Esporta tutti i dati di archiviazione scritti nel database di archiviazione atl-sql-001.contoso.com dal 1 ° giugno 2012. Il file di output risultante verrà archiviato nella cartella C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Il comando seguente esporta i dati di archiviazione per un singolo utente: kenmyer@contoso.com. Questa operazione viene eseguita includendo il parametro UserUri seguito dall'indirizzo SIP dell'utente. Ad esempio: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

