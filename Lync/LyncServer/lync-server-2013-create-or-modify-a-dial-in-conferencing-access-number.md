---
title: 'Lync Server 2013: creare o modificare un numero di accesso per le conferenze telefoniche con chiamata in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2793a37fcac58afdf3e996094bcb8d2ff8f5a2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="16994-102">Creare o modificare un numero di accesso per le conferenze telefoniche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16994-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16994-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="16994-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="16994-104">Eseguire questa procedura se si desidera creare o modificare un numero di accesso per partecipare a una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="16994-p101">Prima di creare un nuovo numero di accesso esterno, è necessario impostare per tale numero un'area di conferenza telefonica con accesso esterno associata al dial plan. Più dial plan possono utilizzare la stessa area.</span><span class="sxs-lookup"><span data-stu-id="16994-p101">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number. Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="16994-107">Per creare o modificare un numero di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="16994-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="16994-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="16994-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16994-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16994-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="16994-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="16994-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="16994-111">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="16994-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="16994-112">Nella pagina **Numero di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16994-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="16994-113">Fare clic su **Nuovo** per aprire **Nuovo numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="16994-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="16994-114">Fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="16994-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="16994-p103">Se si utilizza il campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso esterno, i risultati ottenuti potrebbero non essere quelli previsti. Ordinare invece l'elenco in base alla colonna a cui si è interessati per identificare il numero di accesso esterno da visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="16994-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="16994-117">In **Numero visualizzato** digitare il numero di telefono che gli utenti della rete PSTN (Public Switched Telephone Network) devono comporre per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="16994-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16994-118">Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="16994-119">In **Nome visualizzato** digitare una descrizione per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="16994-120">Si tratta del nome associato al numero di accesso esterno nei risultati della ricerca di Lync.</span><span class="sxs-lookup"><span data-stu-id="16994-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16994-121">Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="16994-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="16994-p105">In **URI linea** digitare il numero E.164 del numero di accesso esterno nel formato URI TEL, preceduto dal simbolo + e senza utilizzare spazi. Ad esempio, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="16994-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16994-124">Non è possibile riutilizzare lo stesso URI linea per un altro numero di accesso per conferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="16994-125">In **URI SIP** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16994-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="16994-126">Nella casella di testo digitare un URI SIP univoco per il numero di accesso per conferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="16994-127">Questo URI SIP viene visualizzato in diverse posizioni, tra cui, ma non solo, i messaggi di notifica di chiamata e le versioni precedenti dei client Communicator.</span><span class="sxs-lookup"><span data-stu-id="16994-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="16994-p107">Non è possibile riutilizzare lo stesso URI SIP per un altro numero di accesso per conferenze con accesso esterno. L'URI SIP non può essere modificato dopo che il numero di accesso è stato creato. L'unico modo per modificare l'URI SIP è quello di eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="16994-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="16994-131">Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione Operatore Conferenza che supporta il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="16994-132">In **Pool** fare clic sul pool che esegue l'istanza di Operatore Conferenza che supporta il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16994-133">Se è necessario modificare il pool dopo avere creato il numero di accesso, utilizzare il cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> oppure eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="16994-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="16994-134">In **Lingua principale** fare clic sulla lingua in cui verranno riprodotte le richieste per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16994-p108">La lingua principale è la lingua utilizzata da Operatore Conferenza per rispondere alla chiamata. Le lingue supportate vengono visualizzate insieme a ogni numero di telefono di accesso nella pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16994-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="16994-137">(Facoltativo) In **Lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti al numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="16994-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16994-p109">È possibile selezionare fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando chiamano per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="16994-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="16994-140">Per aggiungere un'area per il numero di accesso esterno, in **aree associate**fare clic su **Aggiungi**, fare clic su una o più aree associate ai dial plan per il numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="16994-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="16994-141">Per eliminare un'area dal numero di accesso esterno, in **Aree associate** fare clic sull'area desiderata e quindi su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="16994-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="16994-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="16994-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

