---
title: 'Lync Server 2013: risoluzione dei problemi relativi al plug-in di Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7afaa0067e4ca06f8bb40ff201b090a45c66f442
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="e0ec2-102">Risoluzione dei problemi relativi al plug-in di Lync VDI in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0ec2-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0ec2-103">_**Argomento Ultima modifica:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e0ec2-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="e0ec2-104">Risoluzione dei problemi relativi all'installazione del plug-in di Lync VDI in un thin client</span><span class="sxs-lookup"><span data-stu-id="e0ec2-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="e0ec2-105">In caso di problemi con l'installazione del plug-in VDI in un thin client, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e0ec2-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="e0ec2-106">Verificare che nella cartella specificata nelle variabili di sistema TEMP e TMP sia disponibile spazio sufficiente.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="e0ec2-107">Verificare che la protezione da scrittura sia disattivata.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-107">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="e0ec2-108">Per istruzioni, vedere la documentazione del produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-108">Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="e0ec2-109">Risoluzione dei problemi di associazione</span><span class="sxs-lookup"><span data-stu-id="e0ec2-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="e0ec2-110">Quando l'associazione del plug-in VDI non riesce, l'icona di associazione nell'angolo in basso a destra viene visualizzata come "X" rossa, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e0ec2-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="e0ec2-111">![Icona di Lync VDI che mostra l'associazione corretta]di(images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI con l'associazione corretta")</span><span class="sxs-lookup"><span data-stu-id="e0ec2-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="e0ec2-112">Di seguito sono riportate le possibili cause degli errori e le azioni correttive che è possibile eseguire.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="e0ec2-113">**L'utente ha immesso credenziali non corrette durante l'accesso.**</span><span class="sxs-lookup"><span data-stu-id="e0ec2-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="e0ec2-114">L'utente deve disconnettersi da Lync ed eseguire di nuovo l'accesso con le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="e0ec2-115">La finestra di dialogo Associazione verrà ricomparsa e mostrerà se l'associazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="e0ec2-116">**È in corso un'altra istanza del client desktop remoto.**</span><span class="sxs-lookup"><span data-stu-id="e0ec2-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="e0ec2-117">Se si usa la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0ec2-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="e0ec2-118">Avviare Task Manager: premere **ALT + CTRL + CANC**e quindi fare clic su **Avvia Gestione attività**.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="e0ec2-119">Fare clic sulla scheda **processi** e cercare tutti i processi denominati **mstsc. exe** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="e0ec2-120">Evidenziare ogni processo **mstsc. exe** e quindi fare clic su **Termina processo**.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="e0ec2-121">Avviare una nuova sessione di desktop remoto e riprovare a connettersi.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="e0ec2-122">**I file necessari non sono stati installati correttamente.**</span><span class="sxs-lookup"><span data-stu-id="e0ec2-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="e0ec2-123">Dopo aver installato il plug-in nel computer locale, i file seguenti devono essere presenti in C:\\programmi\\Microsoft Office\\Office15 (o la lettera di unità appropriata):</span><span class="sxs-lookup"><span data-stu-id="e0ec2-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="e0ec2-124">LyncVdiPlugin. dll</span><span class="sxs-lookup"><span data-stu-id="e0ec2-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="e0ec2-125">UcVdi. dll</span><span class="sxs-lookup"><span data-stu-id="e0ec2-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="e0ec2-126">In caso di problemi con l'associazione VDI, verificare che questi file siano presenti nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="e0ec2-127">**Il client Lync è in uso nel computer locale.**</span><span class="sxs-lookup"><span data-stu-id="e0ec2-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="e0ec2-128">Per usare il plug-in di Lync VDI, non è necessario che un client Lync sia in esecuzione nel computer locale, altrimenti l'associazione non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="e0ec2-129">Come procedura consigliata, l'utente non deve installare un client Lync nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="e0ec2-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

