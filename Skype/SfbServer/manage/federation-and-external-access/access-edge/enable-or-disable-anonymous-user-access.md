---
title: Abilitare o disabilitare l'accesso degli utenti anonimi
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188894"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="f111b-102">Abilitare o disabilitare l'accesso anonimo agli utenti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f111b-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="f111b-103">Gli utenti anonimi sono utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma possono essere invitati a partecipare in remoto in una conferenza locale.</span><span class="sxs-lookup"><span data-stu-id="f111b-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="f111b-104">Consentendo la partecipazione anonima alle riunioni, è possibile abilitare gli utenti anonimi, ovvero gli utenti la cui identità viene verificata solo tramite la riunione o la chiave di conferenza, per partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="f111b-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="f111b-105">Per consentire la partecipazione anonima, è necessario abilitarla per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f111b-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="f111b-106">Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso da parte di utenti anonimi, è possibile disabilitarlo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f111b-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="f111b-107">Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti anonimi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f111b-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="f111b-108">Abilitando l'accesso degli utenti anonimi per l'organizzazione, devi solo specificare che i server che esegue il servizio Access Edge supportano l'accesso da parte di utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="f111b-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="f111b-109">Gli utenti anonimi non possono partecipare a riunioni dell'organizzazione fino a quando non vengono configurati almeno un criterio di conferenza e lo si applicano a uno o più utenti o gruppi di utente.</span><span class="sxs-lookup"><span data-stu-id="f111b-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="f111b-110">Gli unici utenti che possono invitare utenti anonimi alle riunioni sono gli utenti a cui sono assegnati i criteri di conferenza configurati per il supporto degli utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="f111b-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="f111b-111">Per informazioni dettagliate sulla configurazione dei criteri di conferenza per supportare l'invito agli utenti anonimi, vedere [gestire i criteri di conferenza](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f111b-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="f111b-112">Per abilitare o disabilitare l'accesso degli utenti anonimi per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f111b-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="f111b-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f111b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f111b-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f111b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f111b-115">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="f111b-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f111b-116">Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f111b-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f111b-117">In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f111b-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="f111b-118">Per abilitare l'accesso degli utenti anonimi per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con utenti anonimi** .</span><span class="sxs-lookup"><span data-stu-id="f111b-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="f111b-119">Per disabilitare l'accesso degli utenti anonimi per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con utenti anonimi** .</span><span class="sxs-lookup"><span data-stu-id="f111b-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="f111b-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f111b-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f111b-121">Abilitazione o disabilitazione dell'accesso degli utenti anonimi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f111b-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f111b-122">Per gestire l'accesso degli utenti anonimi, è possibile usare Windows PowerShell e il cmdlet **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f111b-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="f111b-123">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f111b-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="f111b-124">Per abilitare l'accesso degli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="f111b-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="f111b-125">Per abilitare l'accesso degli utenti anonimi, imposta il valore della proprietà **AllowAnonymousUsers** su True ($true):</span><span class="sxs-lookup"><span data-stu-id="f111b-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="f111b-126">Per disabilitare l'accesso degli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="f111b-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="f111b-127">Per disabilitare l'accesso anonimo agli utenti, imposta il valore della proprietà **AllowAnonymousUsers** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="f111b-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="f111b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f111b-128">See Also</span></span>

[<span data-ttu-id="f111b-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="f111b-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
