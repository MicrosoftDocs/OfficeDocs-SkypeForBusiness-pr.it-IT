---
title: 'Lync Server 2013: Creare o modificare le impostazioni del PIN di conferenza telefonica con accesso esterno per un sito o un gruppo di utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2af1dc8e3f9bde06e799c758b711f94b7c0e6411
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="8cd1f-102">Creare o modificare le impostazioni del PIN di conferenza telefonica con accesso esterno in Lync Server 2013 per un sito o un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="8cd1f-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cd1f-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8cd1f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8cd1f-104">Seguire questa procedura per creare o modificare un criterio PIN (Personal Identification Number) dei servizi di conferenza telefonica con accesso esterno a livello di utente o a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="8cd1f-105">Per informazioni dettagliate su come modificare il criterio PIN globale, vedere [modificare le impostazioni predefinite dei pin per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8cd1f-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="8cd1f-106">Per creare un criterio PIN per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="8cd1f-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="8cd1f-107">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8cd1f-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8cd1f-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8cd1f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8cd1f-110">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="8cd1f-111">Nella pagina **criteri PIN** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cd1f-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="8cd1f-112">Per creare un criterio a livello di utente, fare clic su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-112">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="8cd1f-113">In **nome**digitare un nome che descriva il criterio in **nuovo criterio PIN**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-113">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="8cd1f-114">Per creare un criterio a livello di sito, fare clic su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-114">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="8cd1f-115">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-115">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="8cd1f-116">Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-116">In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="8cd1f-117">Nel campo **Descrizione** Digitare una descrizione del criterio PIN.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="8cd1f-118">Nel campo **lunghezza minima PIN** Digitare o selezionare la lunghezza minima del PIN che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-118">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="8cd1f-119">La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-119">The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="8cd1f-120">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** .</span><span class="sxs-lookup"><span data-stu-id="8cd1f-120">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="8cd1f-121">Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-121">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="8cd1f-122">Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-122">By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="8cd1f-123">Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="8cd1f-124">Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** .</span><span class="sxs-lookup"><span data-stu-id="8cd1f-124">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="8cd1f-125">Se non si seleziona questa opzione, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-125">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="8cd1f-126">Per impostazione predefinita, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-126">By default, PINs never expire.</span></span>

10. <span data-ttu-id="8cd1f-127">Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="8cd1f-128">In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-128">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="8cd1f-129">Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-129">By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="8cd1f-130">Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** .</span><span class="sxs-lookup"><span data-stu-id="8cd1f-130">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="8cd1f-131">Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-131">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="8cd1f-132">Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-132">By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8cd1f-133">È consigliabile non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="8cd1f-134">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="8cd1f-135">Per modificare un criterio PIN per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="8cd1f-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="8cd1f-136">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8cd1f-137">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8cd1f-138">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8cd1f-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8cd1f-139">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="8cd1f-140">Nella pagina **criteri PIN** fare clic sul criterio PIN che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8cd1f-141">In **modifica criterio PIN**modificare le impostazioni dei criteri (ad eccezione del nome del criterio, che non può essere modificato).</span><span class="sxs-lookup"><span data-stu-id="8cd1f-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="8cd1f-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8cd1f-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

