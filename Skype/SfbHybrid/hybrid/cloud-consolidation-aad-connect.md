---
title: Aggiornare AAD Connect per includere più di una foresta
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include la procedura dettagliata per aggiornare AAD Connect per includere più foreste come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049098"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="cae88-103">Aggiornare AAD Connect per includere più di una foresta</span><span class="sxs-lookup"><span data-stu-id="cae88-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="cae88-104">Azure AD Connect supporta la [sincronizzazione da più foreste.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies)</span><span class="sxs-lookup"><span data-stu-id="cae88-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="cae88-105">Tuttavia, supporta una sola istanza di Azure AD Connect che esegue la sincronizzazione con AAD.</span><span class="sxs-lookup"><span data-stu-id="cae88-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="cae88-106">Pertanto, nei casi in cui Azure AD è già installato in una foresta, l'istanza esistente di AAD Connect deve essere aggiornata per la sincronizzazione dalla foresta aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="cae88-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="cae88-107">Se tutte le identità sono rappresentate una sola volta in entrambe le foreste (ovvero non sono stati effettuati contatti abilitati alla posta elettronica),  è sufficiente eseguire di nuovo la procedura guidata AAD Connect, scegliere "Personalizza opzioni di sincronizzazione" e quindi nella pagina Connetti directory immettere il nome della foresta e delle identità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="cae88-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="cae88-108">![Pagina Connetti le directory](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="cae88-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="cae88-109">Tuttavia, se gli utenti possono esistere in più directory e si uniranno i dati (ad esempio, se gli oggetti contatto esistono in una foresta corrispondente agli utenti di un'altra foresta), sarà necessario disinstallare Azure AD Connect e reinstallarlo.</span><span class="sxs-lookup"><span data-stu-id="cae88-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="cae88-110">Questo perché la condizione delle regole di join tra foreste può essere configurata solo durante la prima installazione.</span><span class="sxs-lookup"><span data-stu-id="cae88-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="cae88-111">Questa operazione viene eseguita nella pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="cae88-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="cae88-112">![Pagina Identificazione univoca degli utenti](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="cae88-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="cae88-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cae88-113">See also</span></span>

[<span data-ttu-id="cae88-114">Consolidamento del cloud per Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cae88-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)