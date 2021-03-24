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
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="a6397-103">Esportare i dati archiviati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a6397-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="a6397-104">**Riepilogo:** Informazioni su come esportare i dati archiviati per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a6397-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="a6397-105">I dati archiviati nei database di archiviazione non sono disponibili per la ricerca o in un formato leggibile, ma è possibile utilizzare il cmdlet **Export-CsArchivingData** per estrarre i record dal database e salvarli come file EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="a6397-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="a6397-106">Se si abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati negli archivi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6397-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="a6397-107">I dati archiviati in Exchange sono ricercabili e individuabili.</span><span class="sxs-lookup"><span data-stu-id="a6397-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="a6397-108">Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la documentazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6397-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a6397-109">Esportazione dei dati di archiviazione tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="a6397-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a6397-110">È possibile esportare i dati archiviati utilizzando il cmdlet Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="a6397-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="a6397-111">Il comando seguente esporta tutti i dati di archiviazione scritti nel database di archiviazione atl-sql-001.contoso.com dal 1° giugno 2012.</span><span class="sxs-lookup"><span data-stu-id="a6397-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="a6397-112">Il file di output risultante verrà archiviato nella cartella C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="a6397-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="a6397-113">Il comando seguente esporta i dati di archiviazione per un singolo utente: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a6397-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="a6397-114">A tale scopo, viene incluso il parametro UserUri seguito dall'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a6397-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="a6397-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6397-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="a6397-116">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Export-CsArchivingData.](/powershell/module/skype/export-csarchivingdata?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a6397-116">For more information, see the help topic for the [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
