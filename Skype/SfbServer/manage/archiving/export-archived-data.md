---
title: Esportare dati archiviati in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Riepilogo: informazioni su come esportare i dati archiviati per Skype for Business Server.'
ms.openlocfilehash: 6914b4c32c22165b551bb56ece8d7b3b9c21fdbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190361"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Esportare dati archiviati in Skype for Business Server

**Riepilogo:** Informazioni su come esportare i dati archiviati per Skype for Business Server.
  
I dati archiviati nei database di archiviazione non sono ricercabili o in formato leggibile, ma è possibile usare il cmdlet **Export-CsArchivingData** per estrarre i record dal database e salvarli come file di posta elettronica di Outlook (EML).
  
Se si Abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati negli archivi di Exchange. I dati archiviati in Exchange sono ricercabili ed individuabili. Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la documentazione di Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Esportazione dei dati di archiviazione tramite i cmdlet di Windows PowerShell

È possibile esportare i dati archiviati usando il cmdlet Export-CSArchivingData. 
  
Il comando seguente Esporta tutti i dati di archiviazione scritti nel database di archiviazione atl-sql-001.contoso.com dal 1 ° giugno 2012. Il file di output risultante verrà archiviato nella cartella C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Il comando seguente esporta i dati di archiviazione per un singolo utente: kenmyer@contoso.com. Questa operazione viene eseguita includendo il parametro UserUri seguito dall'indirizzo SIP dell'utente. Ad esempio: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

