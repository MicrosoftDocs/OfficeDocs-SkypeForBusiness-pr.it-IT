---
title: 'Lync Server 2013: Abilitare gli utenti di Lync per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="7cafd-102">Abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cafd-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cafd-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7cafd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7cafd-104">Puoi configurare gli utenti di Lync per il controllo delle chiamate remote usando i criteri di provisioning in banda basati su server.</span><span class="sxs-lookup"><span data-stu-id="7cafd-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="7cafd-105">È possibile gestire le impostazioni di provisioning in banda tramite il pannello di controllo di Lync Server o l'interfaccia della riga di comando di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7cafd-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="7cafd-106">Questi strumenti sostituiscono lo snap-in Strumentazione gestione Windows (WMI) usato per gestire le impostazioni dei criteri di gruppo nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="7cafd-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="7cafd-107">Se si preferisce consentire agli utenti di configurare le proprie impostazioni di controllo delle chiamate remote in Lync, è possibile configurare le impostazioni del controllo delle chiamate remote per gli utenti nel server senza specificare l' **URI del server di linea** e i valori degli URI di **linea** .</span><span class="sxs-lookup"><span data-stu-id="7cafd-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="7cafd-108">Assicurati di comunicare agli utenti l' **URI del server di linea** e i valori **URI** di linea appropriati e fornisci agli utenti le istruzioni per configurare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7cafd-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="7cafd-109">Per la procedura per configurare manualmente il controllo delle chiamate remote in Lync Server, vedere "impostare le opzioni e i <http://go.microsoft.com/fwlink/p/?linkid=210132> numeri dei telefoni" nella documentazione del client Lync nel sito Web di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="7cafd-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="7cafd-110">Se si dispone di una distribuzione di Communications Server 2007 R2 o Communications Server 2007 esistente, i client Communicator 2007 R2 e Communicator 2007 continueranno a usare criteri di gruppo durante la migrazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="7cafd-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="7cafd-111">Tuttavia, se si vuole che le impostazioni dei criteri vengano riportate ai client Lync, è necessario configurare le equivalenti impostazioni di provisioning in banda di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7cafd-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cafd-112">Per abilitare un utente per il controllo delle chiamate remote, è necessario specificare all'utente sia un URI di linea che un URI del server di linea.</span><span class="sxs-lookup"><span data-stu-id="7cafd-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="7cafd-113">Come descritto in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013</A>, è necessario assicurarsi di usare la sintassi richiesta dal gateway per queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7cafd-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="7cafd-114">Assicurarsi che il dominio nell'URI del server di linea sia lo stesso del dominio di destinazione specificato nel parametro MatchUri quando è stata configurata la route statica per il gateway.</span><span class="sxs-lookup"><span data-stu-id="7cafd-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="7cafd-115">L'URI di linea specifica il numero di telefono assegnato all'utente nel formato E. 164, con il prefisso "TEL:", ad esempio Tel: + 14255550150.</span><span class="sxs-lookup"><span data-stu-id="7cafd-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="7cafd-116">Se si vuole configurare un numero di interno, il formato è Tel: + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="7cafd-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="7cafd-117">Se l'URI di linea dell'utente è stato configurato in precedenza e il valore non è stato modificato, non è necessario specificare l'URI di linea quando si Abilita l'utente per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="7cafd-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="7cafd-118">Per abilitare il controllo delle chiamate remote per gli utenti abilitati a Lync tramite Management Shell</span><span class="sxs-lookup"><span data-stu-id="7cafd-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="7cafd-119">Accedere a un computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o come ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="7cafd-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="7cafd-120">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7cafd-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7cafd-121">Per usare il cmdlet **Set-CsUser** per configurare il controllo delle chiamate remote per un utente abilitato a Lync esistente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cafd-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="7cafd-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7cafd-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="7cafd-123">Per configurare gli utenti per il controllo delle chiamate remote tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7cafd-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7cafd-124">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7cafd-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7cafd-125">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7cafd-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7cafd-126">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7cafd-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7cafd-127">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="7cafd-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="7cafd-128">Nella casella **Cerca utenti** Digitare All (o la prima parte) del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) line dell'account utente desiderato, quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="7cafd-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="7cafd-129">Nella tabella fare clic sull'account utente che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="7cafd-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="7cafd-130">Nel menu **modifica** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="7cafd-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="7cafd-131">In **telefonia**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cafd-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="7cafd-132">Per abilitare il controllo delle chiamate remote per consentire all'utente di controllare il proprio telefono PBX (Private Branch Exchange) da Lync 2013 per effettuare chiamate audio da PC a PC e chiamate da PC a telefono, fare clic su **controllo delle chiamate remote**.</span><span class="sxs-lookup"><span data-stu-id="7cafd-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="7cafd-133">In **URI linea**specificare il numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7cafd-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="7cafd-134">In **URI del server di linea**specificare l'URI SIP del gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="7cafd-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="7cafd-135">Per abilitare il controllo delle chiamate remote, ma disabilitare le chiamate audio da PC a PC e per consentire solo all'utente di controllare il proprio telefono PBX da Lync 2013 per effettuare chiamate da PC a telefono, fare clic su **solo controllo chiamata remota**.</span><span class="sxs-lookup"><span data-stu-id="7cafd-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="7cafd-136">In **URI linea**specificare il numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7cafd-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="7cafd-137">In **URI del server di linea**specificare l'URI SIP del gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="7cafd-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="7cafd-138">Al termine, fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="7cafd-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

