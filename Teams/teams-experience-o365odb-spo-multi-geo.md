---
title: Esperienza di Teams in un ambiente Multi-Geo-enabled di Microsoft 365
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
description: In questo articolo imparerai a usare Teams in un ambiente multi-geo-abilitato per Microsoft 365.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122246"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="1477d-103">Esperienza di Teams in una tenancy multi-geo-enabled di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1477d-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="1477d-104">Microsoft Teams è un software di chat di gruppo, l'hub per il lavoro in team in Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="1477d-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="1477d-105">È basato sul servizio Gruppi di Microsoft 365 insieme a SharePoint Online e OneDrive for Business per l'esperienza con i file.</span><span class="sxs-lookup"><span data-stu-id="1477d-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="1477d-106">In una tenancy multi-geo di OneDrive for Business/SharePoint Online, in cui il tenant viene esteso a molte aree geografiche, come Nord America, Europa e Australia, l'esperienza dei file sottostanti è con supporto multi-geo, quindi anche l'esperienza di Teams per la collaborazione dei file è multi-geo..</span><span class="sxs-lookup"><span data-stu-id="1477d-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="1477d-107">Questa funzionalità è una funzionalità chiave all'avanguardia che consente a Teams di visualizzare i file ospitati su più elementi geografici nell'esperienza dei file nativi.</span><span class="sxs-lookup"><span data-stu-id="1477d-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="1477d-108">Sono inclusi anche i file di OneNote e Wiki.</span><span class="sxs-lookup"><span data-stu-id="1477d-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="1477d-109">Ad esempio, in una tenancy Contoso con l'Europa come geo satellitare e l'America del  Nord come geo centrale, un utente satellitare europeo vede i propri file di OneDrive nella scheda File nel riquadro sinistro, anche se i file sono ospitati nella posizione dei dati in Europa e gli Stati Uniti sono la posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="1477d-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="1477d-110">Inoltre, l'utente può accedere ai file usati più di recente nel blade **Visualizzazione** recente.</span><span class="sxs-lookup"><span data-stu-id="1477d-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="1477d-111">I file recenti possono includere file condivisi da utenti in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="1477d-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="1477d-112">Anche il sito di SharePoint di un determinato team è multi-geo-aware.</span><span class="sxs-lookup"><span data-stu-id="1477d-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="1477d-113">In altri caso, se un utente satellitare europeo sta creando un team, il sito di SharePoint corrispondente verrà creato nella località europa.</span><span class="sxs-lookup"><span data-stu-id="1477d-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="1477d-114">I file associati al team verranno mantenuti in quella posizione.</span><span class="sxs-lookup"><span data-stu-id="1477d-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="1477d-115">Tutte le esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, verranno archiviate in questa posizione europea, mantenendo la residenza dei dati per tali file.</span><span class="sxs-lookup"><span data-stu-id="1477d-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="1477d-116">Una tenancy multi-geo è un singolo tenant globale, quindi durante le @menzioni gli utenti satellitari potranno vedere i colleghi di tutto il mondo, indipendentemente da dove si trova.</span><span class="sxs-lookup"><span data-stu-id="1477d-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="1477d-117">Le conversazioni in chat, i messaggi nei canali, le note di messaggistica istantanea delle riunioni e le chat all'interno dell'esperienza Teams non sono multi-geo-aware e sono tutte conservate solo all'interno della posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="1477d-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="1477d-118">In genere, le conversazioni di chat non vengono applicate alle esigenze di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="1477d-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="1477d-119">Per altre informazioni, vedere [Posizione dei dati in Microsoft Teams.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="1477d-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="1477d-120">Per altre informazioni su Multi-Geo, vedere la pagina delle funzionalità [Microsoft Multi-Geo.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="1477d-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
