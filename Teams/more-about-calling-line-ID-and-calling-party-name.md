---
title: Ulteriori informazioni su ID linea chiamante e nome del chiamante
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: Informazioni sull'ID della linea di chiamata e sul nome della parte chiamante.
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308315"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="6eb7d-103">Ulteriori informazioni su ID linea chiamante e nome del chiamante</span><span class="sxs-lookup"><span data-stu-id="6eb7d-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="6eb7d-104">CallerID è costituito da due informazioni rivolte all'utente:</span><span class="sxs-lookup"><span data-stu-id="6eb7d-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="6eb7d-105">Un numero di telefono (in genere definito CLID o ID della linea telefonica).</span><span class="sxs-lookup"><span data-stu-id="6eb7d-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="6eb7d-106">Nome della parte chiamante (in genere denominata CNAM).</span><span class="sxs-lookup"><span data-stu-id="6eb7d-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="6eb7d-107">Quando viene effettuata una chiamata, il CLID (numero di telefono) viene instradato al gestore di destinazione (noto anche come gestore di terminazione).</span><span class="sxs-lookup"><span data-stu-id="6eb7d-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="6eb7d-108">Le informazioni CNAM per la chiamata possono essere instradati o meno con la chiamata, perché queste informazioni dipendono da come il paese ha implementato CNAM (se del tutto).</span><span class="sxs-lookup"><span data-stu-id="6eb7d-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="6eb7d-109">L'affidabilità della consegna CNAM con la chiamata varia a seconda del paese e dei gestori che gestiscono la chiamata, sia come intermediario che come gestore di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="6eb7d-110">La trasmissione CLID & CNAM è responsabilità del gestore di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="6eb7d-111">Il gestore di terminazione deve supportare & CNAM clid e fornire record aggiornati per entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="6eb7d-112">Microsoft fornisce in modo affidabile i valori CLID durante le chiamate di origine, ma questi valori potrebbero non essere mantenuti intatti quando passano attraverso un gestore intermedio o il gestore di terminazione.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="6eb7d-113">Se il valore CLID viene modificato, omesso o troncato dal gestore intermedio o di terminazione, Microsoft non ha alcun ricorso per correggere tali problemi nella rete telefonica pubblica.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="6eb7d-114">Le incoerenze in CNAM possono essere causate quando i gestori intermedi o terminanti ritardano l'aggiornamento delle informazioni CNAM in database autorevoli, come nel caso degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="6eb7d-115">Nei paesi in cui non sono presenti database autorevoli per CNAM, le procedure dei singoli gestori possono anche causare problemi con le informazioni CNAM che arrivano intatte con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="6eb7d-116">Microsoft attualmente non supporta le informazioni CNAM di origine in paesi diversi dagli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="6eb7d-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6eb7d-117">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6eb7d-117">Related topics</span></span>


