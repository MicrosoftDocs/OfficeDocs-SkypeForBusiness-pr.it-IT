---
title: Unione legacy
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: L'FQDN esterno di Web Conferencing consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.
ms.openlocfilehash: b49d8ed17bdc56050e00216c5506b85db2b1d3aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832996"
---
# <a name="legacy-merge"></a>Unione legacy

**L'FQDN esterno di Web Conferencing** consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.

Il valore della porta esterna **443** per le conferenze **Web** esterne è la porta SIP (Session Initiation Protocol) TCP (Transmission Control Protocol) predefinita configurata per i client di conferenza. Se non è stato utilizzato il valore predefinito, aggiornare il valore della porta **esterna di Web Conferencing** esterna.

Selezionare la casella di controllo Questo pool di server perimetrali viene utilizzato per la federazione e la connettività **per messaggistica** istantanea pubblica se si prevede di utilizzare questo server perimetrale per la federazione. Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione. Se non si seleziona questa casella e in seguito si decide di abilitare la federazione, sarà necessario eseguire di nuovo l'unione guidata di Generatore di topologie e pubblicare la topologia. Per informazioni dettagliate, vedere [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


