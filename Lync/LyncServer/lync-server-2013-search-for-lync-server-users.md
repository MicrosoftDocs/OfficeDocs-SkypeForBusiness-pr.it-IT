---
title: 'Lync Server 2013: cercare utenti di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068fe07bf14894d22f929291514854360d6d0465
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="d9e1f-102">Cercare gli utenti di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9e1f-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9e1f-103">_**Argomento Ultima modifica:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="d9e1f-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="d9e1f-104">È possibile usare i risultati di una query di ricerca per configurare gli utenti per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="d9e1f-105">È possibile cercare gli utenti per nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (SAM), indirizzo SIP o URI (Uniform Resource Identifier) linea.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="d9e1f-106">È possibile cercare gli utenti usando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="d9e1f-107">La procedura seguente descrive come usare il pannello di controllo di Lync Server per cercare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9e1f-108">In un ambiente con una topologia di foresta centrale i risultati della ricerca potrebbero non essere precisi quando si cerca un utente tramite l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="d9e1f-109">È invece possibile cercare gli utenti specificando un prefisso di indirizzo SIP, ad esempio SIP: Name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP che contiene un indirizzo di posta elettronica parziale oppure usare il cmdlet <STRONG>Get-CSUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d9e1f-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="d9e1f-110">Per cercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="d9e1f-110">To search for one or more users</span></span>

1.  <span data-ttu-id="d9e1f-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9e1f-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9e1f-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d9e1f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9e1f-114">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d9e1f-115">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome dell'account SAM, indirizzo SIP o URI di linea dell'account utente che si desidera cercare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="d9e1f-116">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="d9e1f-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="d9e1f-117">Fare clic sul pulsante Espandi freccia nell'angolo in alto a destra dello schermo sopra i **Risultati della ricerca**e quindi fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="d9e1f-118">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare una proprietà utente.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="d9e1f-119">Nell'elenco **uguale a** fare clic su **uguale** a o **non uguale a**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="d9e1f-120">Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="d9e1f-121">I risultati della ricerca vengono visualizzati nei **Risultati della ricerca**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-121">The search results appear under **Search Results**.</span></span> <span data-ttu-id="d9e1f-122">È possibile selezionare uno o tutti gli utenti nell'elenco ed eseguire attività di configurazione per gli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-122">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9e1f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9e1f-123">See Also</span></span>


[<span data-ttu-id="d9e1f-124">Visualizzazione di informazioni sugli account utente abilitati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9e1f-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="d9e1f-125">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9e1f-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

