---
title: 'Lync Server 2013: assegnare un criterio per il dial plan per utente'
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
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722966"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="c269b-102">Assegnare un criterio di dial plan per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c269b-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="c269b-103">Per completare la configurazione dell'account utente per gli utenti di VoIP aziendale o per gli utenti di servizi di conferenza telefonica con accesso esterno, l'utente deve essere assegnato a un dial plan.</span><span class="sxs-lookup"><span data-stu-id="c269b-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="c269b-104">Gli account utente utilizzeranno automaticamente il dial plan globale o, se disponibile, il dial plan a livello di sito quando non si assegna esplicitamente un dial plan per utente esistente.</span><span class="sxs-lookup"><span data-stu-id="c269b-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="c269b-105">Se si vuole usare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c269b-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="c269b-106">Per assegnare un dial plan tramite il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c269b-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="c269b-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c269b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c269b-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c269b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c269b-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c269b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c269b-110">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="c269b-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c269b-111">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="c269b-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="c269b-112">Nella tabella fare clic sull'account utente che si vuole assegnare a un dial plan.</span><span class="sxs-lookup"><span data-stu-id="c269b-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="c269b-113">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c269b-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="c269b-114">Nella pagina **modifica utente di Lync Server** , in **telefonia**, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="c269b-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="c269b-115">Fare clic su **Criteri dial plan**e quindi scegliere il dial plan desiderato.</span><span class="sxs-lookup"><span data-stu-id="c269b-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="c269b-116">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c269b-116">Click **Commit**.</span></span>

<span data-ttu-id="c269b-117">Per informazioni dettagliate sulla configurazione dei dial plan, vedere l'argomento [configurazione di dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="c269b-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c269b-118">Assegnare un dial plan per utente usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c269b-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c269b-119">È possibile assegnare piani di dial per utente con Windows PowerShell e il cmdlet **Grant-CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="c269b-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="c269b-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c269b-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c269b-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="c269b-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="c269b-122">Per assegnare un dial plan per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="c269b-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="c269b-123">Con il comando seguente viene assegnato il dial plan per utente "RedmondDialPlan" all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="c269b-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="c269b-124">Per assegnare un dial plan per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="c269b-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="c269b-125">Questo comando assegna il dial plan per utente "RedmondDialPlan" a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="c269b-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="c269b-126">Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="c269b-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="c269b-127">Per annullare l'assegnazione di un dial plan per utente</span><span class="sxs-lookup"><span data-stu-id="c269b-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="c269b-128">Il comando seguente annulla l'assegnazione di un dial plan per utente precedentemente assegnato a Ken.</span><span class="sxs-lookup"><span data-stu-id="c269b-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="c269b-129">Dopo la mancata assegnazione del dial plan per utente, Ken è gestito automaticamente tramite il dial plan globale, il dial plan locale (se presente) o il dial plan di servizio assegnato al proprio registrar o al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="c269b-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="c269b-130">Un dial plan per l'ambito dei servizi ha la precedenza su qualsiasi piano di dial-up del sito e il dial plan di un sito ha la precedenza sul dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="c269b-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="c269b-131">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="c269b-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="c269b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c269b-132">See Also</span></span>


[<span data-ttu-id="c269b-133">Configurazione dei dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c269b-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="c269b-134">Account utente abilitato per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c269b-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

