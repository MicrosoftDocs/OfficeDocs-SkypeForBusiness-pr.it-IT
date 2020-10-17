---
title: "Lync Server 2013: configurare i criteri di conferenza per l'accesso esterno"
description: "Lync Server 2013: configurare i criteri di conferenza per l'accesso esterno."
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
ms.openlocfilehash: dd8dee1d9e7e6391c6420b15a895199dfc7a8791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564392"
---
# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="68ba7-103">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ba7-103">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ba7-104">_**Ultimo argomento modificato:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="68ba7-104">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="68ba7-105">I criteri di conferenza sono un'impostazione dell'account utente che specifica l'esperienza di conferenza per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="68ba7-105">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="68ba7-106">È possibile creare criteri di conferenza con un ambito di sito o un ambito utente.</span><span class="sxs-lookup"><span data-stu-id="68ba7-106">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="68ba7-107">Le impostazioni dei criteri di conferenza comprendono numerosi aspetti della pianificazione e della partecipazione alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="68ba7-107">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="68ba7-108">Numerose impostazioni dei criteri di conferenza supportano le conferenze telefoniche con accesso esterno per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="68ba7-108">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="68ba7-109">Quando si configura una conferenza telefonica con accesso esterno, è necessario verificare che i campi siano impostati in modo appropriato per l'organizzazione e modificarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="68ba7-109">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="68ba7-110">Verificare i campi seguenti nei criteri di conferenza:</span><span class="sxs-lookup"><span data-stu-id="68ba7-110">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="68ba7-111">**Consenti ai partecipanti di invitare utenti**     anonimi Questa impostazione consente agli organizzatori di riunioni di invitare partecipanti anonimi, ovvero non autenticati, alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="68ba7-111">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="68ba7-112">Questa impostazione è facoltativa per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="68ba7-112">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="68ba7-113">Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="68ba7-113">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="68ba7-114">**Abilitare le conferenze telefoniche con accesso esterno PSTN**     Questa impostazione consente agli utenti di partecipare alla parte audio di una conferenza tramite la chiamata dalla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="68ba7-114">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="68ba7-115">Questa impostazione è obbligatoria per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="68ba7-115">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="68ba7-116">Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="68ba7-116">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="68ba7-117">**Consenti ai partecipanti anonimi di effettuare chiamate in uscita**     Questa impostazione consente agli utenti anonimi che sono già stati aggiunti alla riunione di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="68ba7-117">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="68ba7-118">Questa impostazione è facoltativa per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="68ba7-118">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="68ba7-119">Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="68ba7-119">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="68ba7-120">**Consenti ai partecipanti non abilitati per VoIP aziendale di effettuare la chiamata in uscita**     Questa impostazione consente agli organizzatori e ai partecipanti alla riunione che non sono abilitati per VoIP aziendale di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="68ba7-120">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="68ba7-121">La chiamata in uscita è autorizzata in base ai criteri vocali assegnati all'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="68ba7-121">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="68ba7-122">Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="68ba7-122">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="68ba7-123">Il valore predefinito dell'impostazione è Disabled.</span><span class="sxs-lookup"><span data-stu-id="68ba7-123">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68ba7-124">Per abilitare questa funzionalità, un organizzatore di riunioni non abilitato per VoIP aziendale deve disporre di un criterio vocale appropriato assegnato per autorizzare qualsiasi chiamata in uscita da una conferenza organizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="68ba7-124">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="68ba7-125">È possibile assegnare un criterio vocale a un utente che non è abilitato per VoIP aziendale da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="68ba7-125">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="68ba7-126">Se all'utente non è assegnato esplicitamente un criterio vocale, il criterio vocale del sito verrà utilizzato per autorizzare la richiesta di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="68ba7-126">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="68ba7-127">Se non è presente alcun criterio vocale del sito, verrà utilizzato il criterio vocale globale.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="68ba7-127">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="68ba7-128">Nella procedura descritta in questa sezione viene illustrato come modificare i criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="68ba7-128">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="68ba7-129">Per informazioni dettagliate su come configurare tutte le impostazioni che definiscono l'esperienza dei partecipanti nei criteri di conferenza predefiniti, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="68ba7-129">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="68ba7-130">Per informazioni dettagliate sulla creazione di un criterio di conferenza per un utente o un gruppo di utenti specifico, vedere [Create or modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="68ba7-130">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="68ba7-131">Per un elenco di tutte le impostazioni disponibili per i criteri di conferenza, vedere informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="68ba7-131">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="68ba7-132">Per modificare i criteri di conferenza per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="68ba7-132">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="68ba7-133">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="68ba7-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="68ba7-134">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68ba7-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68ba7-135">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68ba7-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68ba7-136">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="68ba7-136">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="68ba7-137">Nella scheda **criteri conferenza** fare doppio clic su un nome per i criteri di conferenza per aprire la finestra di dialogo **modifica criterio conferenza** .</span><span class="sxs-lookup"><span data-stu-id="68ba7-137">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="68ba7-138">Verificare che i campi per le conferenze telefoniche con accesso esterno siano adatti all'organizzazione e modificare le impostazioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="68ba7-138">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="68ba7-139">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="68ba7-139">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

