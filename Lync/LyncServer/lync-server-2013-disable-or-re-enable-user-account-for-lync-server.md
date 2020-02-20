---
title: "Lync Server 2013: disabilitare o riabilitare l'account utente per Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 502b4cc9c6ed70d0a418dbed7e844064939809d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="0dc2d-102">Disabilitare o riabilitare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dc2d-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dc2d-103">_**Ultimo argomento modificato:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="0dc2d-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="0dc2d-104">È possibile utilizzare la procedura seguente per disabilitare un account utente abilitato in precedenza in Lync Server 2013 senza perdere le impostazioni di Lync Server configurate per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="0dc2d-105">Poiché le impostazioni dell'account utente di Lync Server non vengono perse, è possibile riattivare nuovamente un account utente abilitato in precedenza senza dover riconfigurare l'account utente.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0dc2d-106">La semplice disabilitazione di un account utente in Active Directory <STRONG>non</STRONG> impedirà a un utente di accedere o utilizzare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="0dc2d-107">Ciò è dovuto al fatto che Lync utilizza l'autenticazione dei certificati per semplificare il processo di autenticazione e questi certificati client sono validi per 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="0dc2d-108">Se si desidera arrestare gli account di Active Directory disabilitati che sono stati abilitati per Lync dall'accesso a Lync Server, è necessario utilizzare il cmdlet <STRONG>Disable-CsUser</STRONG> oppure utilizzare il <STRONG>Pannello di controllo di Lync Server</STRONG> come indicato in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="0dc2d-109">Dopo che l'utente è stato disabilitato in Lync e l'archivio di gestione centrale è stato replicato nell'ambiente, gli utenti non saranno più in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="0dc2d-110">Inoltre, gli utenti che hanno effettuato l'accesso verranno disconnessi.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="0dc2d-111">Per disabilitare o riabilitare un account utente abilitato in precedenza per Lync Server</span><span class="sxs-lookup"><span data-stu-id="0dc2d-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="0dc2d-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0dc2d-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0dc2d-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0dc2d-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0dc2d-115">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0dc2d-116">Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome di account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o abilitare di nuovo e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="0dc2d-117">Nella tabella fare clic sull'account utente che si desidera disabilitare o abilitare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="0dc2d-118">Dal menu **Azione** scegliere uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dc2d-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="0dc2d-119">Per disabilitare temporaneamente l'account utente per Lync Server 2013, fare clic su **Disabilita temporaneamente per Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="0dc2d-120">Per abilitare l'account utente per Lync Server 2013, fare clic su **riattiva per Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="0dc2d-121">Utilizzo di Windows PowerShell per disabilitare o riabilitare gli account utente</span><span class="sxs-lookup"><span data-stu-id="0dc2d-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="0dc2d-122">Gli account utente possono essere temporaneamente disattivati e quindi riattivati in un secondo momento utilizzando il cmdlet **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="0dc2d-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="0dc2d-123">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0dc2d-124">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="0dc2d-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="0dc2d-125">Per disabilitare un account utente</span><span class="sxs-lookup"><span data-stu-id="0dc2d-125">To disable a user account</span></span>

  - <span data-ttu-id="0dc2d-126">Per disabilitare temporaneamente un account utente, impostare il valore della proprietà Enabled su false ($False).</span><span class="sxs-lookup"><span data-stu-id="0dc2d-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="0dc2d-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0dc2d-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="0dc2d-128">Per riattivare un account utente</span><span class="sxs-lookup"><span data-stu-id="0dc2d-128">To re-enable a user account</span></span>

  - <span data-ttu-id="0dc2d-129">Per riattivare un account utente disabilitato, impostare il valore della proprietà Enabled su true ($True).</span><span class="sxs-lookup"><span data-stu-id="0dc2d-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="0dc2d-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0dc2d-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="0dc2d-131">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="0dc2d-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0dc2d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dc2d-132">See Also</span></span>


[<span data-ttu-id="0dc2d-133">Aggiungere e abilitare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dc2d-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="0dc2d-134">Abilitazione e disabilitazione degli utenti per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dc2d-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

