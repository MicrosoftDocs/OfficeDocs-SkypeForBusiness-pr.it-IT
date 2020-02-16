---
title: Update AAD Connect per includere più di una foresta
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
description: In questa appendice sono riportati i passaggi dettagliati per l'aggiornamento di AAD Connect per includere più foreste nell'ambito del consolidamento del cloud per i team e per Skype for business.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049098"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="7dc6f-103">Update AAD Connect per includere più di una foresta</span><span class="sxs-lookup"><span data-stu-id="7dc6f-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="7dc6f-104">Azure AD Connect supporta la [sincronizzazione da più foreste](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="7dc6f-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="7dc6f-105">Tuttavia, supporta solo un'istanza di Azure AD Connect syncing to AAD.</span><span class="sxs-lookup"><span data-stu-id="7dc6f-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="7dc6f-106">Pertanto, nei casi in cui Azure AD è già installato in una foresta, è necessario aggiornare l'istanza esistente di AAD Connect per eseguire la sincronizzazione dalla foresta aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="7dc6f-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="7dc6f-107">Se tutte le identità sono rappresentate solo una volta in entrambe le foreste (ovvero se non sono stati apportati contatti abilitati alla posta elettronica), è possibile rieseguire la procedura guidata per la connessione di AAD, scegliere "Personalizza opzioni di sincronizzazione" e quindi nella pagina **Connetti le directory** immettere il nome della foresta aggiuntiva e creds.</span><span class="sxs-lookup"><span data-stu-id="7dc6f-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="7dc6f-108">![Pagina Connetti le directory](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="7dc6f-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="7dc6f-109">Tuttavia, se gli utenti possono esistere in più di una directory e si intende unire i dati (ad esempio, se gli oggetti contatto sono presenti in una foresta corrispondente agli utenti di un'altra foresta), sarà necessario disinstallare Azure AD Connect e reinstallarlo.</span><span class="sxs-lookup"><span data-stu-id="7dc6f-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="7dc6f-110">Ciò è dovuto al fatto che la condizione per le regole di join tra foreste può essere configurata solo durante la prima installazione.</span><span class="sxs-lookup"><span data-stu-id="7dc6f-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="7dc6f-111">Questa operazione viene fatta nella pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="7dc6f-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="7dc6f-112">![La pagina di identificazione univoca degli utenti](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="7dc6f-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="7dc6f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dc6f-113">See also</span></span>

[<span data-ttu-id="7dc6f-114">Consolidamento cloud per Teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="7dc6f-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)