---
title: 'Lync Server 2013: trasferire gli utenti in un altro pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb716c0b551475a53cacf09be10ffdc039f5db8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="3bf94-102">Trasferire utenti in un altro pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bf94-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3bf94-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3bf94-103"></span></span>

<span data-ttu-id="3bf94-104">_**Argomento Ultima modifica:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="3bf94-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="3bf94-105">È possibile usare il pannello di controllo di Lync Server per assegnare gli utenti a un server o un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="3bf94-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="3bf94-106">Lo spostamento di tutti gli utenti esistenti da un pool di origine che utilizza Lync Server 2010 o versioni precedenti in un pool di destinazione di Lync Server 2013 in un ambiente di Active Directory complesso può causare una replica di Active Directory più lenta.</span><span class="sxs-lookup"><span data-stu-id="3bf94-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="3bf94-107">Per evitare questo problema, è possibile usare i filtri di ricerca per trasferire gli utenti da pool che esegue Lync Server 2010 o versioni precedenti separatamente oppure è possibile usare Lync Server Management Shell per trasferire gli utenti con i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bf94-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="3bf94-108">Inoltre, la funzionalità di filtro funziona con gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bf94-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="3bf94-109">Per trasferire gli utenti selezionati in un altro server o pool</span><span class="sxs-lookup"><span data-stu-id="3bf94-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="3bf94-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3bf94-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3bf94-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3bf94-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3bf94-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3bf94-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3bf94-113">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3bf94-114">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente desiderato, quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="3bf94-115">Nella tabella selezionare un utente o utenti specifici nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3bf94-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="3bf94-116">Nel menu **azione** fare clic su **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="3bf94-117">In **Move users**selezionare il pool in cui si vuole trasferire gli utenti nel **pool di registrar di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="3bf94-118">Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .</span><span class="sxs-lookup"><span data-stu-id="3bf94-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="3bf94-119">Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="3bf94-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="3bf94-120">Per trasferire tutti gli utenti da un server o da un pool a un altro server o pool</span><span class="sxs-lookup"><span data-stu-id="3bf94-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="3bf94-121">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3bf94-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3bf94-122">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3bf94-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3bf94-123">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3bf94-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3bf94-124">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3bf94-125">Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="3bf94-126">In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="3bf94-127">Nel **pool di registrar di destinazione**selezionare il pool a cui si vuole trasferire gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3bf94-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="3bf94-128">Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .</span><span class="sxs-lookup"><span data-stu-id="3bf94-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="3bf94-129">Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="3bf94-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="3bf94-130">Per trasferire gli utenti da un pool a un altro tramite un filtro</span><span class="sxs-lookup"><span data-stu-id="3bf94-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="3bf94-131">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3bf94-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3bf94-132">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3bf94-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3bf94-133">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3bf94-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3bf94-134">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3bf94-135">In **ricerca utente**fare clic su **Cerca**e quindi su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="3bf94-136">Nel criterio di ricerca selezionare **pool di registrazione**, selezionare **uguale a**, selezionare **FQDN corrente del pool**e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="3bf94-137">Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3bf94-138">Quando si applica un filtro a un set di utenti esistente, l'opzione <STRONG>trasferisce tutti gli utenti al pool</STRONG> si trova nel contesto del sottoinsieme filtrato degli utenti, non di <STRONG><EM>tutti</EM></STRONG> gli utenti possibili.</span><span class="sxs-lookup"><span data-stu-id="3bf94-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="3bf94-139">In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="3bf94-140">Nel **pool di registrar di destinazione**selezionare il pool in cui si desidera trasferire gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3bf94-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="3bf94-141">Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .</span><span class="sxs-lookup"><span data-stu-id="3bf94-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="3bf94-142">Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="3bf94-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="3bf94-143">Per trasferire gli utenti da un pool a un altro usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bf94-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="3bf94-144">A seconda del modo in cui vengono eseguiti i comandi di Windows PowerShell, ovvero localmente o in remoto, è necessario accedere come membro dei ruoli amministrativi corretti di Lync Server 2013, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3bf94-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="3bf94-145">Se si esegue i comandi nel computer locale, ad esempio si accede direttamente a un server front-end, accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [autorizzazioni di configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3bf94-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="3bf94-146">Se si eseguono i comandi in remoto in un altro computer, ad esempio si accede al computer e si eseguono i comandi in remoto in un server front-end Standard Edition: da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator ruolo, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3bf94-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3bf94-147">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3bf94-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3bf94-148">Per trasferire singoli utenti, usare il cmdlet Move-CsUser come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3bf94-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="3bf94-149">Dove l'utente deve spostarsi è l'utente Pilar Ackerman e l'utente verrà spostato dal proprio pool di Home attualmente assegnato al pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3bf94-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="3bf94-150">Per trasferire un numero elevato di utenti, usare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultante a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="3bf94-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="3bf94-151">I comandi combinati di **Get-CsUser** e **Move-CsUser** possono risultare in questo:</span><span class="sxs-lookup"><span data-stu-id="3bf94-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3bf94-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bf94-152">See Also</span></span>


[<span data-ttu-id="3bf94-153">Modifica delle proprietà dell'account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bf94-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="3bf94-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3bf94-154"></span></span></div>

