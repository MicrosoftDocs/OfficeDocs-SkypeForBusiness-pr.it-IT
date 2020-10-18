---
title: 'Lync Server 2013: creare o modificare un numero di accesso per le conferenze telefoniche con chiamata in ingresso'
description: 'Lync Server 2013: creare o modificare un numero di accesso per le conferenze telefoniche con chiamata in ingresso.'
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
ms.openlocfilehash: 187361ab839fe2f80fda7cb68285c8f36398f5a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577962"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="b6fc9-103">Creare o modificare un numero di accesso per le conferenze telefoniche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6fc9-103">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6fc9-104">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="b6fc9-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="b6fc9-105">Eseguire questa procedura se si desidera creare o modificare un numero di accesso per partecipare a una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-105">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b6fc9-p101">Prima di creare un nuovo numero di accesso esterno, è necessario impostare per tale numero un'area di conferenza telefonica con accesso esterno associata al dial plan. Più dial plan possono utilizzare la stessa area.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-p101">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number. Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="b6fc9-108">Per creare o modificare un numero di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="b6fc9-108">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="b6fc9-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b6fc9-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b6fc9-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b6fc9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b6fc9-112">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-112">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="b6fc9-113">Nella pagina **Numero di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6fc9-113">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b6fc9-114">Fare clic su **Nuovo** per aprire **Nuovo numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-114">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="b6fc9-115">Fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-115">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b6fc9-p103">Se si utilizza il campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso esterno, i risultati ottenuti potrebbero non essere quelli previsti. Ordinare invece l'elenco in base alla colonna a cui si è interessati per identificare il numero di accesso esterno da visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="b6fc9-118">In **Numero visualizzato** digitare il numero di telefono che gli utenti della rete PSTN (Public Switched Telephone Network) devono comporre per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-118">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6fc9-119">Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-119">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="b6fc9-120">In **Nome visualizzato** digitare una descrizione per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-120">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="b6fc9-121">Si tratta del nome associato al numero di accesso esterno nei risultati della ricerca di Lync.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-121">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6fc9-122">Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-122">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="b6fc9-p105">In **URI linea** digitare il numero E.164 del numero di accesso esterno nel formato URI TEL, preceduto dal simbolo + e senza utilizzare spazi. Ad esempio, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6fc9-125">Non è possibile riutilizzare lo stesso URI linea per un altro numero di accesso per conferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-125">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="b6fc9-126">In **URI SIP** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6fc9-126">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="b6fc9-127">Nella casella di testo digitare un URI SIP univoco per il numero di accesso per conferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-127">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="b6fc9-128">Questo URI SIP viene visualizzato in diverse posizioni, tra cui, ma non solo, i messaggi di notifica di chiamata e le versioni precedenti dei client Communicator.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-128">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b6fc9-p107">Non è possibile riutilizzare lo stesso URI SIP per un altro numero di accesso per conferenze con accesso esterno. L'URI SIP non può essere modificato dopo che il numero di accesso è stato creato. L'unico modo per modificare l'URI SIP è quello di eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="b6fc9-132">Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione Operatore Conferenza che supporta il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-132">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="b6fc9-133">In **Pool** fare clic sul pool che esegue l'istanza di Operatore Conferenza che supporta il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-133">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6fc9-134">Se è necessario modificare il pool dopo avere creato il numero di accesso, utilizzare il cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> oppure eliminare e ricreare il numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-134">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="b6fc9-135">In **Lingua principale** fare clic sulla lingua in cui verranno riprodotte le richieste per il numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-135">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6fc9-p108">La lingua principale è la lingua utilizzata da Operatore Conferenza per rispondere alla chiamata. Le lingue supportate vengono visualizzate insieme a ogni numero di telefono di accesso nella pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="b6fc9-138">(Facoltativo) In **Lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti al numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-138">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6fc9-p109">È possibile selezionare fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando chiamano per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="b6fc9-141">Per aggiungere un'area per il numero di accesso esterno, in **aree associate**fare clic su **Aggiungi**, fare clic su una o più aree associate ai dial plan per il numero di accesso esterno e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-141">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="b6fc9-142">Per eliminare un'area dal numero di accesso esterno, in **Aree associate** fare clic sull'area desiderata e quindi su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-142">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="b6fc9-143">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b6fc9-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

