---
title: 'Lync Server 2013: spostare gli utenti in un altro pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d2702e744fbadc5d51ea42095d7bd3d60f6f010
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="8ad56-102">Spostare gli utenti in un altro pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ad56-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8ad56-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8ad56-103">

<span> </span></span></span>

<span data-ttu-id="8ad56-104">_**Ultimo argomento modificato:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="8ad56-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="8ad56-105">È possibile utilizzare il pannello di controllo di Lync Server per assegnare gli utenti a un server o un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="8ad56-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8ad56-106">Lo spostamento di tutti gli utenti esistenti da un pool di origine che esegue Lync Server 2010 o versione precedente in un pool di destinazione di Lync Server 2013 in un ambiente di Active Directory complesso potrebbe provocare una replica di Active Directory più lenta.</span><span class="sxs-lookup"><span data-stu-id="8ad56-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="8ad56-107">Per evitare questo, è possibile utilizzare i filtri di ricerca per spostare gli utenti da pool che eseguono Lync Server 2010 o versioni precedenti separatamente oppure è possibile utilizzare Lync Server Management Shell per spostare gli utenti con i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8ad56-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="8ad56-108">Inoltre, la funzionalità del filtro è compatibile con gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad56-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="8ad56-109">Per spostare un gruppo selezionato di utenti in un server o un pool diverso</span><span class="sxs-lookup"><span data-stu-id="8ad56-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="8ad56-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8ad56-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ad56-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ad56-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8ad56-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8ad56-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8ad56-113">Nella barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8ad56-114">Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier (URI) di linea dell'account utente desiderato e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="8ad56-115">Nell'elenco della tabella selezionare uno o più utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="8ad56-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="8ad56-116">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="8ad56-117">In **Sposta utenti** selezionare il pool in cui spostare gli utenti in **Pool di registrazione di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="8ad56-118">(Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="8ad56-119">Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="8ad56-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="8ad56-120">Per spostare tutti gli utenti da un server o un pool a un server o un pool diverso</span><span class="sxs-lookup"><span data-stu-id="8ad56-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="8ad56-121">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8ad56-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ad56-122">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ad56-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8ad56-123">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8ad56-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8ad56-124">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8ad56-125">Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="8ad56-126">In **Sposta utenti** selezionare in **Pool di registrazione di origine** il pool contenente gli account utente che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="8ad56-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="8ad56-127">In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8ad56-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="8ad56-128">(Facoltativo) Se il server o pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="8ad56-129">Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="8ad56-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="8ad56-130">Per spostare gli utenti da un pool a un altro mediante un filtro</span><span class="sxs-lookup"><span data-stu-id="8ad56-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="8ad56-131">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8ad56-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ad56-132">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ad56-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8ad56-133">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8ad56-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8ad56-134">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8ad56-135">In **ricerca utente**fare clic su **Cerca**e quindi su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="8ad56-136">Nei criteri di ricerca selezionare **Pool di registrazione**, **Uguale a**, **FQDN pool** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="8ad56-137">Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ad56-138">Quando un filtro viene applicato a un set di utenti esistente, l'opzione <STRONG>Sposta tutti gli utenti nel pool</STRONG> si trova nel contesto del sottoinsieme filtrato di utenti, non di <STRONG><EM>tutti</EM></STRONG> gli utenti possibili.</span><span class="sxs-lookup"><span data-stu-id="8ad56-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="8ad56-139">In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="8ad56-140">In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8ad56-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="8ad56-141">(Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="8ad56-142">Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="8ad56-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="8ad56-143">Per spostare gli utenti da un pool a un altro utilizzando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ad56-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="8ad56-144">A seconda di come vengono eseguiti i comandi di Windows PowerShell, ovvero localmente o in remoto, è necessario eseguire l'accesso come membri dei ruoli amministrativi di Lync Server 2013 corretti come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ad56-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="8ad56-145">Se si eseguono i comandi nel computer locale, ad esempio si esegue l'accesso direttamente a un front end server, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8ad56-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="8ad56-146">Se si eseguono i comandi in remoto in un altro computer (ad esempio, si accede al computer e si eseguono i comandi in remoto in un front end server Standard Edition): da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator ruolo, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8ad56-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ad56-147">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8ad56-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8ad56-148">Per spostare singoli utenti, utilizzare il cmdlet Move-CsUser come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ad56-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="8ad56-149">Dove l'utente da spostare si chiama Luisa Cazzaniga e verrà spostato dal pool principale assegnato al pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8ad56-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="8ad56-150">Per spostare un numero elevato di utenti, utilizzare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultanti a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="8ad56-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="8ad56-151">La combinazione dei comandi di **Get-CsUser** e **Move-CsUser** può generare questo risultato:</span><span class="sxs-lookup"><span data-stu-id="8ad56-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ad56-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ad56-152">See Also</span></span>


[<span data-ttu-id="8ad56-153">Modifica delle proprietà degli account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ad56-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="8ad56-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8ad56-154"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

