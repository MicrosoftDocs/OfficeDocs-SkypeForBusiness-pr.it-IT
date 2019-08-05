---
title: Gestire gli aggiornamenti di Windows per Microsoft teams rooms
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gestire gli aggiornamenti di Windows per Microsoft teams rooms
ms.openlocfilehash: 4ac80404acf507cafa038fe6a0cf667621f5b798
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182329"
---
# <a name="manage-windows-updates"></a>Gestire gli aggiornamenti di Windows

Microsoft teams Rooms viene eseguito in Windows 10 Enterprise o Windows 10 Enterprise (contratto multilicenza) e riceve gli stessi aggiornamenti di Windows e le build del sistema operativo come desktop standard.

Gli aggiornamenti di Windows possono essere gestiti in diversi modi:

## <a name="hands-off-approach"></a>Approccio hands-off 
- Gli aggiornamenti possono essere scaricati direttamente dagli aggiornamenti di Windows automaticamente e installati durante le ore lavorative. Se non viene apportata alcuna modifica alla configurazione, si tratta dello stato predefinito.
- Gli aggiornamenti non rinviabili installeranno automaticamente il giorno-uno del rilascio. 
- Gli aggiornamenti e i driver di qualità verranno scaricati e installati automaticamente in un giorno. 
- Aggiornamenti delle caratteristiche. Vedere altre note seguenti. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Aggiornamenti di Windows per le aziende](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO o Intune)   
- Gli aggiornamenti vengono scaricati da WU o da WSUS, ma con ritardi configurati oltre la data di rilascio originale della Knowledge base. 
- In combinazione con più criteri per le UO o i filtri filtrati, questo consente la creazione di "anelli" di distribuzione, in cui gli amministratori possono specificare i dispositivi prima di installare gli aggiornamenti di qualità e quelli che verranno installati in un secondo momento. In questo modo è possibile eseguire test di affidabilità e prestazioni su un sottoinsieme di sistemi prima di distribuire gli aggiornamenti in tutta la distribuzione senza l'overhead di gestire gli aggiornamenti di Windows in SCCM ad esempio.
- Gli aggiornamenti di WSUS e Windows per le aziende possono essere configurati [contemporaneamente](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) se si vuole consentire la gestione della larghezza di banda e il controllo degli aggiornamenti di Windows per le aziende.
- Aggiornamenti delle caratteristiche. Vedere altre note seguenti.

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Molto simile a Windows Update for business, ma con l'opzione aggiuntiva di destinazione di KB specifici all'interno di ogni "Ring" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, anziché basarsi solo su un ritardo. 
- Aggiornamenti delle caratteristiche. Vedere altre note seguenti.


### <a name="feature-updates"></a>Aggiornamenti delle caratteristiche

A differenza degli aggiornamenti di qualità e non rinviabili, Windows 10 "aggiornamenti delle funzionalità" (versioni principali del sistema operativo) verrà installato solo dopo che Microsoft verifica e convalida una determinata funzionalità degli aggiornamenti con le sale di Microsoft teams. Anche se viene rilasciata sul canale semestrale (o mirata se si dispone di sistemi impostati su quel canale per il testing) o anche manualmente spinto da propri tentativi o configurazioni, non consentirà l'installazione finché non viene rimosso il blocco alla fine.

Microsoft teams room "out-of-box", con l'approccio hands off, non installa un Windows Update o riavvia un dispositivo automaticamente a causa di un Windows Update. I sistemi possono tuttavia scaricare un aggiornamento e attendere il riavvio successivo per installarlo. A meno che non venga riavviato manualmente, l'installazione deve avvenire durante il riavvio automatico notturno. Gli aggiornamenti di Windows devono essere trasparenti nella sala, ma l'interfaccia utente non deve mai essere interrotta dagli aggiornamenti di Windows.

Se si sceglie di partecipare al dominio, usare SCCM o WSUS e prestare particolare attenzione ai criteri o alle azioni che potrebbero portare il dispositivo a installare un aggiornamento o a forzare un riavvio durante l'orario di ufficio. Se si hanno sistemi nel riavvio della distribuzione durante l'uso o l'avviso sugli aggiornamenti di Windows nell'interfaccia utente, è necessario esaminare la configurazione.