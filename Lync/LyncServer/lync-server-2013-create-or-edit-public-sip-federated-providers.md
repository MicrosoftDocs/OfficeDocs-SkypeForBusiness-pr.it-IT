---
title: 'Lync Server 2013: creare o modificare provider federati SIP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51e31c731270bc0e3e25da712db5aff9137d84b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="0f4c8-102">Creare o modificare provider federati SIP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f4c8-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f4c8-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0f4c8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0f4c8-104">La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici,\!inclusi Windows Live Messenger, Yahoo e AOL.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="0f4c8-105">Lync Server 2013 dispone di configurazioni di provider pubblici per America Online, Windows Live e Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="0f4c8-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="0f4c8-106">messaggistica immediata.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-106">instant messaging.</span></span> <span data-ttu-id="0f4c8-107">Ogni provider pubblico è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con le persone presenti nell'elenco dei contatti che utilizzano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="0f4c8-108">Come impostazione predefinita, nessuno dei provider pubblici è abilitato.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="0f4c8-109">Prima di abilitare i provider pubblici, è necessario completare il contratto di licenza e il provisioning.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="0f4c8-110">È possibile abilitare il provider prima di completare il lavoro di gestione delle licenze e del provisioning.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="0f4c8-111">Gli utenti non saranno in grado di comunicare con i contatti su tali provider fino al completamento del lavoro prerequisito.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="0f4c8-112">Per informazioni dettagliate sulle licenze e il provisioning dei provider pubblici, vedere [Configure policies to Control public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0f4c8-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="0f4c8-113">Per creare o modificare provider pubblici, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0f4c8-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="0f4c8-114">Per creare o modificare provider pubblici:</span><span class="sxs-lookup"><span data-stu-id="0f4c8-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="0f4c8-115">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0f4c8-116">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0f4c8-117">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0f4c8-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0f4c8-118">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="0f4c8-119">Se è necessario creare un nuovo provider pubblico, fare clic su **Nuovo** e quindi su **Provider pubblico**.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="0f4c8-120">Se è necessario modificare una voce dell'elenco di provider pubblici, selezionare un provider pubblico, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="0f4c8-121">Nella pagina **Modifica Provider federato SIP** è possibile digitare o modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f4c8-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="0f4c8-122">**Abilita comunicazioni con questo provider**   la selezione di questa impostazione consente di abilitare la messaggistica istantanea con gli utenti di questo provider.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="0f4c8-123">**Nome provider:**   una proprietà obbligatoria, digitare il nome del provider come verrà riflesso nell'elenco dei provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="0f4c8-124">**Servizio Access Edge (FQDN):**   una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="0f4c8-125">Queste informazioni vengono fornite come elementi predefiniti e devono essere modificate solo se il provider pubblico apporta una modifica al nome di dominio completo del servizio Access Edge nel provider pubblico.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="0f4c8-126">**Livello di verifica predefinito:**   l'impostazione predefinita, **Consenti agli utenti di comunicare con persone presenti nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e che si trovano nell'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="0f4c8-p105">Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider** rimuove la limitazione di dover ricevere e accettare l'invito di un contatto. Questa impostazione non impone limiti sugli utenti della rete del provider pubblico da cui si può essere contattati.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="0f4c8-129">Al termine della configurazione delle impostazioni, fare clic su **Commit** per salvare o su **Annulla** per annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f4c8-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f4c8-130">See Also</span></span>


[<span data-ttu-id="0f4c8-131">Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f4c8-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="0f4c8-132">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f4c8-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

