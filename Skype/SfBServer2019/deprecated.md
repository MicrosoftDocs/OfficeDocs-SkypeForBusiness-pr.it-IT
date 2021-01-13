---
title: Cosa è obsoleto da Skype for Business Server 2019
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
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Cosa è obsoleto da Skype for Business Server 2019

Informazioni sulle caratteristiche e le funzionalità deprecate in Skype for Business Server 2019. Per informazioni sulle nuove funzionalità in Skype for Business Server 2019, vedere [What ' s in Skype for Business server 2019](whats-new.md).

Alcune caratteristiche de-enfatizzate sono incluse in Skype for Business Server 2019 per la compatibilità con le versioni precedenti del prodotto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Caratteristiche deprecate in Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateway XMPP per Skype for Business Server

Skype for Business Server 2015 e i suoi predecessori hanno consentito di configurare un proxy XMPP (Extensible Messaging and Presence Protocol) nel server perimetrale e un gateway XMPP nel front end server o nel pool Front end. Questa funzionalità non è più disponibile in Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente per Skype for Business Server

Il server Chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare a conversazioni chat room che persistono nel tempo. La chat persistente non può essere distribuita con Skype for Business Server 2019. Questo ruolo del server viene rimosso dal generatore di topologie e dal codice. 

La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Mirroring SQL per Skype for Business Server

Il mirroring SQL non può essere distribuito con Skype for Business Server 2019. Altre opzioni per la disponibilità elevata e il ripristino di emergenza sono ancora supportate e è consigliabile scegliere tra di esse. Per esaminare le opzioni, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) .

### <a name="in-place-upgrades"></a>Aggiornamenti sul posto 

Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. L'aggiornamento affiancato e la coesistenza sono supportati, vedere [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) per ulteriori informazioni.

### <a name="mobility-service-mcx"></a>Servizio per dispositivi mobili (MCX)

Il supporto per i servizi mobili utilizzato dai client mobili legacy non è più disponibile in Skype for Business Server 2019. Questo è stato annunciato in precedenza in Skype for Business Server 2015.

Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.

Per ulteriori informazioni, vedere [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [mobile client Feature Comparison for Skype for business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Strumenti

Gli strumenti seguenti non saranno disponibili per l'uso nella versione iniziale di Skype for Business Server 2019:

- Calcolatore di pianificazione della capacità di Skype for Business Server
- Strumenti di debug di Skype for Business Server
- Strumenti del Resource Kit di Skype for Business Server (alcuni strumenti verranno rimossi)
    - Chiamata Parkometer
    - Console utente di ricerca
    - Migrazione degli annunci di numeri non assegnati

Gli strumenti seguenti non sono supportati con Skype for Business Server 2019:

- Metodologia della qualità delle chiamate (ma non Call Quality Dashboard)
- Scorecard della metodologia della qualità delle chiamate Microsoft, v 1.5
- Strumento di pianificazione di Skype for Business Server 2015
- Strumento per lo stress e le prestazioni di Skype for Business Server 2015

### <a name="see-also"></a>Vedere anche

[Novità di Skype for Business Server 2019](whats-new.md)

[Migrazione della federazione di XMPP](migration/migrating-xmpp-federation.md)
