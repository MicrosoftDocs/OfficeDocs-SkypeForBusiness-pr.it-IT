---
title: Modificare l'azione predefinita per i client non esplicitamente supportati o limitati
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="7d842-102">Modificare l'azione predefinita per i client non esplicitamente supportati o limitati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d842-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d842-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7d842-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7d842-104">Oltre a specificare la versione dei client che si vuole supportare nell'ambiente Lync Server 2013, è anche possibile specificare un'azione predefinita per i client che non hanno già un criterio di versione definito.</span><span class="sxs-lookup"><span data-stu-id="7d842-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="7d842-105">Ciò consente di limitare le versioni client usate nell'ambiente Lync Server, che consentono di controllare i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="7d842-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="7d842-106">Per modificare l'azione predefinita per i client non esplicitamente supportati o limitati</span><span class="sxs-lookup"><span data-stu-id="7d842-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="7d842-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7d842-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7d842-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d842-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d842-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d842-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d842-110">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione versione client**.</span><span class="sxs-lookup"><span data-stu-id="7d842-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="7d842-111">Nella pagina **Configurazione versione client** fare doppio clic sulla configurazione **globale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7d842-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="7d842-112">Nella finestra di dialogo **modifica configurazione versione client** verificare che sia selezionata la casella di **controllo Enable Version Control** e quindi, in **azione predefinita**, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d842-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="7d842-113">**Consenti**   consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** .</span><span class="sxs-lookup"><span data-stu-id="7d842-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="7d842-114">**Il blocco**   impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** .</span><span class="sxs-lookup"><span data-stu-id="7d842-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="7d842-115">**Il blocco con URL**   impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** e include un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.</span><span class="sxs-lookup"><span data-stu-id="7d842-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="7d842-116">**Consenti con URL**   consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** e di includere un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.</span><span class="sxs-lookup"><span data-stu-id="7d842-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="7d842-117">Se si è selezionato **blocca con URL**, digitare l'URL di download del client da includere nel messaggio di errore nella casella **URL** .</span><span class="sxs-lookup"><span data-stu-id="7d842-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="7d842-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7d842-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="7d842-119">Per disabilitare il controllo della versione client</span><span class="sxs-lookup"><span data-stu-id="7d842-119">To disable client version control</span></span>

  - <span data-ttu-id="7d842-120">Per disabilitare il controllo della versione per consentire l'accesso a tutti i client indipendentemente dalla versione del client, deselezionare la casella di controllo **Enable Version Control** e quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="7d842-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7d842-121">Modifica dell'azione predefinita con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d842-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7d842-122">L'azione predefinita da eseguire quando gli utenti provano a eseguire l'accesso usando client non esplicitamente supportati o limitati da criteri di versione client possono essere gestiti usando l'interfaccia della riga di comando di Windows PowerShell e il cmdlet **Set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="7d842-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="7d842-123">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d842-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7d842-124">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="7d842-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="7d842-125">Per configurare l'azione predefinita per bloccare l'accesso</span><span class="sxs-lookup"><span data-stu-id="7d842-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="7d842-126">Il comando seguente imposta l'azione predefinita per il blocco di sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="7d842-126">The following command sets the default action for the Redmond site Block.</span></span> <span data-ttu-id="7d842-127">In questo modo si bloccherà la registrazione per qualsiasi client per cui non esiste alcuna regola di configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="7d842-127">This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="7d842-128">Per configurare l'azione predefinita per consentire l'accesso</span><span class="sxs-lookup"><span data-stu-id="7d842-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="7d842-129">In questo esempio l'azione predefinita per il sito Redmond è impostata su Consenti.</span><span class="sxs-lookup"><span data-stu-id="7d842-129">In this example, the default action for the Redmond site is set to Allow.</span></span> <span data-ttu-id="7d842-130">Ciò consentirà la registrazione per qualsiasi client per cui non esiste alcuna regola di configurazione della versione client.</span><span class="sxs-lookup"><span data-stu-id="7d842-130">This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="7d842-131">Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="7d842-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d842-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d842-132">See Also</span></span>


[<span data-ttu-id="7d842-133">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d842-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

