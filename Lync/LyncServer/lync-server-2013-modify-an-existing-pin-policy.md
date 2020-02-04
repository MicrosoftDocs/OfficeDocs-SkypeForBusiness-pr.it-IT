---
title: 'Lync Server 2013: modificare un criterio PIN esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19d2a3d259ee5f45241063764cfd905cbd0f0854
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a><span data-ttu-id="1bd7f-102">Modificare un criterio PIN esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bd7f-102">Modify an existing PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bd7f-103">_**Argomento Ultima modifica:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="1bd7f-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="1bd7f-104">È possibile usare la scheda **criteri PIN** per specificare l'autenticazione PIN (Personal Identification Number) per gli utenti che si connettono a Lync 2013 con telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-104">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="1bd7f-105">Per usare l'autenticazione PIN, verificare che **l'opzione Abilita autenticazione PIN** sia selezionata nelle impostazioni del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="1bd7f-106">Per informazioni dettagliate, vedere [modificare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1bd7f-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="1bd7f-107">Seguire questa procedura per modificare un criterio PIN a livello di utente o a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="1bd7f-108">Per modificare un criterio PIN esistente</span><span class="sxs-lookup"><span data-stu-id="1bd7f-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="1bd7f-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1bd7f-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1bd7f-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1bd7f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1bd7f-112">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="1bd7f-113">Nella pagina **criteri PIN** fare clic su un criterio, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1bd7f-114">In **modifica criterio PIN**, in **lunghezza minima PIN**, digitare o selezionare la lunghezza minima del PIN che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-114">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="1bd7f-115">La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-115">The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="1bd7f-116">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **specifica tentativi di accesso massimo** .</span><span class="sxs-lookup"><span data-stu-id="1bd7f-116">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="1bd7f-117">Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-117">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="1bd7f-118">Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-118">By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="1bd7f-119">Se è stata selezionata la casella di controllo **specifica tentativi di accesso massimo** , in **tentativi di accesso massimo**digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-119">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="1bd7f-120">Per impostare i pin in scadenza, selezionare la casella di controllo **Abilita scadenza PIN** .</span><span class="sxs-lookup"><span data-stu-id="1bd7f-120">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="1bd7f-121">Se non si seleziona questa opzione, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-121">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="1bd7f-122">Per impostazione predefinita, i pin non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-122">By default, PINs never expire.</span></span>

9.  <span data-ttu-id="1bd7f-123">Se è stata selezionata la casella di controllo **Abilita scadenza PIN** , in **PIN scade dopo (giorni)** digitare o selezionare il numero di giorni dopo il quale i pin scadono.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-123">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="1bd7f-124">In **conteggio cronologia PIN**Digitare il numero di pin che un utente deve creare prima che l'utente possa riutilizzare un PIN.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-124">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="1bd7f-125">Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-125">By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="1bd7f-126">Per consentire modelli comuni di cifre nei pin, ad esempio numeri sequenziali e set ripetitivi di numeri, selezionare la casella di controllo **Consenti schemi comuni** .</span><span class="sxs-lookup"><span data-stu-id="1bd7f-126">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="1bd7f-127">Se non si seleziona questa opzione, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-127">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="1bd7f-128">Per impostazione predefinita, sono consentiti solo modelli complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-128">By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1bd7f-129">È consigliabile non consentire modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-129">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="1bd7f-130">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1bd7f-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

