---
title: Bloccare l'accesso a SharePoint per utenti specifici
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come bloccare l'accesso a SharePoint per utenti specifici
ms.openlocfilehash: a2cfdb938dc11d38303df59061db1c46e5b08fcc
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135930"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="2dc5a-103">Bloccare l'accesso a SharePoint per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="2dc5a-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="2dc5a-104">L'applicazione di qualsiasi criterio di accesso condizionale in SharePoint in Microsoft 365 viene applicata anche ai team.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="2dc5a-105">Alcune organizzazioni vogliono tuttavia bloccare l'accesso ai file di SharePoint (caricare, scaricare, visualizzare, modificare, creare) ma consentire ai dipendenti di usare i client desktop, mobili e Web Teams nei dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="2dc5a-106">In base alle regole dei criteri della CA, il blocco di SharePoint porterebbe anche a bloccare teams.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="2dc5a-107">In questo articolo viene spiegato come aggirare questa limitazione e consentire ai dipendenti di continuare a usare teams bloccando completamente l'accesso ai file archiviati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="2dc5a-108">Il blocco o la limitazione dell'accesso ai dispositivi non gestiti si basa sui criteri di accesso condizionale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="2dc5a-109">Informazioni sulle [licenze di Azure ad](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="2dc5a-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="2dc5a-110">Per una panoramica dell'accesso condizionale in Azure AD, vedere [accesso condizionale in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="2dc5a-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="2dc5a-111">Per informazioni sui criteri di accesso di SharePoint Online consigliati, vedere [Suggerimenti per proteggere i file e i siti di SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="2dc5a-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="2dc5a-112">Se si limita l'accesso nei dispositivi non gestiti, gli utenti dei dispositivi gestiti devono usare una delle [combinazioni di sistema operativo e browser supportate](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)o avranno anche accesso limitato.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="2dc5a-113">È possibile bloccare o limitare l'accesso per:</span><span class="sxs-lookup"><span data-stu-id="2dc5a-113">You can block or limit access for:</span></span>

- <span data-ttu-id="2dc5a-114">Utenti dell'organizzazione o solo di alcuni utenti o gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="2dc5a-115">Tutti i siti dell'organizzazione o solo alcuni siti.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="2dc5a-116">Quando Access è bloccato, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="2dc5a-117">Il blocco di Access consente di garantire sicurezza e proteggere i dati sicuri.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="2dc5a-118">Quando Access è bloccato, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="2dc5a-119">Aprire l'interfaccia di [Amministrazione](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-119">Open the SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span></span>

2. <span data-ttu-id="2dc5a-120">Espandere **Policies**criteri di  >  **accesso ai**criteri.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="2dc5a-121">Nella sezione **dispositivi non gestiti** selezionare **Blocca accesso** e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![sezione dispositivi non gestiti per i criteri](media/no-sharepoint-access1.png)

4. <span data-ttu-id="2dc5a-123">Aprire il portale di [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e passare a **criteri di accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="2dc5a-124">Verrà visualizzato un nuovo criterio creato da SharePoint simile a questo esempio:</span><span class="sxs-lookup"><span data-stu-id="2dc5a-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![un nuovo criterio denominato USA restrizioni applicate dall'app per l'accesso al browser](media/no-sharepoint-access2.png)

5. <span data-ttu-id="2dc5a-126">Aggiornare i criteri per destinare solo utenti specifici o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-126">Update the policy to target only specific users or a group.</span></span>

    ![interfaccia di amministrazione di SharePoint con la sezione selezionare l'utente evidenziata.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="2dc5a-128">L'impostazione di questo criterio consente di ridurre l'accesso al portale di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="2dc5a-129">È consigliabile configurare i criteri di esclusione e selezionare gli amministratori globali e di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="2dc5a-130">Verificare che solo SharePoint sia selezionato come app di destinazione cloud</span><span class="sxs-lookup"><span data-stu-id="2dc5a-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![SharePoint è selezionato come app di destinazione.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="2dc5a-132">Aggiornare **le condizioni** per includere anche i client desktop.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![app per desktop e dispositivi mobili evidenziate.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="2dc5a-134">Verificare che **l'autorizzazione di accesso** sia abilitata</span><span class="sxs-lookup"><span data-stu-id="2dc5a-134">Make sure that **Grant access** is enabled</span></span>

    ![concedere l'accesso è abilitato.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="2dc5a-136">Verificare che sia abilitata l' **uso delle restrizioni applicate all'app** .</span><span class="sxs-lookup"><span data-stu-id="2dc5a-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="2dc5a-137">Abilitare i criteri e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-137">Enable your policy and select **Save**.</span></span>

    ![Le restrizioni applicate all'app sono abilitate.](media/no-sharepoint-access6.png)

<span data-ttu-id="2dc5a-139">Per testare i criteri, è necessario disconnettersi da qualsiasi client, ad esempio l'app desktop teams o il client di sincronizzazione di OneDrive for business, e accedere di nuovo per vedere il criterio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="2dc5a-140">Se l'accesso è stato bloccato, viene visualizzato un messaggio in teams che indica che l'elemento potrebbe non esistere.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Messaggio dell'elemento non trovato.](media/access-denied-sharepoint.png)

<span data-ttu-id="2dc5a-142">In SharePoint si riceverà un messaggio di Access denied.</span><span class="sxs-lookup"><span data-stu-id="2dc5a-142">In Sharepoint, you'll receive an access denied message.</span></span>

![Messaggio di Access denied.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="2dc5a-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2dc5a-144">Related topics</span></span>

[<span data-ttu-id="2dc5a-145">Controllare l'accesso per i dispositivi non gestiti in SharePoint</span><span class="sxs-lookup"><span data-stu-id="2dc5a-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
