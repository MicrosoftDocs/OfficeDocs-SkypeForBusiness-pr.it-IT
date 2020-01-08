---
title: 'Lync Server 2013: Creare o modificare un numero di accesso per una conferenza telefonica con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="a14a3-102">Creare o modificare un numero di accesso per una conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14a3-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a14a3-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a14a3-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a14a3-104">Seguire questa procedura se si vuole creare o modificare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a14a3-105">Prima di creare un nuovo numero di accesso per la chiamata in ingresso, è necessario impostare un'area di conferenza telefonica con accesso esterno nel dial plan associato al nuovo numero di Access per la chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="a14a3-106">Più piani di chiamata possono usare la stessa area geografica.</span><span class="sxs-lookup"><span data-stu-id="a14a3-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="a14a3-107">Per creare o modificare un numero di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="a14a3-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="a14a3-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a14a3-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a14a3-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a14a3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a14a3-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a14a3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a14a3-111">Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno** .</span><span class="sxs-lookup"><span data-stu-id="a14a3-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="a14a3-112">Nella pagina **numero di accesso** esterno effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a14a3-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a14a3-113">Fare clic su **nuovo** per aprire il **nuovo numero di accesso**esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="a14a3-114">Fare clic su uno dei numeri di accesso per la chiamata in ingresso nell'elenco, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a14a3-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a14a3-115">L'uso del campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso per la chiamata in ingresso potrebbe non restituire i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="a14a3-115">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="a14a3-116">Ordinare invece l'elenco in base alla colonna di interesse per identificare il numero di accesso esterno che si vuole visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="a14a3-116">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="a14a3-117">In **numero di visualizzazione**Digitare il numero di telefono che gli utenti del telefono PSTN (Public Switched Telephone Network) Dial per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a14a3-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a14a3-118">Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="a14a3-119">In **nome visualizzato**Digitare una descrizione per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="a14a3-120">Questo è il nome associato al numero di accesso esterno nei risultati della ricerca in Lync.</span><span class="sxs-lookup"><span data-stu-id="a14a3-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a14a3-121">Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="a14a3-122">In **URI di linea**Digitare il numero e. 164 del numero di accesso esterno in formato Tel URI, incluso il simbolo + prima del numero ed escludendo gli spazi.</span><span class="sxs-lookup"><span data-stu-id="a14a3-122">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="a14a3-123">Ad esempio, Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="a14a3-123">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a14a3-124">Lo stesso URI di linea non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="a14a3-125">In **URI SIP**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a14a3-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="a14a3-126">Nella casella di testo digitare un URI SIP univoco per questo numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="a14a3-127">Questo URI SIP viene visualizzato in varie posizioni, inclusi, ma non solo, i messaggi di notifica delle chiamate e le versioni precedenti dei client Communicator.</span><span class="sxs-lookup"><span data-stu-id="a14a3-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a14a3-128">Lo stesso URI SIP non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-128">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="a14a3-129">L'URI SIP non può essere modificato dopo la creazione del numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-129">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="a14a3-130">L'unico modo per modificare l'URI SIP consiste nell'eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-130">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="a14a3-131">Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione operatore di conferenza che supporta questo numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="a14a3-132">In **pool**fare clic sul pool in cui è in esecuzione l'istanza di operatore conferenza che supporta questo numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a14a3-133">Se è necessario modificare il pool dopo la creazione del numero di accesso, è necessario usare il cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> oppure eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="a14a3-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="a14a3-134">In **lingua principale**fare clic sulla lingua in cui vengono riprodotti le richieste per questo numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a14a3-135">La lingua principale è la lingua che l'operatore di conferenza USA per rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a14a3-135">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="a14a3-136">Le lingue supportate vengono visualizzate accanto a ogni numero di telefono di Access nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-136">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="a14a3-137">Opzionale In **lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti per il numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a14a3-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a14a3-138">È possibile scegliere fino a quattro lingue secondarie per ogni numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a14a3-138">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="a14a3-139">Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando effettuano la chiamata a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a14a3-139">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="a14a3-140">Per aggiungere un'area geografica per il numero di accesso esterno, fare clic su **Aggiungi**in **aree geografiche associate**, fare clic su una o più aree geografiche associate ai dial plan per questo numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a14a3-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="a14a3-141">Per eliminare un'area dal numero di accesso esterno, in **aree geografiche associate**fare clic sull'area che si vuole eliminare e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="a14a3-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="a14a3-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a14a3-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

