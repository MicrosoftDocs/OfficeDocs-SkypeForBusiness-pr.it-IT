---
title: "Lync Server 2013: Configurare i criteri di conferenza per l'accesso esterno"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74621fee97a1e6721f8772b265761b62b1b9f266
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="34724-102">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34724-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34724-103">_**Argomento Ultima modifica:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="34724-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="34724-104">Criteri di conferenza è un'impostazione dell'account utente che specifica l'esperienza di conferenza per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="34724-104">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="34724-105">È possibile creare criteri di conferenza con un ambito del sito o un ambito utente.</span><span class="sxs-lookup"><span data-stu-id="34724-105">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="34724-106">Le impostazioni dei criteri di conferenza includono molti aspetti della pianificazione e della partecipazione a conferenze.</span><span class="sxs-lookup"><span data-stu-id="34724-106">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="34724-107">Diverse impostazioni dei criteri di conferenza supportano i servizi di conferenza telefonica con accesso esterno per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="34724-107">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="34724-108">Quando si configurano i servizi di conferenza telefonica con accesso esterno, è necessario verificare che questi campi siano impostati in modo appropriato per l'organizzazione e modificarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="34724-108">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="34724-109">Verificare i campi seguenti nei criteri di conferenza:</span><span class="sxs-lookup"><span data-stu-id="34724-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="34724-110">**Consentire ai partecipanti di invitare utenti**   anonimi questa impostazione consente agli organizzatori della riunione di invitare partecipanti anonimi (ovvero non autenticati) alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="34724-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="34724-111">Questa impostazione è facoltativa per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="34724-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="34724-112">Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="34724-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="34724-113">**Abilitare i servizi di conferenza telefonica con accesso esterno**   PSTN Questa impostazione consente agli utenti di partecipare alla parte audio di una conferenza effettuando la chiamata dalla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="34724-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="34724-114">Questa impostazione è necessaria per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="34724-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="34724-115">Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="34724-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="34724-116">**Consentire ai partecipanti anonimi di effettuare chiamate in uscita**   questa impostazione consente agli utenti anonimi già iscritti alla riunione di effettuare chiamate in uscita a un numero di telefono per partecipare alla parte audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="34724-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="34724-117">Questa impostazione è facoltativa per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="34724-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="34724-118">Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="34724-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="34724-119">**Consenti ai partecipanti non abilitati per la chiamata a VoIP aziendale**   questa impostazione consente ai partecipanti e agli organizzatori della riunione che non sono abilitati per VoIP aziendale di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="34724-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="34724-120">La chiamata esterna è autorizzata in base al criterio vocale assegnato dall'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="34724-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="34724-121">Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="34724-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="34724-122">Il valore predefinito dell'impostazione è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="34724-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34724-123">Per abilitare questa funzionalità, un organizzatore della riunione non abilitato per VoIP aziendale dovrebbe avere un criterio vocale appropriato assegnato per autorizzare qualsiasi chiamata in uscita da una conferenza organizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="34724-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="34724-124">Un criterio vocale può essere assegnato a un utente che non è abilitato per VoIP aziendale da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="34724-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="34724-125">Se l'utente non ha un criterio vocale assegnato in modo esplicito, il criterio vocale del sito verrà usato per autorizzare la richiesta di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="34724-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="34724-126">Se non è presente alcun criterio vocale del sito, verrà usato il criterio vocale globale.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="34724-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="34724-127">La procedura descritta in questa sezione illustra come modificare i criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="34724-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="34724-128">Per informazioni dettagliate su come configurare tutte le impostazioni che definiscono l'esperienza dei partecipanti nei criteri di conferenza predefiniti, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="34724-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="34724-129">Per informazioni dettagliate su come creare criteri per i servizi di conferenza per un utente o un gruppo di utenti specifico, vedere [creare o modificare criteri per i servizi di conferenza in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="34724-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="34724-130">Per un elenco di tutte le impostazioni dei criteri di conferenza disponibili, vedere informazioni di [riferimento sulle impostazioni per i criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="34724-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="34724-131">Per modificare i criteri di conferenza per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="34724-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="34724-132">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="34724-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="34724-133">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34724-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="34724-134">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="34724-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34724-135">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.</span><span class="sxs-lookup"><span data-stu-id="34724-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="34724-136">Nella scheda **criteri di conferenza** fare doppio clic su un nome per i criteri di conferenza per aprire la finestra di dialogo **modifica criteri di conferenza** .</span><span class="sxs-lookup"><span data-stu-id="34724-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="34724-137">Verificare che i campi per i servizi di conferenza telefonica con accesso esterno siano appropriati per l'organizzazione e modificare le impostazioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="34724-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="34724-138">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="34724-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

