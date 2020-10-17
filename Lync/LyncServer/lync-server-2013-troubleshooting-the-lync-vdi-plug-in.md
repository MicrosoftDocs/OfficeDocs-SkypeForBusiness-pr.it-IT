---
title: 'Lync Server 2013: risoluzione dei problemi relativi al plug-in VDI di Lync'
description: 'Lync Server 2013: risoluzione dei problemi relativi al plug-in VDI di Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd2c0e3c8a47225f00ce280706dea2287e4dc8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548942"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="157f5-103">Risoluzione dei problemi relativi al plug-in VDI di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="157f5-103">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="157f5-104">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="157f5-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="157f5-105">Risoluzione dei problemi relativi all'installazione del plug-in VDI di Lync in un thin client</span><span class="sxs-lookup"><span data-stu-id="157f5-105">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="157f5-106">In caso di problemi durante l'installazione del plug-in VDI in un thin client, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="157f5-106">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="157f5-107">Verificare che nella cartella specificata vi sia sufficiente spazio per le variabili di sistema TEMP e TMP.</span><span class="sxs-lookup"><span data-stu-id="157f5-107">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="157f5-p101">Verificare che la protezione dalla scrittura sia disattivata. Per istruzioni, consultare la documentazione del produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="157f5-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="157f5-110">Risoluzione dei problemi di abbinamento</span><span class="sxs-lookup"><span data-stu-id="157f5-110">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="157f5-111">Quando l'abbinamento del plug-in VDI non riesce, nell'icona in basso a destra viene visualizzata una "X" rossa come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="157f5-111">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="157f5-112">![Icona di Lync VDI che mostra un accoppiamento corretto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icona di Lync VDI che mostra un accoppiamento corretto")</span><span class="sxs-lookup"><span data-stu-id="157f5-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="157f5-113">Di seguito vengono elencate le possibili cause degli errori e le azioni correttive che è possibile intraprendere.</span><span class="sxs-lookup"><span data-stu-id="157f5-113">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="157f5-114">**Sono state inserite credenziali non corrette durante l'accesso.**</span><span class="sxs-lookup"><span data-stu-id="157f5-114">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="157f5-115">L'utente deve disconnettersi da Lync ed eseguire nuovamente l'accesso con le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="157f5-115">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="157f5-116">Verrà visualizzata di nuovo la finestra di dialogo di abbinamento che segnalerà se l'abbinamento è andato a buon fine.</span><span class="sxs-lookup"><span data-stu-id="157f5-116">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="157f5-117">**È in esecuzione un'altra istanza del client desktop remoto.**</span><span class="sxs-lookup"><span data-stu-id="157f5-117">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="157f5-118">Se si utilizza la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="157f5-118">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="157f5-119">Avviare Gestione attività: premere **Alt+Ctrl+Canc** e quindi fare clic su **Avvia Gestione attività**.</span><span class="sxs-lookup"><span data-stu-id="157f5-119">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="157f5-120">Fare clic sulla scheda **Processi** e cercare tutti i processi denominati **mstsc.exe** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="157f5-120">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="157f5-121">Selezionare ogni processo **mstsc.exe** e fare clic su **Termina processo**.</span><span class="sxs-lookup"><span data-stu-id="157f5-121">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="157f5-122">Avviare una nuova sessione di desktop remoto e riprovare a connettersi.</span><span class="sxs-lookup"><span data-stu-id="157f5-122">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="157f5-123">**I file necessari non sono installati correttamente.**</span><span class="sxs-lookup"><span data-stu-id="157f5-123">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="157f5-124">Dopo aver installato il plug-in nel computer locale, è necessario che i file seguenti siano presenti in C: \\ Program Files \\ Microsoft Office \\ Office15 (o la lettera di unità appropriata):</span><span class="sxs-lookup"><span data-stu-id="157f5-124">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="157f5-125">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="157f5-125">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="157f5-126">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="157f5-126">UcVdi.dll</span></span>
    
    <span data-ttu-id="157f5-127">In caso di problemi di abbinamento VDI, controllare che questi file siano presenti nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="157f5-127">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="157f5-128">**Il client Lync è in esecuzione nel computer locale.**</span><span class="sxs-lookup"><span data-stu-id="157f5-128">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="157f5-129">Per utilizzare il plug-in di Lync VDI, non è necessario che un client Lync sia in esecuzione nel computer locale, altrimenti l'accoppiamento avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="157f5-129">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="157f5-130">Come procedura consigliata, l'utente non deve installare un client Lync nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="157f5-130">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

