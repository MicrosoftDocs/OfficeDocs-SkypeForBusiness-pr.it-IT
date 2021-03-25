---
title: Unione legacy
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: L'FQDN esterno di Web Conferencing consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per conferenze Web del server perimetrale legacy.
ms.openlocfilehash: 87b70bc6d577f2752c00c7f7f73577eac7e759fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121064"
---
# <a name="legacy-merge"></a>Unione legacy

**L'FQDN esterno di Web Conferencing** consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per conferenze Web del server perimetrale legacy.

Il valore della porta esterna **443** per le conferenze **Web** esterne è la porta SIP (Transmission Control Protocol) predefinita configurata per i client di conferenza. Se il valore predefinito non è stato utilizzato, aggiornare il **valore della porta esterna di Conferenza Web** esterna.

Selezionare la casella di controllo Questo pool di server perimetrali viene utilizzato per **la federazione** e la connettività di messaggistica istantanea pubblica se si prevede di utilizzare questo server perimetrale per la federazione. Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione. Se non si seleziona questa casella e si decide in un secondo momento che si desidera abilitare la federazione, è necessario eseguire di nuovo l'Unione guidata generatore di topologie, nonché pubblicare la topologia. Per informazioni dettagliate, vedere [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).