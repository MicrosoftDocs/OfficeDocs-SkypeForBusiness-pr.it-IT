---
title: 'Lync Server 2013: Creare o modificare provider federati SIP ospitati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbdc22f2e877d7dafc8f52506d77312730ab428
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="68168-102">Creare o modificare provider federati SIP ospitati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68168-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68168-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="68168-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="68168-104">La connettività di messaggistica istantanea del provider ospitata consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti da provider ospitati, tra cui Microsoft Office 365 e Lync Online.</span><span class="sxs-lookup"><span data-stu-id="68168-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="68168-105">Ogni provider ospitato è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con persone presenti nell'elenco contatti che usano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="68168-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="68168-106">Usare la procedura seguente per creare o modificare i provider ospitati:</span><span class="sxs-lookup"><span data-stu-id="68168-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="68168-107">Per creare o modificare i provider ospitati</span><span class="sxs-lookup"><span data-stu-id="68168-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="68168-108">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="68168-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68168-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68168-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68168-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68168-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68168-111">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="68168-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="68168-112">Se è necessario creare un nuovo provider ospitato, fare clic su **nuovo** e quindi su **provider ospitati**.</span><span class="sxs-lookup"><span data-stu-id="68168-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="68168-113">Se è necessario modificare una voce dall'elenco di provider ospitati, selezionare un provider ospitata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="68168-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="68168-114">Nella pagina **Modifica provider FEDERATO SIP** è possibile digitare o modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68168-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="68168-115">**Abilitare le comunicazioni con questo provider**   Selezionare questa impostazione consente le comunicazioni con gli utenti del provider.</span><span class="sxs-lookup"><span data-stu-id="68168-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="68168-116">**Nome provider:**   una proprietà obbligatoria, digitare il nome del provider che verrà riflesso nell'elenco dei provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="68168-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="68168-117">**Access Edge service (FQDN):**   una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider ospitato che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="68168-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="68168-118">Queste informazioni devono essere fornite dal provider ospitato e devono essere modificate solo se il provider ospitato apporta una modifica all'FQDN del servizio Access Edge presso il provider ospitata.</span><span class="sxs-lookup"><span data-stu-id="68168-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="68168-119">**Livello di verifica predefinito:**   l'impostazione predefinita **consente agli utenti di comunicare con persone nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e inclusi nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="68168-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="68168-120">Selezionando **Consenti agli utenti di comunicare con tutti i membri che usano questo provider** , viene eliminata la restrizione che deve essere stata ricevuta e accettata da un contatto.</span><span class="sxs-lookup"><span data-stu-id="68168-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="68168-121">Questa impostazione non limita chi può contattarti dalla rete del provider ospitata.</span><span class="sxs-lookup"><span data-stu-id="68168-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="68168-122">Dopo aver configurato le impostazioni, fare clic su **conferma** per salvare o su **Annulla per annullare** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="68168-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68168-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68168-123">See Also</span></span>


[<span data-ttu-id="68168-124">Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68168-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="68168-125">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68168-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

