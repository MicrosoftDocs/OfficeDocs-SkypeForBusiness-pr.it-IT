---
title: 'Lync Server 2013: creare o modificare provider federati SIP ospitati'
description: 'Lync Server 2013: creare o modificare provider federati SIP ospitati.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaaa1b29b9a85332b85dfb7a1f258503fa4e9c77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553882"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="9ef1c-103">Creare o modificare provider federati SIP ospitati Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ef1c-103">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ef1c-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9ef1c-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9ef1c-105">La connettività di messaggistica istantanea (IM) del provider hosted consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti da provider ospitati, tra cui Microsoft 365 e Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-105">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="9ef1c-106">Ogni provider ospitato è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-106">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="9ef1c-107">Per creare o modificare provider gestiti, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9ef1c-107">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="9ef1c-108">Per creare o modificare provider gestiti</span><span class="sxs-lookup"><span data-stu-id="9ef1c-108">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="9ef1c-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ef1c-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ef1c-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ef1c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ef1c-112">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-112">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="9ef1c-113">Se è necessario creare un nuovo provider ospitato fare clic su **Nuovo** e quindi su **Provider ospitato**.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-113">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="9ef1c-114">Se è necessario modificare una voce nell'elenco di provider ospitati, selezionare un provider ospitato, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-114">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="9ef1c-115">Nella pagina **Modifica provider federato SIP** è possibile immettere o modificare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9ef1c-115">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="9ef1c-116">**Abilitare le comunicazioni con questo provider**     Selezionando questa impostazione, viene abilitata la comunicazione con gli utenti del provider.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-116">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="9ef1c-117">**Nome provider:**     Una proprietà obbligatoria, digitare il nome del provider come verrà riflesso nell'elenco dei provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-117">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="9ef1c-118">**Servizio Access Edge (FQDN):**     Una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider ospitato che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-118">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="9ef1c-119">Queste informazioni devono essere fornite dal provider ospitato e devono essere modificate solo se il provider ospitato apporta una modifica al nome di dominio completo del servizio Access Edge nel provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-119">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="9ef1c-120">**Livello di verifica predefinito:**     L'impostazione predefinita **consente agli utenti di comunicare con le persone presenti nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e che si trovano nell'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-120">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="9ef1c-p103">Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider**, viene rimossa la limitazione che prevede che sia stato ricevuto e accettato un invito di contatto. Questa impostazione non limita gli utenti dai quali è possibile essere contattati dalla rete del provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="9ef1c-123">Terminata la configurazione delle impostazioni, fare clic su **Commit** per salvare oppure su **Annulla** per annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9ef1c-123">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ef1c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ef1c-124">See Also</span></span>


[<span data-ttu-id="9ef1c-125">Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ef1c-125">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="9ef1c-126">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ef1c-126">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

