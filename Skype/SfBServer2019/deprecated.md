---
title: Cosa è deprecato da Skype for Business Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: queste funzionalità sono state rimosse da Skype for Business Server 2019.'
ms.openlocfilehash: f77ccecd0ab963c0707a7b1dc1d24083ed0c3729
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813984"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Cosa è deprecato da Skype for Business Server 2019

Informazioni sulle caratteristiche e le funzionalità deprecate in Skype for Business Server 2019. Per informazioni sulle nuove funzionalità di Skype for Business Server 2019, vedere [novità di Skype for Business server 2019](whats-new.md).

Alcune caratteristiche de-enfatizzate sono incluse in Skype for Business Server 2019 per la compatibilità con le versioni precedenti del prodotto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Caratteristiche deprecate in Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateway XMPP per Skype for Business Server

Skype for Business Server 2015 e i suoi predecessori hanno consentito di configurare un proxy XMPP (Extensible Messaging and Presence Protocol) nell'Edge Server e un gateway XMPP nel server front-end o nel pool Front-end. Questa funzionalità non è più disponibile in Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente per Skype for Business Server

Il server di chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare alle conversazioni delle chat room che persistono nel tempo. La chat persistente non può essere distribuita con Skype for Business Server 2019. Questo ruolo del server viene rimosso dal generatore di topologia e dal codice. 

La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Mirroring SQL per Skype for Business Server

Il mirroring SQL non può essere distribuito con Skype for Business Server 2019. Altre opzioni per fornire elevata disponibilità e ripristino di emergenza sono ancora supportate e scegliere tra di esse. Vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) per esaminare le opzioni.

### <a name="in-place-upgrades"></a>Aggiornamenti sul posto 

Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. L'aggiornamento affiancato e la coesistenza sono supportati, vedere [migrazione a Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) per altre informazioni.

### <a name="mobility-service-mcx"></a>Servizio di mobilità (MCX)

Il supporto del servizio di mobilità usato dai client mobili legacy non è più disponibile in Skype for Business Server 2019. Questa operazione è stata annunciata in precedenza in Skype for Business Server 2015.

Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.

Per altre informazioni, Vedi [pianificare la mobilità per Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) e il [confronto delle caratteristiche dei client per dispositivi mobili per Skype for business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Strumenti

Gli strumenti seguenti non saranno disponibili per l'uso in occasione della versione iniziale di Skype for Business Server 2019:

- Calcolatore di pianificazione della capacità di Skype for Business Server
- Strumenti di debug di Skype for Business Server
- Strumenti del Resource Kit di Skype for Business Server (alcuni strumenti verranno rimossi)
    - Chiama Parkometer
    - Console utente di ricerca
    - Migrazione degli annunci di numeri non assegnati

Gli strumenti seguenti non sono supportati con Skype for Business Server 2019:

- Metodologia di qualità delle chiamate (ma non chiamata Quality Dashboard)
- Scorecard della metodologia della qualità della chiamata Microsoft, v 1.5
- Progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione
- Strumento di stress e prestazioni di Skype for Business Server 2015

### <a name="see-also"></a>Vedere anche

[Novità di Skype for Business Server 2019](whats-new.md)

[Migrazione della federazione di XMPP](migration/migrating-xmpp-federation.md)
