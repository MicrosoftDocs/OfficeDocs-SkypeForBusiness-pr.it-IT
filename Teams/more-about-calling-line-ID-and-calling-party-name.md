---
title: Ulteriori informazioni su ID linea chiamante e nome del chiamante
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Perché è necessario aggiungere una persona autorizzata che possa apportare modifiche all'account quando si usa la procedura guidata Nuovo ordine di portabilità numero locale.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255399"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="cb736-103">Ulteriori informazioni su ID linea chiamante e nome del chiamante</span><span class="sxs-lookup"><span data-stu-id="cb736-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="cb736-104">CallerID, come si fa in genere, è costituito da due informazioni identificabili per l'utente:</span><span class="sxs-lookup"><span data-stu-id="cb736-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="cb736-105">Un numero di telefono (in genere denominato CLID o ID linea chiamante)</span><span class="sxs-lookup"><span data-stu-id="cb736-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="cb736-106">Nome del chiamante (in genere denominato CNAM), che può avere una lunghezza massima di 15 caratteri.</span><span class="sxs-lookup"><span data-stu-id="cb736-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="cb736-107">Quando viene effettuata una chiamata, il CLID (numero di telefono) viene instradato al corriere di destinazione (noto anche come gestore finale).</span><span class="sxs-lookup"><span data-stu-id="cb736-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="cb736-108">Le informazioni CNAM per la chiamata possono essere instradati o meno con la chiamata, in quanto ciò dipende da come il Paese ha implementato il CNAM (se del tutto).</span><span class="sxs-lookup"><span data-stu-id="cb736-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="cb736-109">L'affidabilità della consegna di CNAM con la chiamata varia a seconda del paese e dei gestori che gestiscono la chiamata come intermediario e/o gestore terminante.</span><span class="sxs-lookup"><span data-stu-id="cb736-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="cb736-110">La trasmissione CLID & CNAM è responsabilità del corriere che termina nel momento in cui il vettore che termina deve supportare la funzionalità CLID & CNAM e fornire record aggiornati per entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="cb736-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="cb736-111">Microsoft fornisce in modo affidabile i valori CLID al momento delle chiamate di origine, ma tali valori potrebbero non essere mantenuti intatti dopo il passaggio da un operatore intermedio o dal gestore di terminazione.</span><span class="sxs-lookup"><span data-stu-id="cb736-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="cb736-112">Purtroppo, nel caso in cui il valore CLID sia cambiato, omesso o troncato dall'intermediario o dal gestore di terminazione, Microsoft non ha nulla in più per correggere tali problemi nella rete telefonica pubblica.</span><span class="sxs-lookup"><span data-stu-id="cb736-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="cb736-113">Le incoerenze nel CNAM possono essere causate da ritardi nei gestori intermedi o che terminano aggiornando le informazioni CNAM nei database autorevoli come nel caso degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="cb736-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="cb736-114">Nei paesi in cui non esiste un database autorevole per il CNAM, le procedure dei singoli gestori possono anche causare problemi con le informazioni CNAM che rimangono intatte con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cb736-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="cb736-115">Microsoft attualmente non supporta le informazioni CNAM provenienti da paesi diversi dagli Stati Uniti."</span><span class="sxs-lookup"><span data-stu-id="cb736-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb736-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cb736-116">Related topics</span></span>


