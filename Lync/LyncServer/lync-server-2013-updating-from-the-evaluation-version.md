---
title: 'Lync Server 2013: aggiornamento dalla versione di valutazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787aa9f1983dc755f1ce9b35ff66320be1d5dba5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="c7dbb-102">Aggiornamento dalla versione di valutazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7dbb-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7dbb-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="c7dbb-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="c7dbb-104">Se è stata installata la versione di valutazione di Microsoft Lync Server 2013, sarà necessario aggiornare l'installazione di una copia con licenza del software. Ciò è dovuto al fatto che la versione di valutazione scade 180 giorni dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="c7dbb-105">Non sarà tuttavia necessario disinstallare completamente la versione di valutazione e quindi installare la versione con licenza.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="c7dbb-106">Al contrario, dopo aver ottenuto un codice di licenza valido, è possibile aggiornare la versione di valutazione di Lync Server 2013 eseguendo la procedura seguente in ogni computer che funge da server front-end di Lync Server, Director o server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="c7dbb-107">Si noti che non è necessario aggiornare i computer che svolgono altri ruoli del server, ad esempio Monitoring Server o server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="c7dbb-108">Aggiornamento dalla versione di valutazione di Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7dbb-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="c7dbb-109">Per aggiornare un computer dalla versione di valutazione di Lync Server 2013 alla versione con licenza del software:</span><span class="sxs-lookup"><span data-stu-id="c7dbb-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="c7dbb-110">**Aggiornamento dalla versione di valutazione di Microsoft Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="c7dbb-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="c7dbb-111">Accedere al computer come amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="c7dbb-112">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c7dbb-113">In Lync Server Management Shell, digitare il comando seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="c7dbb-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="c7dbb-114">Si noti che potrebbe essere necessario specificare il percorso completo del file server.msi.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="c7dbb-115">Questo file può essere trovato nella cartella Setup dei file di installazione del volume multimediale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="c7dbb-116">Al termine dell'esecuzione del programma di installazione, digitare il comando seguente al prompt dei comandi e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="c7dbb-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="c7dbb-117">Ripetere questa procedura in qualsiasi altro server front-end, Director o server perimetrale che esegua una copia di valutazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="c7dbb-118">Questa procedura deve essere eseguita anche su tutti i server di succursale distribuiti mediante i file di installazione dei supporti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="c7dbb-119">Se non si è certi che la versione di valutazione di Lync Server sia in esecuzione in un determinato computer, è possibile verificare che eseguendo il comando seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c7dbb-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="c7dbb-120">Il cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analizzerà il computer locale e fornirà una delle indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7dbb-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="c7dbb-121">Che il codice di licenza del volume di Lync Server è stato installato nel computer, il che significa che non è necessario alcun aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="c7dbb-122">Che è stato installato il codice di licenza di valutazione di Lync Server, il che significa che il computer deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="c7dbb-p104">Non è necessario alcun codice di contratto multilicenza nel computer. L'aggiornamento dalla versione di valutazione a quella con licenza è necessaria solo nei Front End Server, nei server Director e nei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="c7dbb-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

