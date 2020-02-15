---
title: 'Lync Server 2013: assegnare un criterio di dial plan per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ea17e772bd98501b0d50674a2b82a9abb0e0b38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043708"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="286d0-102">Assegnare un criterio di dial plan per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="286d0-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="286d0-p101">Per completare la configurazione degli account per gli utenti di VoIP aziendale o per gli utenti delle conferenze telefoniche con accesso esterno, è necessario che all'utente sia assegnato un dial plan. Quando non si assegna esplicitamente un dial plan per utente esistente, gli account utente utilizzeranno automaticamente il dial plan globale oppure il dial plan a livello di sito, se disponibile. Se si desidera utilizzare il dial plan globale o il dial plan del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="286d0-p101">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan. User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan. If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="286d0-106">Per assegnare un dial plan tramite il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="286d0-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="286d0-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="286d0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="286d0-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="286d0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="286d0-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="286d0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="286d0-110">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="286d0-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="286d0-111">Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente che si desidera abilitare e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="286d0-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="286d0-112">Nella tabella fare clic sull'account utente a cui si desidera assegnare un dial plan.</span><span class="sxs-lookup"><span data-stu-id="286d0-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="286d0-113">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="286d0-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="286d0-114">Nella pagina **Modifica utente di Lync Server**, in **Telefonia**, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="286d0-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="286d0-115">Fare clic su **Criteri dial plan** e quindi scegliere il dial plan desiderato.</span><span class="sxs-lookup"><span data-stu-id="286d0-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="286d0-116">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="286d0-116">Click **Commit**.</span></span>

<span data-ttu-id="286d0-117">Per informazioni dettagliate sulla configurazione dei dial plan, vedere l'argomento [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="286d0-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="286d0-118">Assegnare un dial plan per utente utilizzando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="286d0-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="286d0-119">È possibile assegnare dial plan per utente con Windows PowerShell e il cmdlet **Grant-CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="286d0-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="286d0-120">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="286d0-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="286d0-121">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="286d0-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="286d0-122">Per assegnare un dial plan per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="286d0-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="286d0-123">Il comando seguente assegna il dial plan per utente RedmondDialPlan all'utente Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="286d0-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="286d0-124">Per assegnare un dial plan per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="286d0-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="286d0-125">Questo comando assegna il dial plan per utente RedmondDialPlan a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="286d0-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="286d0-126">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="286d0-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="286d0-127">Per annullare l'assegnazione di un dial plan per utente</span><span class="sxs-lookup"><span data-stu-id="286d0-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="286d0-p105">Il comando seguente annulla l'assegnazione di qualsiasi dial plan per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione del dial plan per utente, Ken Myer verrà gestito automaticamente mediante il dial plan globale, il dial plan del sito locale (se esistente) o il dial plan dell'ambito del servizio assegnato alla funzione di registrazione o al gateway PSTN. Un dial plan dell'ambito del servizio ha la precedenza su qualsiasi dial plan del sito, mentre un dial plan del sito ha la precedenza sul dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="286d0-p105">The following command unassigns any per-user dial plan previously assigned to Ken Myer. After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway. A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="286d0-131">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="286d0-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="286d0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="286d0-132">See Also</span></span>


[<span data-ttu-id="286d0-133">Configurazione di dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="286d0-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="286d0-134">Account utente abilitati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="286d0-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

