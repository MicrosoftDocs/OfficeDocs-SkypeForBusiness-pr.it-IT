---
title: 'Lync Server 2013: Configurare componenti aggiuntivi per le chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8389f72394be26057eb12560c054bd5292b528f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="5e9a8-102">Configurare componenti aggiuntivi per le chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e9a8-102">Configure add-ins for rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e9a8-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5e9a8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5e9a8-104">Nel pannello di controllo di Lync Server 2013 è possibile usare la sezione **componente aggiuntivo** della pagina della **chat persistente** per associare gli URL alle chat room permanenti.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-104">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="5e9a8-105">Questi URL vengono visualizzati nel client Lync 2013 nella chat room nel riquadro Extensibility delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-105">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="5e9a8-106">Un amministratore deve aggiungere componenti aggiuntivi all'elenco di componenti aggiuntivi registrati e i responsabili/creatori della chat room devono associare le camere a uno dei componenti aggiuntivi registrati prima che gli utenti possano vedere questo aggiornamento nel client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-106">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="5e9a8-107">I componenti aggiuntivi sono usati per ampliare l'esperienza all'interno della chat.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-107">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="5e9a8-108">Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker del titolo viene inserito in una chat room e Mostra la cronologia del titolo nel riquadro estensibilità.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-108">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="5e9a8-109">Altri esempi sono l'incorporamento di un URL di OneNote 2013 nella chat room come componente aggiuntivo per includere contenuto condiviso, ad esempio "In primo piano" o "Argomento del giorno".</span><span class="sxs-lookup"><span data-stu-id="5e9a8-109">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="5e9a8-110">Per configurare componenti aggiuntivi per le chat room</span><span class="sxs-lookup"><span data-stu-id="5e9a8-110">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="5e9a8-111">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-111">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5e9a8-112">Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5e9a8-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5e9a8-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5e9a8-114">È anche possibile usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5e9a8-115">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="5e9a8-116">Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-116">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="5e9a8-117">Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-117">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="5e9a8-118">Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-118">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="5e9a8-119">In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui è necessario creare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="5e9a8-120">I componenti aggiuntivi non possono essere spostati da un pool a un altro o condivisi da pool diversi.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="5e9a8-121">In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e9a8-121">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="5e9a8-122">In **Nome** specificare un nome per il nuovo componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-122">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="5e9a8-p106">In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL devono limitarsi ai protocolli http e https.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="5e9a8-125">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5e9a8-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e9a8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e9a8-126">See Also</span></span>


[<span data-ttu-id="5e9a8-127">Aprire gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e9a8-127">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="5e9a8-128">Configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e9a8-128">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

