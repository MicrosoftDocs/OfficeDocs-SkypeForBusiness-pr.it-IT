---
title: Assegnare criteri di conferenza per supportare gli utenti anonimi
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: È possibile decidere chi può invitare utenti anonimi configurando un criterio di conferenza che li supporti e applicando tale criterio a utenti specifici.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817456"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="abe77-103">Assegnare criteri di conferenza per supportare gli utenti anonimi in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="abe77-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="abe77-104">Per impostazione predefinita, a tutti gli utenti è proibito invitare utenti anonimi a partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="abe77-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="abe77-105">È possibile decidere chi può invitare utenti anonimi configurando un criterio di conferenza che li supporti e applicando tale criterio a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="abe77-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="abe77-106">Per informazioni dettagliate su come configurare i criteri di conferenza per supportare gli utenti anonimi, vedere Creare criteri di conferenza [in Skype for Business Server](../../conferencing/create-policies.md) e Gestire la federazione e l'accesso esterno a Skype for Business [Server.](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="abe77-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="abe77-107">Utilizzare la procedura in questa sezione per applicare criteri di conferenza già creati a uno o più utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="abe77-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="abe77-108">Oltre alla configurazione e all'applicazione di criteri per consentire agli utenti di invitare utenti anonimi, è inoltre necessario abilitare il supporto degli utenti anonimi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abe77-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="abe77-109">Per informazioni dettagliate, vedere [Configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="abe77-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="abe77-110">Per configurare i criteri utente per la partecipazione anonima alle riunioni</span><span class="sxs-lookup"><span data-stu-id="abe77-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="abe77-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="abe77-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="abe77-112">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="abe77-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="abe77-113">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abe77-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="abe77-p103">Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. Creare un nome univoco nel campo **Nome** che indichi lo scopo dei criteri, ad esempio **AbilitaAnonimi** per criteri utente per l'abilitazione delle comunicazioni per gli utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="abe77-p103">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="abe77-116">Per configurare criteri utente esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="abe77-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="abe77-117">Nella finestra di dialogo **Criteri conferenza** selezionare la casella di controllo **Consenti ai partecipanti di invitare utenti anonimi**.</span><span class="sxs-lookup"><span data-stu-id="abe77-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="abe77-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="abe77-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="abe77-119">Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="abe77-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="abe77-120">Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="abe77-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="abe77-121">In **Modifica utente di Skype for Business Server** in Criteri conferenza selezionare il criterio utente con la configurazione di accesso utente anonimo che si desidera applicare all'utente. </span><span class="sxs-lookup"><span data-stu-id="abe77-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="abe77-122">Le <STRONG> &lt; impostazioni automatiche &gt; </STRONG> applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="abe77-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="abe77-123">Per consentire agli utenti di invitare utenti anonimi alle conferenze, è inoltre necessario abilitare il supporto per gli utenti anonimi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abe77-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="abe77-124">Per informazioni dettagliate, vedere [Configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="abe77-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

