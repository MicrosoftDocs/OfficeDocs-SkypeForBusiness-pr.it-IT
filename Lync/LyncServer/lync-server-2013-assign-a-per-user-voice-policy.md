---
title: 'Lync Server 2013: assegnare un criterio vocale per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e74bebc202a9e8d9fbc7b925c14bbe030e4c577
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975990"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="1e0b0-102">Assegnare un criterio vocale per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e0b0-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="1e0b0-103">I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente di Lync Server 2013 abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="1e0b0-104">È anche possibile assegnare criteri vocali a utenti specifici tramite il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="1e0b0-105">Usare le procedure descritte in questo argomento per assegnare esplicitamente i criteri per utente agli utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="1e0b0-106">Per assegnare un criterio vocale specifico dell'utente tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="1e0b0-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1e0b0-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1e0b0-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1e0b0-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1e0b0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1e0b0-110">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="1e0b0-111">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1e0b0-112">In **modifica utenti di Lync Server** in **criteri vocali**Selezionare il criterio utente che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1e0b0-113">Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni predefinite del server o dei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1e0b0-114">Assegnazione di un criterio vocale per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e0b0-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1e0b0-115">È possibile assegnare criteri vocali per utente tramite Windows PowerShell e il cmdlet **Grant-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="1e0b0-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="1e0b0-116">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1e0b0-117">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="1e0b0-118">Per assegnare un criterio vocale per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="1e0b0-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="1e0b0-119">Con il comando seguente viene assegnato il criterio vocale per utente RedmondVoicePolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="1e0b0-120">Per assegnare un criterio vocale per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="1e0b0-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="1e0b0-121">Questo comando assegna il criterio vocale per utente FinanceVoicePolicy a tutti gli utenti che hanno account nell'unità organizzativa Finanza in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="1e0b0-122">Per altre informazioni sul parametro OU usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="1e0b0-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="1e0b0-123">Per annullare l'assegnazione di un criterio vocale per utente</span><span class="sxs-lookup"><span data-stu-id="1e0b0-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="1e0b0-124">Il comando seguente annulla l'assegnazione di qualsiasi criterio vocale per utente assegnato in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="1e0b0-125">Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="1e0b0-126">Un criterio di sito ha la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="1e0b0-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="1e0b0-127">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="1e0b0-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e0b0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e0b0-128">See Also</span></span>


[<span data-ttu-id="1e0b0-129">Disabilitare un utente per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e0b0-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="1e0b0-130">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="1e0b0-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

