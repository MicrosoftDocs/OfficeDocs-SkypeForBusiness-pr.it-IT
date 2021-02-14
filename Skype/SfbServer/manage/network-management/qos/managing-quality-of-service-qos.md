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
description: QoS (Quality of Service) è una tecnologia di rete utilizzata in alcune organizzazioni per offrire un'esperienza utente finale ottimale per le comunicazioni audio e video.
ms.openlocfilehash: 77fae69a6ceeaf65f80dd38e78e42e186786c4ed
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814156"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gestione della qualità del servizio (QoS) in Skype for Business Server


QoS (Quality of Service) è una tecnologia di rete utilizzata in alcune organizzazioni per offrire un'esperienza utente finale ottimale per le comunicazioni audio e video. QoS viene in genere utilizzato nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete in concorrenza per una quantità relativamente ridotta di larghezza di banda disponibile, La qualità del servizio consente agli amministratori di assegnare priorità più elevate ai pacchetti che trasportano dati audio o video. Fornendo a questi pacchetti una priorità più alta, è probabile che le comunicazioni audio e video si completino più velocemente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni quali trasferimenti di file, esplorazione Web o backup dei database. Questo perché ai pacchetti di rete utilizzati per i trasferimenti di file o per i backup dei database viene assegnata una priorità di "impegno ottimale".


> [!NOTE]  
> Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione nella rete interna. Quando si implementa QoS, si configurano i server e i router per supportare il contrassegno dei pacchetti; Tuttavia, è possibile configurare questi dispositivi in modo da supportare il contrassegno dei pacchetti in modo specifico. Non è possibile presupporre che la qualità del servizio sia supportata su Internet o su altre reti. Anche se il servizio è supportato su altre reti, non è garantito che QoS verrà configurato nello stesso modo in cui è stato configurato il servizio nella rete.

Skype for Business Server non richiede la qualità del servizio; se attualmente non si usa QoS, non è necessario installare il servizio prima di installare Skype for Business Server. Se si verifica una notevole perdita di pacchetti nella rete, il modo consigliato per ridurre questo problema è aggiungere ulteriore larghezza di banda. Se non è possibile aggiungere più larghezza di banda, è consigliabile implementare la qualità del servizio.

Skype for Business Server offre il supporto completo per la qualità del servizio: ciò significa che le organizzazioni che già usano QoS possono integrare facilmente Skype for Business Server nell'infrastruttura di rete esistente. A tale scopo, è necessario eseguire le attività seguenti:

  - [Abilitazione di QoS per i dispositivi non basati su Windows.](enabling-qos-for-devices-that-are-not-based-on-windows.md) Per impostazione predefinita, QoS è disabilitato per computer e altri dispositivi (ad esempio iPhone) che eseguono altri sistemi operativi. Sebbene sia possibile utilizzare Skype for Business Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non è possibile utilizzare il prodotto per modificare i codici DSCP utilizzati da questi dispositivi.

  - [Configurazione degli intervalli di porte e dei criteri qualità del servizio](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)per i server per conferenze, applicazioni e Mediation Server. È necessario riservare un set univoco di porte per tipi di pacchetti diversi, ad esempio audio e video. Con Skype for Business Server non è possibile abilitare o disabilitare la qualità del servizio impostando, ad esempio, un valore di proprietà su True o su False. È invece possibile abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando Criteri di gruppo. Se successivamente si decide di non utilizzare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo appropriati.

  - [Configurazione degli intervalli di porte e dei criteri qualità del servizio per i server perimetrali.](configuring-port-ranges-for-your-edge-servers.md) Anche se non è necessario, è possibile configurare i server perimetrali in modo che utilizzino gli stessi intervalli di porte degli altri server. La configurazione di un criterio qualità del servizio deve essere eseguita solo per il lato interno dei server perimetrali. Questo perché la qualità del servizio è progettata per l'utilizzo nella rete interna e non in Internet.

- [Configurazione degli intervalli di porte e dei criteri qualità del servizio per i client in Skype for Business Server](configuring-port-ranges-for-your-skype-clients.md)  Questi intervalli di porte si applicano solo ai computer client e in genere sono diversi dagli intervalli di porte configurati nei server. Skype for Business Server non supporta QoS per sistemi operativi Windows diversi da Windows 10.


