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
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Riepilogo: informazioni su come esportare i dati archiviati per Skype for Business Server.'
ms.openlocfilehash: e69c283304395d697e99ef0607e2aec1eb7960e4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095380"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Esportare i dati archiviati in Skype for Business Server

**Riepilogo:** Informazioni su come esportare i dati archiviati per Skype for Business Server.
  
I dati archiviati nei database di archiviazione non sono disponibili per la ricerca o in un formato leggibile, ma è possibile utilizzare il cmdlet **Export-CsArchivingData** per estrarre i record dal database e salvarli come file EML (Outlook Electronic Mail).
  
Se si abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati negli archivi di Exchange. I dati archiviati in Exchange sono ricercabili e individuabili. Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la documentazione di Exchange.
  
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
