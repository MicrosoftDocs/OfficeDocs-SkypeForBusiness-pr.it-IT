---
title: 'Lync Server 2013: assegnare un criterio di accesso utente esterno a un utente abilitato per Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612b872e0071e2ad3fa2d4d064048805a4e65953
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="26a00-102">Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26a00-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26a00-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="26a00-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="26a00-104">Se un utente è stato abilitato per Lync Server, è possibile configurare la federazione SIP, la Federazione XMPP, l'accesso degli utenti remoti e la connettività per la messaggistica istantanea pubblica nel pannello di controllo di Lync Server applicando i criteri corretti a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="26a00-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="26a00-105">Ad esempio, se è stato creato un criterio per supportare l'accesso degli utenti remoti, è necessario applicarlo all'utente prima che l'utente possa connettersi a Lync Server da una posizione remota e collaborare con utenti interni dalla postazione remota.</span><span class="sxs-lookup"><span data-stu-id="26a00-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26a00-106">Per supportare l'accesso utente esterno, è necessario abilitare il supporto per ogni tipo di accesso utente esterno desiderato e configurare i criteri appropriati e altre opzioni per il controllo.</span><span class="sxs-lookup"><span data-stu-id="26a00-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="26a00-107">Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-support-for-external-user-access.md">configurazione del supporto per l'accesso degli utenti esterni in Lync server 2013</A> nella documentazione relativa alla distribuzione o <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">gestione della Federazione e dell'accesso esterno a Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="26a00-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="26a00-108">Utilizzare la procedura contenuta in questo argomento per applicare criteri di accesso utente esterno creati in precedenza a uno o più account utente.</span><span class="sxs-lookup"><span data-stu-id="26a00-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="26a00-109">Per applicare criteri di accesso utente esterno a un account utente</span><span class="sxs-lookup"><span data-stu-id="26a00-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="26a00-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="26a00-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="26a00-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="26a00-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="26a00-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26a00-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="26a00-113">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="26a00-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="26a00-114">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="26a00-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="26a00-115">In **Criteri di accesso esterno** in **Modifica utente di Lync Server** selezionare i criteri utente che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="26a00-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26a00-116">Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni predefinite del server o dei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="26a00-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="26a00-117">Assegnazione dei criteri di accesso esterno per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26a00-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="26a00-118">I criteri di accesso esterno per utente possono essere assegnati utilizzando Windows PowerShell e il cmdlet Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="26a00-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="26a00-119">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26a00-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="26a00-120">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="26a00-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="26a00-121">Per assegnare un criterio di accesso esterno per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="26a00-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="26a00-122">Questo comando assegna il criterio di accesso esterno per utente RedmondExternalAccessPolicy all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="26a00-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="26a00-123">Per assegnare criteri di accesso esterno per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="26a00-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="26a00-124">Questo comando assegna il criterio di accesso esterno per utente USAExternalAccessPolicy a tutti gli utenti che dispongono di account nell'unità organizzativa UnitedStates in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="26a00-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="26a00-125">Per ulteriori informazioni sul parametro OU utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="26a00-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="26a00-126">Per annullare l'assegnazione di un criterio di accesso esterno per utente</span><span class="sxs-lookup"><span data-stu-id="26a00-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="26a00-p106">Questo comando annulla l'assegnazione di tutti i criteri di accesso esterno per utente precedentemente assegnati a Ken Myer. Dopo l'annullamento del criterio per utente, Ken Myer sarà gestito automaticamente dal criterio globale oppure dall'eventuale criterio del sito locale, che ha la precedenza sul criterio globale.</span><span class="sxs-lookup"><span data-stu-id="26a00-p106">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="26a00-130">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="26a00-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

