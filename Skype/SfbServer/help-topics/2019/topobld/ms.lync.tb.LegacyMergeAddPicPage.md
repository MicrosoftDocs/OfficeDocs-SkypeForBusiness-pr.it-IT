---
title: Unione legacy
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Il nome di dominio completo esterno webconferenza consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per conferenze Web del server perimetrale legacy.
ms.openlocfilehash: 9e24e3f89d3ed7e63406b0a7eb3e46201ae7e530
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836738"
---
# <a name="legacy-merge"></a>Unione legacy

Il **nome di dominio completo esterno** webconferenza consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per conferenze Web del server perimetrale legacy.

Il valore della porta esterna **443** per le conferenze **Web** esterne è la porta SIP (Transmission Control Protocol) predefinita configurata per i client di conferenza. Se il valore predefinito non è stato utilizzato, aggiornare il valore della porta **esterna di Conferenza Web** esterna.

Selezionare la casella di controllo Questo pool di server perimetrali viene utilizzato per **la federazione** e la connettività di messaggistica istantanea pubblica se si prevede di utilizzare questo server perimetrale per la federazione. Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione. Se non si seleziona questa casella e si decide in un secondo momento che si desidera abilitare la federazione, è necessario eseguire di nuovo l'Unione guidata generatore di topologie, nonché pubblicare la topologia. Per informazioni dettagliate, vedere [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).