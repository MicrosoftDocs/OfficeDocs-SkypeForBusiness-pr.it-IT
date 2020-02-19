---
title: "Lync Server 2013: configurare i criteri di conferenza per l'accesso esterno"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a74d49797565f643e36dfc59956ecc3ad73824e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="6395d-102">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6395d-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6395d-103">_**Ultimo argomento modificato:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="6395d-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="6395d-104">I criteri di conferenza sono un'impostazione dell'account utente che specifica l'esperienza di conferenza per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="6395d-104">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="6395d-105">È possibile creare criteri di conferenza con un ambito di sito o un ambito utente.</span><span class="sxs-lookup"><span data-stu-id="6395d-105">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="6395d-106">Le impostazioni dei criteri di conferenza comprendono numerosi aspetti della pianificazione e della partecipazione alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="6395d-106">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="6395d-107">Numerose impostazioni dei criteri di conferenza supportano le conferenze telefoniche con accesso esterno per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="6395d-107">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="6395d-108">Quando si configura una conferenza telefonica con accesso esterno, è necessario verificare che i campi siano impostati in modo appropriato per l'organizzazione e modificarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6395d-108">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="6395d-109">Verificare i campi seguenti nei criteri di conferenza:</span><span class="sxs-lookup"><span data-stu-id="6395d-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="6395d-110">**Consenti ai partecipanti di invitare utenti**   anonimi questa impostazione consente agli organizzatori di riunioni di invitare partecipanti anonimi, ovvero non autenticati, alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="6395d-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="6395d-111">Questa impostazione è facoltativa per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6395d-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="6395d-112">Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6395d-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="6395d-113">**Abilitare le conferenze telefoniche con accesso esterno**   PSTN Questa impostazione consente agli utenti di partecipare alla parte audio di una conferenza tramite la chiamata dalla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="6395d-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="6395d-114">Questa impostazione è obbligatoria per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6395d-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="6395d-115">Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6395d-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="6395d-116">**Consenti ai partecipanti anonimi di**   effettuare la chiamata in uscita questa impostazione consente agli utenti anonimi che sono già stati aggiunti alla riunione di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="6395d-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="6395d-117">Questa impostazione è facoltativa per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6395d-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="6395d-118">Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6395d-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="6395d-119">**Consenti ai partecipanti non abilitati per VoIP aziendale di comporre**   questa impostazione consente ai partecipanti e agli organizzatori della riunione che non sono abilitati per VoIP aziendale di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="6395d-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="6395d-120">La chiamata in uscita è autorizzata in base ai criteri vocali assegnati all'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="6395d-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="6395d-121">Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6395d-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="6395d-122">Il valore predefinito dell'impostazione è Disabled.</span><span class="sxs-lookup"><span data-stu-id="6395d-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6395d-123">Per abilitare questa funzionalità, un organizzatore di riunioni non abilitato per VoIP aziendale deve disporre di un criterio vocale appropriato assegnato per autorizzare qualsiasi chiamata in uscita da una conferenza organizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6395d-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="6395d-124">È possibile assegnare un criterio vocale a un utente che non è abilitato per VoIP aziendale da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6395d-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="6395d-125">Se all'utente non è assegnato esplicitamente un criterio vocale, il criterio vocale del sito verrà utilizzato per autorizzare la richiesta di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="6395d-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="6395d-126">Se non è presente alcun criterio vocale del sito, verrà utilizzato il criterio vocale globale.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="6395d-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="6395d-127">Nella procedura descritta in questa sezione viene illustrato come modificare i criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="6395d-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="6395d-128">Per informazioni dettagliate su come configurare tutte le impostazioni che definiscono l'esperienza dei partecipanti nei criteri di conferenza predefiniti, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6395d-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="6395d-129">Per informazioni dettagliate sulla creazione di un criterio di conferenza per un utente o un gruppo di utenti specifico, vedere [Create or modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6395d-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="6395d-130">Per un elenco di tutte le impostazioni disponibili per i criteri di conferenza, vedere informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="6395d-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="6395d-131">Per modificare i criteri di conferenza per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="6395d-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="6395d-132">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="6395d-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="6395d-133">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6395d-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6395d-134">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6395d-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6395d-135">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="6395d-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="6395d-136">Nella scheda **criteri conferenza** fare doppio clic su un nome per i criteri di conferenza per aprire la finestra di dialogo **modifica criterio conferenza** .</span><span class="sxs-lookup"><span data-stu-id="6395d-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="6395d-137">Verificare che i campi per le conferenze telefoniche con accesso esterno siano adatti all'organizzazione e modificare le impostazioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="6395d-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="6395d-138">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="6395d-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

