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
ms.openlocfilehash: 586a9022602de97526b262b612d3e87e0a174ccc12a728b57d0664d9d05317b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342341"
---
# <a name="legacy-merge"></a>Unione legacy

**L'FQDN esterno di Web Conferencing** consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per conferenze Web del server perimetrale legacy.

Il valore della porta esterna **443** per le conferenze **Web** esterne è la porta SIP (Transmission Control Protocol) predefinita configurata per i client di conferenza. Se il valore predefinito non è stato utilizzato, aggiornare il **valore della porta esterna di Conferenza Web** esterna.

Selezionare la casella di controllo Questo pool di server perimetrali viene utilizzato per **la federazione** e la connettività di messaggistica istantanea pubblica se si prevede di utilizzare questo server perimetrale per la federazione. Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione. Se non si seleziona questa casella e si decide in un secondo momento che si desidera abilitare la federazione, è necessario eseguire di nuovo l'Unione guidata generatore di topologie, nonché pubblicare la topologia. Per informazioni dettagliate, vedere [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).