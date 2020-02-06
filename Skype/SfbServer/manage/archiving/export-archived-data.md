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
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="5399a-103">Esportare dati archiviati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5399a-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="5399a-104">**Riepilogo:** Informazioni su come esportare i dati archiviati per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5399a-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="5399a-105">I dati archiviati nei database di archiviazione non sono ricercabili o in formato leggibile, ma è possibile usare il cmdlet **Export-CsArchivingData** per estrarre i record dal database e salvarli come file di posta elettronica di Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="5399a-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="5399a-106">Se si Abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati negli archivi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="5399a-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="5399a-107">I dati archiviati in Exchange sono ricercabili ed individuabili.</span><span class="sxs-lookup"><span data-stu-id="5399a-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="5399a-108">Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la documentazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="5399a-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5399a-109">Esportazione dei dati di archiviazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5399a-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5399a-110">È possibile esportare i dati archiviati usando il cmdlet Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="5399a-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="5399a-111">Il comando seguente Esporta tutti i dati di archiviazione scritti nel database di archiviazione atl-sql-001.contoso.com dal 1 ° giugno 2012.</span><span class="sxs-lookup"><span data-stu-id="5399a-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="5399a-112">Il file di output risultante verrà archiviato nella cartella C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="5399a-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="5399a-113">Il comando seguente esporta i dati di archiviazione per un singolo utente: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5399a-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="5399a-114">Questa operazione viene eseguita includendo il parametro UserUri seguito dall'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5399a-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="5399a-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5399a-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="5399a-116">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5399a-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

