---
title: 'Lync Server 2013: creare o modificare una nuova regola di criteri di versione client'
description: 'Lync Server 2013: creare o modificare una nuova regola di criteri di versione client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ebcf17d5cb14fd519fba8ad36be10894fabdb9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574622"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="baf7e-103">Creare o modificare una nuova regola di criteri di versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="baf7e-103">Create or modify a new client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baf7e-104">_**Ultimo argomento modificato:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="baf7e-104">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="baf7e-105">Le regole dei criteri di versione client definiscono le azioni da eseguire quando gli utenti tentano di accedere con client e versioni client specifici.</span><span class="sxs-lookup"><span data-stu-id="baf7e-105">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="baf7e-106">È possibile creare o modificare singole regole per un criterio di versione client dal pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="baf7e-106">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="baf7e-107">Le regole sono elencate in ordine di precedenza.</span><span class="sxs-lookup"><span data-stu-id="baf7e-107">Rules are listed in order of precedence.</span></span> <span data-ttu-id="baf7e-108">Ad esempio, se si dispone di una regola che consente ai client che eseguono la versione 1,5 di connettersi, seguito da una regola che blocca i client che eseguono una versione precedente a 2,0, la prima regola ha la precedenza e i client che eseguono la versione 1,5 sono consentiti per la connessione.</span><span class="sxs-lookup"><span data-stu-id="baf7e-108">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="baf7e-109">Per creare o modificare le regole dei criteri di versione client con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="baf7e-109">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="baf7e-110">[Creare o modificare un nuovo criterio versione client in Lync server 2013 con il](lync-server-2013-create-or-modify-a-new-client-version-policy.md) pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="baf7e-110">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="baf7e-111">Nella pagina **modifica criteri versione client** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="baf7e-111">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="baf7e-112">Fare clic su **nuovo** per creare una nuova regola di versione client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-112">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="baf7e-113">Fare clic su uno dei tipi di client definiti nell'elenco e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-113">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="baf7e-114">È possibile utilizzare i caratteri jolly per indicare il tipo di client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-114">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="baf7e-115">In **agente utente**, selezionare un tipo di client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-115">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="baf7e-116">In **numero di versione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="baf7e-116">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="baf7e-117">Nella **versione principale**Digitare il numero corrispondente alla versione principale del client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-117">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="baf7e-118">In **versione secondaria**Digitare il numero corrispondente alla versione secondaria del client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-118">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="baf7e-119">In **Build**Digitare il numero corrispondente alla versione principale e secondaria del client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-119">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="baf7e-120">In **aggiornamento**Digitare il numero corrispondente alla versione aggiornata del client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-120">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="baf7e-121">È possibile utilizzare i caratteri jolly per indicare il numero di versione client.</span><span class="sxs-lookup"><span data-stu-id="baf7e-121">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="baf7e-122">Per specificare l'operazione corrispondente per la versione client specificata nei passaggi precedenti, in operazione di **confronto**fare clic su una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="baf7e-122">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="baf7e-123">**Corrispondente a**</span><span class="sxs-lookup"><span data-stu-id="baf7e-123">**Same as**</span></span>
    
      - <span data-ttu-id="baf7e-124">**Diverso da**</span><span class="sxs-lookup"><span data-stu-id="baf7e-124">**Is not**</span></span>
    
      - <span data-ttu-id="baf7e-125">**Più recente di**</span><span class="sxs-lookup"><span data-stu-id="baf7e-125">**Newer than**</span></span>
    
      - <span data-ttu-id="baf7e-126">**Più recente di o corrispondente a**</span><span class="sxs-lookup"><span data-stu-id="baf7e-126">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="baf7e-127">**Meno recente di**</span><span class="sxs-lookup"><span data-stu-id="baf7e-127">**Older than**</span></span>
    
      - <span data-ttu-id="baf7e-128">**Meno recente di o corrispondente a**</span><span class="sxs-lookup"><span data-stu-id="baf7e-128">**Older than or same as**</span></span>

6.  <span data-ttu-id="baf7e-129">Per specificare l'azione da eseguire quando vengono soddisfatti i criteri nei passaggi precedenti, fare clic su una delle opzioni seguenti in **azione**:</span><span class="sxs-lookup"><span data-stu-id="baf7e-129">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="baf7e-130">Per consentire al client di eseguire l'accesso, fare clic su **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-130">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="baf7e-131">Per consentire al client di eseguire l'accesso e ricevere aggiornamenti da Windows Server Update Service o Microsoft Update, fare clic su **Consenti e aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-131">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="baf7e-132">Questa azione è disponibile solo se si seleziona l'agente utente **OC**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-132">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="baf7e-133">Se si seleziona questa azione, viene visualizzata una notifica al successivo accesso degli utenti a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="baf7e-133">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="baf7e-134">La notifica indica che è disponibile un aggiornamento, anche se non sono stati ancora rilasciati aggiornamenti per Windows Server Update Service o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="baf7e-134">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="baf7e-135">Per evitare confusione, è consigliabile scegliere questa azione solo quando vengono resi disponibili gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="baf7e-135">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="baf7e-136">Per consentire al client di accedere e visualizzare un messaggio su dove scaricare un'altra versione client, fare clic su **Consenti con URL**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-136">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="baf7e-137">Specificare l'URL più avanti in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="baf7e-137">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="baf7e-138">Per impedire l'accesso del client, fare clic su **blocca**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-138">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="baf7e-139">Per impedire al client di eseguire l'accesso e consentire al client di ricevere aggiornamenti da Windows Server Update Service o Microsoft Update, fare clic su **blocca e aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-139">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="baf7e-140">Questa azione è disponibile solo se si seleziona l'agente utente **OC**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-140">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="baf7e-141">Per impedire al client di eseguire l'accesso e visualizzare un messaggio su dove scaricare un'altra versione client, fare clic su **blocca con URL**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-141">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="baf7e-142">Specificare l'URL più avanti in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="baf7e-142">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="baf7e-143">Optional Se si è fatto clic su **Consenti con URL** o **blocca con URL** nel passaggio precedente, digitare l'URL di download del client da includere nel messaggio in **URL**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-143">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="baf7e-144">Fare clic su **OK**, quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="baf7e-144">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

