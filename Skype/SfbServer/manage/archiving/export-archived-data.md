---
title: Esportare i dati archiviati in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Riepilogo: informazioni su come esportare i dati archiviati per Skype for Business Server.'
ms.openlocfilehash: 00960625baaeacc74d0e802c7037e2ad3ca24671
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632900"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Esportare i dati archiviati in Skype for Business Server

**Riepilogo:** Informazioni su come esportare i dati archiviati per Skype for Business Server.
  
I dati archiviati nei database di archiviazione non sono disponibili per la ricerca o in un formato leggibile, ma è possibile utilizzare il cmdlet **Export-CsArchivingData** per estrarre i record dal database e salvarli come file EML (Outlook Electronic Mail).
  
Se si abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati in Exchange archiviati. I dati archiviati in Exchange sono ricercabili e individuabili. Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la Exchange documentazione.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Esportazione dei dati di archiviazione tramite Windows PowerShell cmdlet

È possibile esportare i dati archiviati utilizzando il cmdlet Export-CSArchivingData. 
  
Il comando seguente esporta tutti i dati di archiviazione scritti nel database di archiviazione atl-sql-001.contoso.com dal 1° giugno 2012. Il file di output risultante verrà archiviato nella cartella C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Il comando seguente esporta i dati di archiviazione per un singolo utente: kenmyer@contoso.com. A tale scopo, viene incluso il parametro UserUri seguito dall'indirizzo SIP dell'utente. Ad esempio: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Export-CsArchivingData.](/powershell/module/skype/export-csarchivingdata?view=skype-ps)
