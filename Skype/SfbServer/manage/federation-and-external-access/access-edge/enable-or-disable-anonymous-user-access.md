---
title: Abilitare o disabilitare l'accesso utente anonimo
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 7e828745810bd49f9b8f3ea9e7bee1d023e4fc67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817446"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="9b259-102">Abilitazione o disabilitazione dell'accesso degli utenti anonimi in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9b259-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="9b259-103">Gli utenti anonimi sono utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma possono essere invitati a partecipare in remoto in una conferenza locale.</span><span class="sxs-lookup"><span data-stu-id="9b259-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="9b259-104">Consentendo la partecipazione anonima alle riunioni, si consente agli utenti anonimi, ovvero agli utenti la cui identità viene verificata solo mediante la chiave riunione o conferenza, di partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9b259-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="9b259-105">A tale scopo, è necessario abilitare la partecipazione anonima per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9b259-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="9b259-p102">Se successivamente si desidera impedire temporaneamente o definitivamente l'accesso da parte di utenti anonimi, è possibile disabilitarlo per l'organizzazione. Eseguire la procedura illustrata in questa sezione per abilitare o disabilitare l'accesso utente anonimo per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9b259-p102">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization. Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="9b259-108">Abilitando l'accesso utente anonimo per l'organizzazione, si specifica solo che i server che eseguono il servizio Access Edge supportano l'accesso da parte di utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="9b259-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="9b259-109">Tali utenti non possono partecipare alle riunioni dell'organizzazione finché non viene configurato e applicato almeno un criterio di conferenza a uno o più utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="9b259-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="9b259-110">Gli unici utenti che possono invitare utenti anonimi alle riunioni sono quelli a cui è stato assegnato il criterio di conferenza configurato per supportare l'invito di utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="9b259-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="9b259-111">Per informazioni dettagliate sulla configurazione dei criteri di conferenza per supportare invitare utenti anonimi, vedere [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9b259-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="9b259-112">Per abilitare o disabilitare l'accesso utente anonimo per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="9b259-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="9b259-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9b259-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b259-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9b259-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9b259-115">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="9b259-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="9b259-116">Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9b259-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9b259-117">In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b259-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="9b259-118">Per abilitare l'accesso utente anonimo per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.</span><span class="sxs-lookup"><span data-stu-id="9b259-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="9b259-119">Per disabilitare l'accesso utente anonimo per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.</span><span class="sxs-lookup"><span data-stu-id="9b259-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="9b259-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9b259-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9b259-121">Abilitazione o disabilitazione dell'accesso degli utenti anonimi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b259-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9b259-122">È possibile gestire l'accesso degli utenti anonimi utilizzando Windows PowerShell e il cmdlet **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9b259-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="9b259-123">È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b259-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="9b259-124">Per abilitare l'accesso degli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="9b259-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="9b259-125">Per abilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su True ($True):</span><span class="sxs-lookup"><span data-stu-id="9b259-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="9b259-126">Per disabilitare l'accesso degli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="9b259-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="9b259-127">Per disabilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su False ($False):</span><span class="sxs-lookup"><span data-stu-id="9b259-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="9b259-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b259-128">See Also</span></span>

[<span data-ttu-id="9b259-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="9b259-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
