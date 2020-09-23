---
title: Unione legacy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Il nome di dominio completo esterno per i servizi Web Conferencing consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per le conferenze Web del server perimetrale legacy.
ms.openlocfilehash: 984d40f8797a974a5865cca37ba1057dc638d886
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217997"
---
# <a name="legacy-merge"></a>Unione legacy

Il **nome di dominio completo esterno per i servizi Web Conferencing** consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per le conferenze Web del server perimetrale legacy.

Il valore della porta esterna per il servizio **Web Conferencing esterno** di **443** è la porta SIP (Session Initiation Protocol) predefinita del protocollo TCP (Transmission Control Protocol) configurata per i client di conferenza. Se non è stato utilizzato il valore predefinito, aggiornare il valore della porta esterna per il servizio **Web Conferencing esterno** .

Selezionare la casella di controllo il **pool di server perimetrali utilizzato per la Federazione e la connettività per la messaggistica istantanea pubblica** se si prevede di utilizzare questo server perimetrale per la Federazione. Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione. Se non si seleziona questa casella e si decide in seguito che si desidera abilitare la Federazione, è necessario eseguire di nuovo l'Unione guidata generatore di topologie, nonché pubblicare la topologia. Per informazioni dettagliate, vedere [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


