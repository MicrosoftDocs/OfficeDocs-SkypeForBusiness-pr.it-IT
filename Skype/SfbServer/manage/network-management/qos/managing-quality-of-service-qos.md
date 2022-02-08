---
title: Gestione della qualità del servizio (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: QoS (Quality of Service) è una tecnologia di rete utilizzata in alcune organizzazioni per offrire un'esperienza ottimale per gli utenti finali per le comunicazioni audio e video.
ms.openlocfilehash: 043d29eea849ffbd534199a6622b35e2322f7044
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390118"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gestione della qualità del servizio (QoS) in Skype for Business Server


QoS (Quality of Service) è una tecnologia di rete utilizzata in alcune organizzazioni per offrire un'esperienza ottimale per gli utenti finali per le comunicazioni audio e video. QoS viene utilizzato più comunemente nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete in competizione per una quantità relativamente piccola di larghezza di banda disponibile, Quality of Service consente agli amministratori di assegnare priorità più elevate ai pacchetti che trasportano dati audio o video. Dando a questi pacchetti una priorità più alta, è probabile che le comunicazioni audio e video si completino più velocemente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni quali trasferimenti di file, esplorazione Web o backup di database. Ciò è dovuto al fatto che ai pacchetti di rete utilizzati per i trasferimenti di file o i backup dei database viene assegnata una priorità di "sforzo ottimale".


> [!NOTE]  
> Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione nella rete interna. Quando si implementa QoS, si configurano i server e i router per supportare il contrassegno dei pacchetti. tuttavia, si configurano questi dispositivi per supportare il contrassegno dei pacchetti in un modo particolare. Non è possibile presupporre che la qualità del servizio sia supportata in Internet o in altre reti. Anche se Qualità se il servizio è supportato in altre reti, non vi è alcuna garanzia che QoS verrà configurato nello stesso modo in cui è stato configurato il servizio nella rete.

Skype for Business Server non richiede qualità del servizio. Se attualmente non si utilizza QoS, non è necessario installare il servizio prima di installare Skype for Business Server. Se si verifica una notevole perdita di pacchetti nella rete, il modo consigliato per alleviare questo problema è aggiungere ulteriore larghezza di banda. Se non è possibile aggiungere più larghezza di banda, è consigliabile implementare la qualità del servizio.

Skype for Business Server offre il supporto completo per la qualità del servizio: ciò significa che le organizzazioni che usano già QoS possono facilmente integrare Skype for Business Server nell'infrastruttura di rete esistente. A tale scopo, è necessario eseguire le attività seguenti:

  - [Abilitazione di QoS per i dispositivi non basati su Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Per impostazione predefinita, QoS è disabilitato per computer e altri dispositivi (ad esempio iPhone) che eseguono altri sistemi operativi. Anche se puoi usare Skype for Business Server per abilitare e disabilitare qualità del servizio per i dispositivi, in genere non puoi usare il prodotto per modificare i codici DSCP usati da questi dispositivi.

  - [Configurazione degli intervalli di porte e dei criteri qualità del servizio per i server per conferenze, applicazioni e Mediation Server](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). È necessario riservare un set univoco di porte per tipi di pacchetti diversi, ad esempio audio e video. Con Skype for Business Server non si abilita o disabilita qualità del servizio impostando un valore di proprietà su True o su False. È invece possibile abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando Criteri di gruppo. Se in seguito si decide di non utilizzare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo appropriati.

  - [Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i server perimetrali](configuring-port-ranges-for-your-edge-servers.md). Anche se non è necessario, è possibile configurare i server Perimetrali in modo che utilizzino gli stessi intervalli di porte degli altri server. La configurazione di un criterio qualità del servizio deve essere eseguita solo per il lato interno dei server perimetrali. Questo perché La qualità del servizio è progettata per l'utilizzo nella rete interna e non in Internet.

- [Configurazione degli intervalli](configuring-port-ranges-for-your-skype-clients.md) di porte e dei criteri qualità del servizio per i client in Skype for Business Server Questi intervalli di porte si applicano solo ai computer client e in genere sono diversi dagli intervalli di porte configurati nei server. Tenere presente Skype for Business Server non supporta QoS per Windows sistemi operativi diversi da Windows 10.


