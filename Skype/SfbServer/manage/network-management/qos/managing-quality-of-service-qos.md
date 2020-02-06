---
title: Gestione della qualità del servizio (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La qualità del servizio (QoS) è una tecnologia di rete usata in alcune organizzazioni per offrire un'esperienza ottimale per l'utente finale per le comunicazioni audio e video.
ms.openlocfilehash: 821ebb1cd6a101856f4fbc4fb3428ecba7674245
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817362"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gestire la qualità del servizio (QoS) in Skype for Business Server


La qualità del servizio (QoS) è una tecnologia di rete usata in alcune organizzazioni per offrire un'esperienza ottimale per l'utente finale per le comunicazioni audio e video. Il QoS viene usato più comunemente nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete che competono per una quantità relativamente piccola di larghezza di banda disponibile, la qualità del servizio consente agli amministratori di assegnare priorità più alte ai pacchetti trasporto di dati audio o video. Assegnando a questi pacchetti una priorità più alta, le comunicazioni audio e video possono essere completate più rapidamente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come i trasferimenti di file, la navigazione web o i backup di database. Il motivo è che i pacchetti di rete usati per i trasferimenti di file o i backup di database hanno la priorità "migliore sforzo".


> [!NOTE]  
> Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione nella rete interna. Quando si implementa QoS, si configurano i server e i router per supportare il contrassegno dei pacchetti. Tuttavia, configuri questi dispositivi per supportare il contrassegno dei pacchetti in modo particolare. Non si può presupporre che la qualità del servizio sarà supportata su Internet o su altre reti. Anche se la qualità se il servizio è supportato in altre reti, non c'è alcuna garanzia che la QoS venga configurata allo stesso modo in cui il servizio è stato configurato nella rete.

Skype for Business Server non richiede la qualità del servizio; Se attualmente non si usa QoS, non è necessario installare il servizio prima di installare Skype for Business Server. Se si verifica una notevole quantità di perdita di pacchetti nella rete, il metodo consigliato per alleviare questo problema consiste nell'aggiungere ulteriore larghezza di banda. Se non è possibile aggiungere più larghezza di banda, è consigliabile implementare invece la qualità del servizio.

Skype for Business Server offre il supporto completo per la qualità del servizio: ciò significa che le organizzazioni che già usano QoS possono integrare facilmente Skype for Business Server nell'infrastruttura di rete esistente. A tale scopo, è necessario eseguire le attività seguenti:

  - [Abilitazione di QoS per i dispositivi che non sono basati su Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Per impostazione predefinita, QoS è disabilitato per i computer e altri dispositivi (ad esempio iPhone) che eseguono altri sistemi operativi. Anche se puoi usare Skype for Business Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non puoi usare il prodotto per modificare i codici DSCP usati da questi dispositivi.

  - [Configurazione di intervalli di porte e criteri di qualità dei servizi per i server di conferenza, applicazione e mediazione](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). È necessario prenotare un set di porte univoco per tipi di pacchetto diversi, ad esempio audio e video. Con Skype for Business Server non è possibile abilitare o disabilitare la qualità del servizio, ad esempio, impostando un valore di proprietà su true o su false. Puoi invece abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo. Se in seguito si decide di non usare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo appropriati.

  - [Configurazione di intervalli di porte e di criteri di qualità dei servizi per i server perimetrali](configuring-port-ranges-for-your-edge-servers.md). Anche se non è necessario, è possibile configurare gli Edge Server in modo da usare gli stessi intervalli di porte degli altri server. La configurazione di un criterio di qualità dei servizi deve essere eseguita solo per il lato interno degli Edge Server. Questo perché la qualità del servizio è progettata per l'uso nella rete interna e non in Internet.

- [Configurazione di intervalli di porte e di criteri di qualità dei servizi per i clienti in Skype for Business Server](configuring-port-ranges-for-your-skype-clients.md)  Questi intervalli di porte si applicano solo ai computer client e sono in genere diversi dagli intervalli di porte configurati nei server. Tieni presente che Skype for Business Server non supporta QoS per sistemi operativi Windows diversi da Windows 10.


