---
title: 'Lync Server 2013: assegnare un criterio vocale per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943929"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="42d38-102">Assegnare un criterio vocale per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42d38-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="42d38-103">I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente di Lync Server 2013 abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="42d38-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="42d38-104">È inoltre possibile assegnare criteri vocali a utenti specifici utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="42d38-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="42d38-105">Utilizzare le procedure descritte in questo argomento per assegnare in modo esplicito i criteri per utente agli utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42d38-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="42d38-106">Per assegnare un criterio vocale specifico dell'utente utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="42d38-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="42d38-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="42d38-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="42d38-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42d38-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42d38-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="42d38-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42d38-110">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="42d38-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="42d38-111">Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="42d38-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="42d38-112">In **Modifica utente di Lync Server**, in **Criteri vocali**, selezionare i criteri utente da applicare.</span><span class="sxs-lookup"><span data-stu-id="42d38-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="42d38-113">Le impostazioni <STRONG> &lt; automatiche &gt; </STRONG> applicano le impostazioni predefinite del server o dei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="42d38-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="42d38-114">Assegnare criteri vocali per utente</span><span class="sxs-lookup"><span data-stu-id="42d38-114">Assign per-user voice policies</span></span>

<span data-ttu-id="42d38-115">È possibile assegnare criteri vocali per utente tramite Windows PowerShell e il cmdlet **Grant-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="42d38-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="42d38-116">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42d38-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="42d38-117">Per ulteriori informazioni sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere il post del Blog di Windows PowerShell di Lync Server: [Quick Start: Managing Microsoft Lync server 2010 using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="42d38-117">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="42d38-118">Assegnare un criterio vocale per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="42d38-118">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="42d38-119">Il comando seguente assegna il criterio vocale per utente RedmondVoicePolicy all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="42d38-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="42d38-120">Assegnazione di un criterio vocale per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="42d38-120">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="42d38-121">Questo comando assegnare il criterio vocale per utente FinanceVoicePolicy a tutti gli utenti con account nell'unità organizzativa Finance in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42d38-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="42d38-122">Per ulteriori informazioni sul parametro OU utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="42d38-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="42d38-123">Annullamento dell'assegnazione di un criterio vocale per utente</span><span class="sxs-lookup"><span data-stu-id="42d38-123">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="42d38-p105">Il comando seguente annulla l'assegnazione di qualsiasi criterio vocale per utente precedentemente assegnato a Ken Myer. Dopo aver annullato l'assegnazione del criterio vocale per utente, Ken Myer verrà automaticamente gestito mediante i criteri globali oppure, se esistente, i criteri a livello di sito locale. I criteri a livello di sito hanno precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="42d38-p105">The following command unassigns any per-user voice policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="42d38-127">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="42d38-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="42d38-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42d38-128">See Also</span></span>


[<span data-ttu-id="42d38-129">Disabilitare un utente per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42d38-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="42d38-130">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="42d38-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

