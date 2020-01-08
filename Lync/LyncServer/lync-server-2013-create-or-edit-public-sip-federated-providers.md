---
title: 'Lync Server 2013: Creare o modificare provider federati SIP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a79e840990afb0c9cf0bae4fc819ec10db5d8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="e00cc-102">Creare o modificare provider federati SIP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e00cc-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e00cc-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e00cc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e00cc-104">La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici,\!tra cui Windows Live Messenger, Yahoo e AOL.</span><span class="sxs-lookup"><span data-stu-id="e00cc-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="e00cc-105">Lync Server 2013 include configurazioni di provider pubbliche per America Online, Windows Live e Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="e00cc-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="e00cc-106">messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="e00cc-106">instant messaging.</span></span> <span data-ttu-id="e00cc-107">Ogni provider pubblico è configurato con il nome di dominio completo di Edge Server del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con persone presenti nell'elenco contatti che usano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="e00cc-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="e00cc-108">Come impostazione predefinita, nessuno dei provider pubblici è abilitato.</span><span class="sxs-lookup"><span data-stu-id="e00cc-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="e00cc-109">Prima di abilitare i provider pubblici, è consigliabile completare il contratto di licenza e il provisioning.</span><span class="sxs-lookup"><span data-stu-id="e00cc-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="e00cc-110">È possibile abilitare il provider prima di completare il lavoro di licenza e provisioning.</span><span class="sxs-lookup"><span data-stu-id="e00cc-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="e00cc-111">Gli utenti non saranno in grado di comunicare con i contatti di tali provider finché non viene completato il lavoro pre-requisito.</span><span class="sxs-lookup"><span data-stu-id="e00cc-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="e00cc-112">Per informazioni dettagliate sulle licenze e sul provisioning dei provider pubblici, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e00cc-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="e00cc-113">Usare la procedura seguente per creare o modificare provider pubblici:</span><span class="sxs-lookup"><span data-stu-id="e00cc-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="e00cc-114">Per creare o modificare provider pubblici</span><span class="sxs-lookup"><span data-stu-id="e00cc-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="e00cc-115">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e00cc-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e00cc-116">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e00cc-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e00cc-117">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e00cc-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e00cc-118">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="e00cc-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="e00cc-119">Se è necessario creare un nuovo provider pubblico, fare clic su **nuovo** e quindi su **provider pubblico**.</span><span class="sxs-lookup"><span data-stu-id="e00cc-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="e00cc-120">Se è necessario modificare una voce dall'elenco di provider pubblici, selezionare un provider pubblico, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e00cc-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="e00cc-121">Nella pagina **Modifica provider FEDERATO SIP** è possibile digitare o modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e00cc-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="e00cc-122">**Abilitare le comunicazioni con questo provider**   la selezione di questa impostazione consente agli utenti di questo provider di usare la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="e00cc-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="e00cc-123">**Nome provider:**   una proprietà obbligatoria, digitare il nome del provider che verrà riflesso nell'elenco dei provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="e00cc-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="e00cc-124">**Access Edge service (FQDN):**   una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="e00cc-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="e00cc-125">Queste informazioni vengono fornite come elemento predefinito e devono essere modificate solo se il provider pubblico apporta una modifica al nome di dominio completo del servizio Access Edge presso il provider pubblico.</span><span class="sxs-lookup"><span data-stu-id="e00cc-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="e00cc-126">**Livello di verifica predefinito:**   l'impostazione predefinita **consente agli utenti di comunicare con persone nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e inclusi nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="e00cc-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="e00cc-127">Selezionando **Consenti agli utenti di comunicare con tutti i membri che usano questo provider** , viene eliminata la restrizione che deve essere stata ricevuta e accettata da un contatto.</span><span class="sxs-lookup"><span data-stu-id="e00cc-127">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="e00cc-128">Questa impostazione non limita chi può contattarti dalla rete del provider pubblico.</span><span class="sxs-lookup"><span data-stu-id="e00cc-128">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="e00cc-129">Dopo aver configurato le impostazioni, fare clic su **conferma** per salvare o su **Annulla per annullare** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e00cc-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e00cc-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e00cc-130">See Also</span></span>


[<span data-ttu-id="e00cc-131">Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e00cc-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="e00cc-132">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e00cc-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

