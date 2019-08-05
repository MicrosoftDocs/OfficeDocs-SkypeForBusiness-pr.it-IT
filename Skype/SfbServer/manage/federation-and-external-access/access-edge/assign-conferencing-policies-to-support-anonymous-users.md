---
title: Assegnare i criteri di conferenza per supportare gli utenti anonimi
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puoi controllare chi può invitare utenti anonimi configurando un criterio di conferenza per supportare utenti anonimi e applicando i criteri di conferenza a utenti specifici.
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188900"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="3c8ae-103">Assegnare criteri di conferenza per supportare utenti anonimi in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3c8ae-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="3c8ae-104">Per impostazione predefinita, a tutti gli utenti viene impedito di invitare utenti anonimi a partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="3c8ae-105">Puoi controllare chi può invitare utenti anonimi configurando un criterio di conferenza per supportare utenti anonimi e applicando i criteri di conferenza a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="3c8ae-106">Per informazioni dettagliate su come configurare i criteri di conferenza per il supporto degli utenti anonimi, vedere [creare criteri di conferenza in Skype for Business Server](../../conferencing/create-policies.md) e [gestire la Federazione e l'accesso esterno a Skype for Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ae-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="3c8ae-107">Usare la procedura descritta in questa sezione per applicare un criterio di conferenza già creato a uno o più utenti o gruppi di utente.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="3c8ae-108">Oltre a configurare e applicare un criterio per consentire agli utenti di invitare utenti anonimi, è anche necessario abilitare il supporto per gli utenti anonimi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="3c8ae-109">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ae-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="3c8ae-110">Per configurare un criterio utente per la partecipazione anonima alle riunioni</span><span class="sxs-lookup"><span data-stu-id="3c8ae-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="3c8ae-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3c8ae-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3c8ae-113">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c8ae-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="3c8ae-114">Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="3c8ae-115">Creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableAnonymous** per un criterio utente che consente la comunicazione con utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="3c8ae-116">Per configurare un criterio utente esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="3c8ae-117">Nella finestra di dialogo **criteri di conferenza** selezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** .</span><span class="sxs-lookup"><span data-stu-id="3c8ae-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="3c8ae-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="3c8ae-119">Nella barra di spostamento sinistra fare clic su **utenti**, cercare nell'account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="3c8ae-120">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="3c8ae-121">In **modifica utenti di Skype for Business Server** in **criteri di conferenza**Selezionare il criterio utente con la configurazione di accesso utente anonima che si vuole applicare a questo utente.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="3c8ae-122">Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="3c8ae-123">Per consentire agli utenti di invitare utenti anonimi alle conferenze, è anche necessario abilitare il supporto per gli utenti anonimi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="3c8ae-124">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3c8ae-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

