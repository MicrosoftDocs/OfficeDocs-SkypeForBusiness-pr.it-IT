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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include i passaggi dettagliati per l'aggiornamento di AAD Connect per includere più foreste come parte del consolidamento del cloud per Teams e Skype for business.
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185489"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="84e89-103">Aggiornare AAD Connect per includere più di una foresta</span><span class="sxs-lookup"><span data-stu-id="84e89-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="84e89-104">Azure AD Connect supporta la [sincronizzazione da più foreste](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="84e89-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="84e89-105">Supporta tuttavia una sola istanza di Azure AD Connect syncing to AAD.</span><span class="sxs-lookup"><span data-stu-id="84e89-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="84e89-106">Di conseguenza, nei casi in cui Azure AD è già installato in un'unica foresta, l'istanza esistente di AAD Connect deve essere aggiornata per la sincronizzazione dalla foresta aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="84e89-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="84e89-107">Se tutte le identità sono rappresentate una sola volta in entrambe le foreste, ovvero se non sono stati apportati contatti abilitati per la posta elettronica, è possibile rieseguire semplicemente la procedura guidata di connessione AAD, scegliere "Personalizza opzioni di sincronizzazione" e quindi nella \*\*directory Connetti \*\*pagina, immettere il nome della foresta aggiuntiva e creds.</span><span class="sxs-lookup"><span data-stu-id="84e89-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="84e89-108">![Pagina Connetti le tue directory](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="84e89-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="84e89-109">Tuttavia, se gli utenti possono esistere in più directory e si uniscono i dati, ad esempio se gli oggetti contatto sono presenti in una foresta corrispondente agli utenti di un'altra foresta, sarà necessario disinstallare Azure AD Connect e reinstallarlo.</span><span class="sxs-lookup"><span data-stu-id="84e89-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="84e89-110">Il motivo è che la condizione delle regole di join tra foreste può essere configurata solo durante la prima installazione.</span><span class="sxs-lookup"><span data-stu-id="84e89-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="84e89-111">Questa operazione viene eseguita nella pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="84e89-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="84e89-112">![La pagina di identificazione univoca degli utenti](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="84e89-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="84e89-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84e89-113">See also</span></span>

[<span data-ttu-id="84e89-114">Consolidamento cloud per Teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="84e89-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)