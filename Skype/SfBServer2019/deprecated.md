---
title: Funzionalità deprecate di Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: queste funzionalità sono state rimosse da Skype for Business Server 2019.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808726"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Funzionalità deprecate di Skype for Business Server 2019

Informazioni sulle funzionalità deprecate in Skype for Business Server 2019. Per informazioni sulle nuove funzionalità di Skype for Business Server 2019, vedere [What's in Skype for Business Server 2019](whats-new.md).

Alcune funzionalità non evidenziate sono incluse in Skype for Business Server 2019 per garantire la compatibilità con le versioni precedenti del prodotto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Funzionalità deprecate in Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateway XMPP per Skype for Business Server

Skype for Business Server 2015 e i suoi predecessori hanno consentito di configurare un proxy XMPP (Extensible Messaging and Presence Protocol) nel server perimetrale e un gateway XMPP nel Front End Server o nel pool Front End. Questa funzionalità non è più disponibile in Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente per Skype for Business Server

Il server Chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare a conversazioni di chat room persistenti nel tempo. La chat persistente non può essere distribuita con Skype for Business Server 2019. Questo ruolo del server viene rimosso da Generatore di topologie e dal codice. 

Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Mirroring for Skype for Business Server

SQL il mirroring non può essere distribuito con Skype for Business Server 2019. Altre opzioni per fornire disponibilità elevata e ripristino di emergenza sono ancora supportate ed è consigliabile scegliere tra di esse. Vedere [Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) per esaminare le opzioni.

### <a name="in-place-upgrades"></a>Aggiornamenti sul posto 

Gli aggiornamenti sul posto erano disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. L'aggiornamento affiancato e la coesistenza sono supportati, vedere Migrazione a [Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) per ulteriori informazioni.

### <a name="mobility-service-mcx"></a>Servizio per dispositivi mobili (Mcx)

Il supporto del servizio per dispositivi mobili utilizzato dai client mobili legacy non è più disponibile in Skype for Business Server 2019. Questo è stato annunciato in precedenza in Skype for Business Server 2015.

Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano Mcx dovranno eseguire l'aggiornamento a un client corrente.

Per ulteriori dettagli, vedere [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business.](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="tools"></a>Strumenti

I seguenti strumenti non saranno disponibili per l'uso nella versione iniziale di Skype for Business Server 2019:

- Calcolatore di pianificazione della capacità di Skype for Business Server
- Strumenti di debug di Skype for Business Server
- Strumenti del Resource Kit di Skype for Business Server (alcuni strumenti verranno rimossi)
    - Call Parkometer
    - Console utente di ricerca
    - Migrazione degli annunci dei numeri non assegnati

I seguenti strumenti non sono supportati con Skype for Business Server 2019:

- Metodologia di qualità delle chiamate (ma non dashboard qualità chiamata)
- Microsoft Call Quality Methodology Scorecard, v1.5
- Strumento di pianificazione di Skype for Business Server 2015
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Vedere anche

[Novità di Skype for Business Server 2019](whats-new.md)

[Migrazione della federazione di XMPP](migration/migrating-xmpp-federation.md)
