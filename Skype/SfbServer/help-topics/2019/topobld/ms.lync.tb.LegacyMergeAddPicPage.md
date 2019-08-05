---
title: Unione legacy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Il nome FQDN esterno di Web Conferencing consente agli utenti esterni di partecipare a riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.
ms.openlocfilehash: 96b69e53b0f7538412c6bad7cebbf8e964607b48
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195140"
---
# <a name="legacy-merge"></a>Unione legacy

Il **nome FQDN esterno di Web** Conferencing consente agli utenti esterni di partecipare a riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.

Il valore della **porta esterna Web** per la conferenza esterna di **443** è la porta SIP (default Transmission Control Protocol) predefinita configurata per i client di conferenza. Se il valore predefinito non è stato usato, aggiornare il valore della **porta esterna di Web Conferencing esterno** .

Selezionare la casella di controllo **questo pool di bordi viene usato per la Federazione e la connettività di messaggistica istantanea pubblica** se si prevede di usare questo Edge Server per la Federazione. Se sono distribuiti più server perimetrali, solo uno di essi verrà abilitato per la Federazione. Se non si seleziona questa casella e si decide in seguito che si vuole abilitare la Federazione, è necessario eseguire di nuovo la procedura guidata di Unione di generatore di topologia, nonché pubblicare la topologia. Per informazioni dettagliate, vedere la [fase 4: unire](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)le topologie.


