---
title: Cosa è deprecato da Skype for Business Server 2019
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
description: 'Riepilogo: queste funzionalità sono state rimosse Skype for Business Server 2019.'
ms.openlocfilehash: 43fa8bae64e65fcba1aaf21c75e06d396d3c47eee8df40cec0db0eb1d5d646eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282469"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Cosa è deprecato da Skype for Business Server 2019

Informazioni sulle funzionalità deprecate in Skype for Business Server 2019. Per informazioni sulle nuove funzionalità di Skype for Business Server 2019, vedere [What's in Skype for Business Server 2019](whats-new.md).

Alcune funzionalità non evidenziate sono incluse in Skype for Business Server 2019 per garantire la compatibilità con le versioni precedenti del prodotto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Funzionalità deprecate in Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateway XMPP per Skype for Business Server

Skype for Business Server 2015 e i relativi predecessori hanno consentito di configurare un proxy XMPP (Extensible Messaging and Presence Protocol) nel server perimetrale e un gateway XMPP nel Front End Server o nel pool Front End. Questa funzionalità non è più disponibile in Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Persistent Chat per Skype for Business Server

Il server Chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare a conversazioni di chat room persistenti nel tempo. Non è possibile distribuire chat persistente con Skype for Business Server 2019. Questo ruolo del server viene rimosso da Generatore di topologie e dal codice. 

La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Mirroring per Skype for Business Server

SQL Il mirroring non può essere distribuito con Skype for Business Server 2019. Altre opzioni per la disponibilità elevata e il ripristino di emergenza sono ancora supportate ed è consigliabile scegliere tra queste opzioni. Vedere [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) per esaminare le opzioni.

### <a name="in-place-upgrades"></a>Aggiornamenti sul posto 

Gli aggiornamenti sul posto sono disponibili Skype for Business Server 2015, ma non sono più supportati Skype for Business Server 2019. L'aggiornamento affiancato e la coesistenza sono supportati, vedere [Migrazione a Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) per ulteriori informazioni.

### <a name="mobility-service-mcx"></a>Servizio per dispositivi mobili (Mcx)

Il supporto del servizio per dispositivi mobili utilizzato dai client mobili legacy non è più disponibile Skype for Business Server 2019. Questo è stato annunciato in Skype for Business Server 2015.

Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano Mcx dovranno eseguire l'aggiornamento a un client corrente.

Per ulteriori informazioni, vedere [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for [Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Strumenti

Gli strumenti seguenti non saranno disponibili per l'uso nella versione iniziale di Skype for Business Server 2019:

- Calcolatore di pianificazione della capacità di Skype for Business Server
- Skype for Business Server Strumenti di debug
- Skype for Business Server Strumenti del Resource Kit (alcuni strumenti verranno rimossi)
    - Parcheggio di chiamata
    - Console utente di ricerca
    - Migrazione annuncio numero non assegnato

Gli strumenti seguenti non sono supportati con Skype for Business Server 2019:

- Metodologia di qualità delle chiamate (ma non dashboard qualità chiamata)
- Scorecard sulla metodologia della qualità delle chiamate Microsoft, v1.5
- Skype for Business Server 2015 Planning Tool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Vedere anche

[Novità di Skype for Business Server 2019](whats-new.md)

[Migrazione della federazione di XMPP](migration/migrating-xmpp-federation.md)
