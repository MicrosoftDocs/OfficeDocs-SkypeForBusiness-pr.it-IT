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
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203839"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="45dd5-103">Bloccare l'accesso a SharePoint per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="45dd5-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="45dd5-104">Applicando i criteri di accesso condizionale in SharePoint in Microsoft 365, verranno applicati anche a Teams.</span><span class="sxs-lookup"><span data-stu-id="45dd5-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="45dd5-105">Alcune organizzazioni, tuttavia, desiderano bloccare l'accesso ai file di SharePoint (caricare, scaricare, visualizzare, modificare, creare), ma consentono ai dipendenti di usare Teams desktop, per dispositivi mobili e Web su dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="45dd5-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="45dd5-106">In base alle regole dei criteri CA, il blocco di SharePoint porterebbe anche al blocco di Teams.</span><span class="sxs-lookup"><span data-stu-id="45dd5-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="45dd5-107">Questo articolo spiega come ovviare a questa limitazione e consente ai dipendenti di continuare a usare Teams bloccando al contempo l'accesso ai file archiviati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="45dd5-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="45dd5-108">Il blocco o la limitazione dell'accesso su dispositivi non gestiti si basa sui criteri di accesso condizionale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="45dd5-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="45dd5-109">Informazioni sulla [Licenza Azure AD](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="45dd5-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="45dd5-110">Per una panoramica sull'accesso condizionale in Azure AD, vedere [Accesso condizionale in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="45dd5-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="45dd5-111">Per informazioni sui criteri di accesso consigliati di SharePoint Online, vedere [Suggerimenti sui criteri per la protezione di siti e file di SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="45dd5-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="45dd5-112">Se si limita l'accesso sui dispositivi non gestiti, anche gli utenti di dispositivi gestiti sono tenuti a usare una delle [combinazioni di sistema operativo e browser](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), o avranno un accesso limitato.</span><span class="sxs-lookup"><span data-stu-id="45dd5-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="45dd5-113">È possibile bloccare o limitare l'accesso per:</span><span class="sxs-lookup"><span data-stu-id="45dd5-113">You can block or limit access for:</span></span>

- <span data-ttu-id="45dd5-114">Gli utenti dell'organizzazione o solo per alcuni utenti o gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="45dd5-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="45dd5-115">Tutti i siti dell'organizzazione o solo alcuni siti.</span><span class="sxs-lookup"><span data-stu-id="45dd5-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="45dd5-116">Una volta bloccato l'accesso, gli utenti vedranno un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="45dd5-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="45dd5-117">Il blocco dell'accesso consente di garantire la sicurezza e di proteggere i dati.</span><span class="sxs-lookup"><span data-stu-id="45dd5-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="45dd5-118">Una volta bloccato l'accesso, gli utenti vedranno un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="45dd5-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="45dd5-119">Aprire l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="45dd5-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="45dd5-120">Espandere i **Criteri** > **Criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="45dd5-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="45dd5-121">Nella sezione **Dispositivi non gestiti**, selezionare **Blocca accesso** e seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="45dd5-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![sezione Dispositivi non gestiti per i Criteri](media/no-sharepoint-access1.png)

4. <span data-ttu-id="45dd5-123">Aprire il portale [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e passare a **Criteri di accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="45dd5-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="45dd5-124">Verrà visualizzato un criterio creato da SharePoint simile a questo esempio:</span><span class="sxs-lookup"><span data-stu-id="45dd5-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![un nuovo criterio denominato Usa restrizioni imposte dalle app per l'accesso al browser](media/no-sharepoint-access2.png)

5. <span data-ttu-id="45dd5-126">Aggiornare i criteri in modo che siano destinati solo a utenti specifici o a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="45dd5-126">Update the policy to target only specific users or a group.</span></span>

    ![interfaccia di amministrazione di SharePoint con la sezione Selezionare utente evidenziata.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="45dd5-128">L'impostazione di questo criterio ridurrà l'accesso al portale di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="45dd5-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="45dd5-129">È consigliabile configurare i criteri di esclusione e selezionare gli amministratori globali e di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="45dd5-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="45dd5-130">Verificare che l'opzione solo SharePoint sia selezionata come app cloud di destinazione</span><span class="sxs-lookup"><span data-stu-id="45dd5-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![SharePoint è selezionato come app di destinazione.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="45dd5-132">Aggiornare le **Condizioni** per includere anche i client desktop.</span><span class="sxs-lookup"><span data-stu-id="45dd5-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![applicazioni desktop e per dispositivi mobili evidenziate.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="45dd5-134">Verificare che l'opzione **Concedi accesso** sia abilitata</span><span class="sxs-lookup"><span data-stu-id="45dd5-134">Make sure that **Grant access** is enabled</span></span>

    ![concedi accesso è abilitato.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="45dd5-136">Verificare che **Usa restrizioni imposte dalle app** sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="45dd5-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="45dd5-137">Attivare i criteri e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="45dd5-137">Enable your policy and select **Save**.</span></span>

    ![Le restrizioni imposte dalle app sono abilitate.](media/no-sharepoint-access6.png)

<span data-ttu-id="45dd5-139">Per testare i criteri, è necessario disconnettersi da qualsiasi client, ad esempio l'app desktop Teams o il client di sincronizzazione di OneDrive for Business ed eseguire di nuovo l'accesso per vedere il criterio funzionante.</span><span class="sxs-lookup"><span data-stu-id="45dd5-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="45dd5-140">Se l'accesso è stato bloccato, viene visualizzato un messaggio che indica che l'elemento potrebbe non esistere.</span><span class="sxs-lookup"><span data-stu-id="45dd5-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Messaggio elemento non trovato.](media/access-denied-sharepoint.png)

<span data-ttu-id="45dd5-142">In SharePoint viene visualizzato un messaggio di accesso negato.</span><span class="sxs-lookup"><span data-stu-id="45dd5-142">In Sharepoint, you'll receive an access denied message.</span></span>

![Messaggio di accesso negato.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="45dd5-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="45dd5-144">Related topics</span></span>

[<span data-ttu-id="45dd5-145">Controllare l'accesso per i dispositivi non gestiti in SharePoint</span><span class="sxs-lookup"><span data-stu-id="45dd5-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
