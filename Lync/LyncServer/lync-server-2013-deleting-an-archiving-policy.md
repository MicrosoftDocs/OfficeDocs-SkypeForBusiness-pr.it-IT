---
title: 'Lync Server 2013: eliminazione di un criterio di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bde8694cb5249cd5c284bfadc89d9784ca76ac31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="4740b-102">Eliminazione di un criterio di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4740b-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4740b-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4740b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4740b-104">È possibile eliminare un criterio utente o un criterio sito.</span><span class="sxs-lookup"><span data-stu-id="4740b-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="4740b-105">Non è possibile rimuovere i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="4740b-105">The global policy cannot be removed.</span></span> <span data-ttu-id="4740b-106">Se si tenta di eliminare il criterio globale, Lync Server 2013 Reimposta automaticamente il criterio sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4740b-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4740b-107">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono conservate sul posto.</span><span class="sxs-lookup"><span data-stu-id="4740b-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="4740b-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4740b-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="4740b-109">Per eliminare un criterio utente o sito per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="4740b-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="4740b-110">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4740b-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4740b-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4740b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4740b-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4740b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4740b-113">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="4740b-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="4740b-114">Nell'elenco dei criteri di archiviazione fare clic sul criterio utente o sito che si desidera eliminare, su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4740b-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="4740b-115">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4740b-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4740b-116">Rimozione dei criteri di archiviazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4740b-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4740b-117">I criteri di archiviazione possono essere eliminati utilizzando Windows PowerShell e il cmdlet **Remove-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="4740b-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="4740b-118">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4740b-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4740b-119">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="4740b-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="4740b-120">Per rimuovere un criterio di archiviazione specificato</span><span class="sxs-lookup"><span data-stu-id="4740b-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="4740b-p105">Ad esempio,**Remove-CsArchivingPolicy** elimina il criterio con identità site:Redmond. Si noti che, quando viene eliminato un criterio configurato nell'ambito del sito, gli utenti precedentemente gestiti da quel criterio verranno automaticamente controllati dal criterio di archiviazione globale. Il comando seguente rimuove l'archiviazione applicata al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="4740b-p105">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead. The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="4740b-124">Per rimuovere tutti i criteri di archiviazione applicati all'ambito per utente</span><span class="sxs-lookup"><span data-stu-id="4740b-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="4740b-125">Questo comando rimuove tutti i criteri di archiviazione applicati all'ambito per utente:</span><span class="sxs-lookup"><span data-stu-id="4740b-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="4740b-126">Per rimuovere tutti i criteri di archiviazione che disabilitano l'archiviazione interna</span><span class="sxs-lookup"><span data-stu-id="4740b-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="4740b-127">Questo comando rimuove tutti i criteri di archiviazione in cui è stata disabilitata l'archiviazione interna:</span><span class="sxs-lookup"><span data-stu-id="4740b-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="4740b-128">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="4740b-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4740b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4740b-129">See Also</span></span>


[<span data-ttu-id="4740b-130">Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4740b-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

