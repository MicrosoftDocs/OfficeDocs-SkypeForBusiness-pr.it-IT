---
title: Esperienza teams in un sito Microsoft 365 o Office 365 OneDrive e un contratto di locazione multigeo-abilitato per SharePoint Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Informazioni sull'uso di team in Microsoft 365 o Office 365 OneDrive e il contratto di locazione multi-Geo abilitato per SharePoint Online.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534155d49cda89291e5d8bdfb8da9b8caf0efb5f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780395"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="81c1f-103">Esperienza teams in un sito Microsoft 365 o Office 365 OneDrive e un contratto di locazione multigeo-abilitato per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="81c1f-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="81c1f-104">Microsoft teams è un software per la chat di gruppo, l'hub per il lavoro in team in Office 365.</span><span class="sxs-lookup"><span data-stu-id="81c1f-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="81c1f-105">È alimentato dal servizio Microsoft 365 groups insieme a SharePoint Online e OneDrive for business per l'esperienza dei suoi file.</span><span class="sxs-lookup"><span data-stu-id="81c1f-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="81c1f-106">In un OneDrive for business/SharePoint Online Multi-geo-locazione, in cui il tenant è esteso a molte posizioni geografiche come il Nord America, l'Europa e l'Australia, l'esperienza dei file sottostanti è a conoscenza di più Geo, quindi l'esperienza di teams con la collaborazione di file è anche a livello geo-consapevole.</span><span class="sxs-lookup"><span data-stu-id="81c1f-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="81c1f-107">Questa è una delle principali funzionalità all'avanguardia per i team per la superficie di file ospitati in più GEOS nella sua esperienza di file nativo.</span><span class="sxs-lookup"><span data-stu-id="81c1f-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="81c1f-108">Ad esempio, in un contratto di locazione di Contoso con l'Europa come satellite geo e Nord America come Geo centrale, un utente satellite europeo vedrà i file di OneDrive nella scheda file nel riquadro sinistro, anche se i file sono ospitati nella posizione dati in Europa e gli Stati Uniti sono la posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="81c1f-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="81c1f-109">Inoltre, l'utente può accedere ai file usati più di recente sotto la lama di visualizzazione recente.</span><span class="sxs-lookup"><span data-stu-id="81c1f-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="81c1f-110">I file recenti possono includere file condivisi con l'utente dagli utenti di altri GEOS e potrebbero essere padroneggiati in altre posizioni geografiche a cui il tenant è esteso.</span><span class="sxs-lookup"><span data-stu-id="81c1f-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="81c1f-111">Il sito del gruppo di un team specifico è anche a livello di Geo-Aware.</span><span class="sxs-lookup"><span data-stu-id="81c1f-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="81c1f-112">Ossia, se un utente satellite europeo sta creando un team, il sito dei gruppi corrispondenti verrà creato nella posizione Europa e i file associati al gruppo del team verranno mantenuti a riposo in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="81c1f-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="81c1f-113">Le eventuali esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, saranno destinate a tale posizione europea, mantenendo la promessa di data Residency per tali file.</span><span class="sxs-lookup"><span data-stu-id="81c1f-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="81c1f-114">Tutto ciò è reso possibile dai gruppi di Microsoft 365 della Fondazione sottostante che diventano più consapevoli della multigeo.</span><span class="sxs-lookup"><span data-stu-id="81c1f-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="81c1f-115">Dato che un contratto multigeo è un unico tenant globale, durante le @ menzioni gli utenti satellitari potranno vedere i loro colleghi da tutto il mondo, indipendentemente dal luogo in cui risiedono.</span><span class="sxs-lookup"><span data-stu-id="81c1f-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="81c1f-116">Tieni presente che le conversazioni nelle chat e nelle note ISTANTANEe della riunione all'interno dell'esperienza teams non sono a conoscenza di più Geo e vengono mantenute solo all'interno della posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="81c1f-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="81c1f-117">In genere, le conversazioni di chat non vengono applicate alle esigenze di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="81c1f-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="81c1f-118">Per altre informazioni su Office 365 multi-Geo, vedere la [pagina Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="81c1f-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>