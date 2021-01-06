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
description: In questo articolo verranno fornite informazioni sull'uso di team in un ambiente Microsoft 365 multigeo-Enabled.
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757751"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="c3f13-103">Esperienza teams in un contratto di locazione multigeo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3f13-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="c3f13-104">Microsoft teams è un software per la chat di gruppo, l'hub per il lavoro in team in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f13-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365.</span></span> <span data-ttu-id="c3f13-105">È alimentato dal servizio Microsoft 365 groups insieme a SharePoint e OneDrive per l'esperienza di file.</span><span class="sxs-lookup"><span data-stu-id="c3f13-105">It is powered by the Microsoft 365 Groups service along with SharePoint and OneDrive for its files experience.</span></span> <span data-ttu-id="c3f13-106">In un'organizzazione multi-Geo in cui il tenant è esteso a molte posizioni geografiche come il Nord America, l'Europa e l'Australia, l'esperienza dei file sottostanti è a conoscenza di più Geo, quindi l'esperienza dei team con la collaborazione di file è anche a livello geo-consapevole.</span><span class="sxs-lookup"><span data-stu-id="c3f13-106">In a Multi-Geo organization in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="c3f13-107">In questo modo i team devono eseguire la superficie dei file ospitati in più posizioni geo nella propria esperienza di file nativi.</span><span class="sxs-lookup"><span data-stu-id="c3f13-107">This allows Teams to surface files hosted across multiple geo locations in its native files experience.</span></span>

<span data-ttu-id="c3f13-108">Ad esempio, in un contratto di locazione di Contoso con l'Europa come satellite geo e Nord America come Geo centrale, un utente satellite europeo vedrà i file di OneDrive nella scheda file nel riquadro sinistro, anche se i file sono ospitati nella posizione dati in Europa e gli Stati Uniti sono la posizione centrale del tenant.</span><span class="sxs-lookup"><span data-stu-id="c3f13-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="c3f13-109">Inoltre, l'utente può accedere ai file usati più di recente sotto la lama di visualizzazione recente.</span><span class="sxs-lookup"><span data-stu-id="c3f13-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="c3f13-110">I file recenti possono includere file condivisi dagli utenti in altre posizioni geo.</span><span class="sxs-lookup"><span data-stu-id="c3f13-110">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="c3f13-111">Il sito di SharePoint di un team specifico è anche a livello geo-Aware.</span><span class="sxs-lookup"><span data-stu-id="c3f13-111">A given Team’s SharePoint site is also Multi-Geo aware.</span></span> <span data-ttu-id="c3f13-112">Ovvero, se un utente satellite europeo sta creando un team, il sito di SharePoint corrispondente verrà creato nella posizione Europa e i file associati al team verranno mantenuti a riposo in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="c3f13-112">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location and the files associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="c3f13-113">Le eventuali esperienze successive, ad esempio il caricamento di un nuovo file o la modifica del file, verranno archiviate in quella posizione europea, mantenendo la promessa di data Residency per tali file.</span><span class="sxs-lookup"><span data-stu-id="c3f13-113">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="c3f13-114">Tieni presente che le conversazioni nelle chat e nelle note ISTANTANEe della riunione all'interno dell'esperienza teams non sono a conoscenza di più Geo e vengono mantenute solo all'interno della posizione centrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3f13-114">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the organization.</span></span>

<span data-ttu-id="c3f13-115">Per altre informazioni su multi-Geo, Vedi [funzionalità Multigeo di Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="c3f13-115">For more information about Multi-Geo, see [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span></span>
