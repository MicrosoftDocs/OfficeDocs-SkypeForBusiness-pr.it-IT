---
title: 'Lync Server 2013: cercare gli utenti di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b690b0880e1da838b3b8f15392e64c4f4c650c10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510493"
---
# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="3cf42-102">Cercare gli utenti di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cf42-102">Search for Lync Server users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf42-103">_**Ultimo argomento modificato:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="3cf42-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="3cf42-104">È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cf42-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="3cf42-105">È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea.</span><span class="sxs-lookup"><span data-stu-id="3cf42-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="3cf42-106">È possibile cercare gli utenti utilizzando il pannello di controllo di Lync Server o lo snap-in utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3cf42-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="3cf42-107">Nella procedura seguente viene descritto come utilizzare il pannello di controllo di Lync Server per cercare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3cf42-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3cf42-108">In un ambiente con una topologia a foresta centralizzata, i risultati della ricerca potrebbero non essere esatti quando si cerca un utente dall'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3cf42-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="3cf42-109">In alternativa, è possibile cercare gli utenti specificando un prefisso di indirizzo SIP, ad esempio SIP: nome, aggiungere un filtro di ricerca e selezionare un indirizzo SIP contenente un indirizzo di posta elettronica parziale oppure utilizzare il cmdlet <STRONG>Get-CSUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3cf42-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="3cf42-110">Per ricercare uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="3cf42-110">To search for one or more users</span></span>

1.  <span data-ttu-id="3cf42-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3cf42-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3cf42-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3cf42-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3cf42-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3cf42-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3cf42-114">Nella barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3cf42-115">Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account SAM, l'indirizzo SIP o l'URI linea dell'account utente da ricercare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="3cf42-116">(Facoltativo) Specificare ulteriori criteri di ricerca per circoscrivere i risultati:</span><span class="sxs-lookup"><span data-stu-id="3cf42-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3cf42-117">Fare clic sul pulsante freccia di espansione nell'angolo in alto a destra della schermata al di sopra di **Risultati della ricerca** e quindi fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3cf42-118">Digitare la proprietà utente oppure selezionarla facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3cf42-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="3cf42-119">Nell'elenco **Uguale a** selezionare **Uguale a** o **Diverso da**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="3cf42-120">Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="3cf42-p105">I risultati della ricerca verranno visualizzati al di sotto di **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti dell'elenco ed eseguire attività di configurazione sugli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="3cf42-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3cf42-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cf42-123">See Also</span></span>


[<span data-ttu-id="3cf42-124">Visualizzazione delle informazioni sugli account utente abilitati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cf42-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="3cf42-125">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cf42-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

