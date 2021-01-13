---
title: Gestione della qualità del servizio (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quality of Service (QoS) è una tecnologia di rete utilizzata in alcune organizzazioni per fornire un'esperienza utente ottimale per le comunicazioni audio e video.
ms.openlocfilehash: 77fae69a6ceeaf65f80dd38e78e42e186786c4ed
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814156"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gestione della qualità del servizio (QoS) in Skype for Business Server


Quality of Service (QoS) è una tecnologia di rete utilizzata in alcune organizzazioni per fornire un'esperienza utente ottimale per le comunicazioni audio e video. La funzionalità QoS è più comunemente utilizzata nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete in competizione per una quantità relativamente ridotta di larghezza di banda disponibile, la qualità del servizio consente agli amministratori di assegnare priorità più elevate ai pacchetti che trasportano dati audio o video. Assegnando a questi pacchetti una priorità più elevata, è probabile che le comunicazioni audio e video vengano completate più velocemente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come il trasferimento di file, la navigazione web o i backup dei database. Ciò è dovuto al fatto che i pacchetti di rete utilizzati per i trasferimenti di file o i backup dei database sono assegnati come priorità "Best Effort".


> [!NOTE]  
> Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione sulla rete interna. Quando si implementa QoS, i server e i router vengono configurati in modo da supportare la marcatura dei pacchetti. Tuttavia, è necessario configurare questi dispositivi per supportare il contrassegno dei pacchetti in un modo specifico. Non è possibile presumere che la qualità del servizio sarà supportata su Internet o su altre reti. Anche se la qualità se il servizio è supportato su altre reti, non vi è alcuna garanzia che QoS venga configurato nello stesso modo in cui è stato configurato il servizio sulla rete.

Skype for Business Server non richiede la qualità del servizio; Se attualmente non si utilizza QoS, non è necessario installare il servizio prima di installare Skype for Business Server. Se si verifica una notevole quantità di perdita di pacchetti sulla rete, il modo consigliato per alleviare questo problema consiste nell'aggiungere ulteriore larghezza di banda. Se non è possibile aggiungere più larghezza di banda, potrebbe essere necessario implementare invece la qualità del servizio.

Skype for Business Server offre supporto completo per la qualità del servizio: ciò significa che le organizzazioni che utilizzano già QoS possono integrare facilmente Skype for Business Server nell'infrastruttura di rete esistente. A tale scopo, è necessario eseguire le attività seguenti:

  - [Abilitazione di QoS per i dispositivi che non sono basati su Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Per impostazione predefinita, QoS è disabilitata per i computer e altri dispositivi (ad esempio iPhones) che eseguono altri sistemi operativi. Anche se è possibile utilizzare Skype for Business Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non è possibile utilizzare il prodotto per modificare i codici DSCP utilizzati da questi dispositivi.

  - [Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i servizi di conferenza, applicazione e Mediation Server](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). È necessario riservare un insieme univoco di porte per diversi tipi di pacchetti, ad esempio audio e video. Con Skype for Business Server non è possibile abilitare o disabilitare la qualità del servizio, ad esempio, l'impostazione di un valore della proprietà su true o su false. In alternativa, è possibile abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo. Se in seguito si decide di non utilizzare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo corretti.

  - [Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i server perimetrali](configuring-port-ranges-for-your-edge-servers.md). Sebbene non sia necessario, è possibile configurare i server perimetrali in modo che utilizzino gli stessi intervalli di porte degli altri server. La configurazione di un criterio di qualità del servizio deve essere svolta solo per il lato interno dei server perimetrali. Ciò è dovuto al fatto che la qualità del servizio è progettata per essere utilizzata sulla rete interna e non su Internet.

- [Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i client in Skype for Business Server](configuring-port-ranges-for-your-skype-clients.md)  Questi intervalli di porte si applicano solo ai computer client e in genere sono diversi dagli intervalli di porte configurati nei server. Si noti che Skype for Business Server non supporta QoS per i sistemi operativi Windows diversi da Windows 10.


