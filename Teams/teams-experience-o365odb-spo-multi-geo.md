---
title: Esperienza teams in un ambiente Microsoft 365 multigeo-Enabled
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: In questo articolo imparerai a usare teams in un ambiente Microsoft 365 multigeo-Enabled.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122246"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="b03c9-103">Esperienza teams in un contratto di locazione multigeo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b03c9-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="b03c9-104">Microsoft teams è un software di chat di gruppo, l'hub per il lavoro in team in Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="b03c9-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="b03c9-105">È alimentato dal servizio Microsoft 365 groups insieme a SharePoint Online e OneDrive for business per l'esperienza dei suoi file.</span><span class="sxs-lookup"><span data-stu-id="b03c9-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="b03c9-106">In un OneDrive for business/SharePoint Online Multi-geo-locazione, in cui il tenant è esteso a molte posizioni geografiche come il Nord America, l'Europa e l'Australia, l'esperienza dei file sottostanti è multi-Geo-Aware, quindi l'esperienza dei team con la collaborazione di file è anche multi-Geo-Aware.</span><span class="sxs-lookup"><span data-stu-id="b03c9-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="b03c9-107">Questa funzionalità è una delle principali funzionalità all'avanguardia per i team per la superficie di file ospitati in più GEOS nella sua esperienza di file nativo.</span><span class="sxs-lookup"><span data-stu-id="b03c9-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="b03c9-108">Questo include anche i file di OneNote e wiki.</span><span class="sxs-lookup"><span data-stu-id="b03c9-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="b03c9-109">Ad esempio, in un contratto di locazione di Contoso con l'Europa come satellite geo e Nord America come Geo centrale, un utente satellite europeo vedrà i propri file di OneDrive nella scheda **file** nel riquadro sinistro, anche se i file sono ospitati nella posizione dati in Europa e gli Stati Uniti sono la posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="b03c9-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="b03c9-110">Inoltre, l'utente può accedere ai file usati più di recente sotto la lama di visualizzazione **recente** .</span><span class="sxs-lookup"><span data-stu-id="b03c9-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="b03c9-111">I file recenti possono includere file condivisi dagli utenti in altre posizioni geo.</span><span class="sxs-lookup"><span data-stu-id="b03c9-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="b03c9-112">Il sito di SharePoint di un team specifico è anche a livello geo-consapevole.</span><span class="sxs-lookup"><span data-stu-id="b03c9-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="b03c9-113">Ovvero, se un utente satellite europeo sta creando un team, il sito di SharePoint corrispondente verrà creato nella posizione Europa.</span><span class="sxs-lookup"><span data-stu-id="b03c9-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="b03c9-114">I file associati al team verranno mantenuti a riposo in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="b03c9-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="b03c9-115">Le eventuali esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, verranno archiviate in quella posizione europea, mantenendo la promessa di data Residency per tali file.</span><span class="sxs-lookup"><span data-stu-id="b03c9-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="b03c9-116">Dato che un contratto di locazione multigeo è un unico tenant globale, durante @ menzioni gli utenti satellitari potranno vedere i loro colleghi provenienti da tutto il mondo, ovunque si trovino.</span><span class="sxs-lookup"><span data-stu-id="b03c9-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="b03c9-117">Le conversazioni in chat, nei messaggi di canale e nelle note/chat ISTANTANEe della riunione all'interno dell'esperienza teams non sono multi-Geo-Aware e vengono mantenute solo all'interno della posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="b03c9-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="b03c9-118">In genere, le conversazioni di chat non vengono applicate alle esigenze di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="b03c9-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="b03c9-119">Per altre informazioni, vedere la [posizione dei dati in Microsoft teams](location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b03c9-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="b03c9-120">Per altre info su multi-Geo, vedere la [pagina Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="b03c9-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
