---
title: Ulteriori informazioni su ID linea di chiamata e nome del chiamante
ms.author: tonysmit
author: tonysmit
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
- NOCSH
ms.custom:
- Calling Plans
description: Informazioni sui motivi per cui è necessario aggiungere una persona autorizzata che può apportare modifiche all'account quando si usa la procedura guidata nuovo ordine di trasferimento dei numeri locali.
ms.openlocfilehash: a687bc1aca8a47b349415d4a0cc2dc9f61f81884
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708802"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="b5c63-103">Ulteriori informazioni su ID linea di chiamata e nome del chiamante</span><span class="sxs-lookup"><span data-stu-id="b5c63-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="b5c63-104">Criteri ID chiamante, come si fa in genere, è costituito da due parti di informazioni identificabili che si trovano di fronte all'utente:</span><span class="sxs-lookup"><span data-stu-id="b5c63-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="b5c63-105">Numero di telefono (in genere denominato CLID o ID linea chiamante)</span><span class="sxs-lookup"><span data-stu-id="b5c63-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="b5c63-106">Nome della festa chiamante (in genere indicato come CNAM) che può contenere fino a 15 caratteri di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="b5c63-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="b5c63-107">Quando viene effettuata una chiamata, il CLID (numero di telefono) viene indirizzato al vettore di destinazione (noto anche come elemento portante di terminazione).</span><span class="sxs-lookup"><span data-stu-id="b5c63-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="b5c63-108">Le informazioni CNAM per la chiamata possono essere instradate o meno con la chiamata in quanto ciò dipende dal modo in cui il paese ha implementato CNAM (se non del tutto).</span><span class="sxs-lookup"><span data-stu-id="b5c63-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="b5c63-109">L'affidabilità della consegna CNAM con la chiamata varia a seconda del paese e dei vettori che gestiscono la chiamata come intermediari e/o come gestore di terminazione.</span><span class="sxs-lookup"><span data-stu-id="b5c63-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="b5c63-110">CLID & CNAM la trasmissione è la responsabilità del vettore di terminazione nella misura in cui il vettore di terminazione deve supportare le funzionalità di CLID & CNAM oltre a consentire i record aggiornati per entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="b5c63-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="b5c63-111">Microsoft fornisce in modo affidabile i valori di CLID in caso di chiamate di origine, ma tali valori potrebbero non essere mantenuti integri dopo il passaggio di un vettore intermedio o del vettore di terminazione.</span><span class="sxs-lookup"><span data-stu-id="b5c63-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="b5c63-112">Purtroppo, se il valore di CLID viene modificato, omesso o troncato dall'intermediario o da un vettore di terminazione, Microsoft non ha alcun ricorso per correggere tali problemi nella rete telefonica pubblica.</span><span class="sxs-lookup"><span data-stu-id="b5c63-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="b5c63-113">Le incongruenze in CNAM possono essere causate da ritardi nei vettori intermedi o di terminazione che aggiornano le informazioni di CNAM nei database autorevoli, come nel caso degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="b5c63-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="b5c63-114">In paesi in cui non esiste un database autorevole per CNAM, le singole procedure di trasporto possono anche causare problemi con le informazioni di CNAM che arrivano intatte con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b5c63-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="b5c63-115">Microsoft attualmente non supporta l'origine di informazioni CNAM in paesi diversi dagli Stati Uniti. "</span><span class="sxs-lookup"><span data-stu-id="b5c63-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5c63-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b5c63-116">Related topics</span></span>


