---
title: Gestire gli aggiornamenti di Windows per Microsoft Teams Rooms
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gestire gli aggiornamenti di Windows per Microsoft Teams Rooms
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103202"
---
# <a name="manage-windows-updates"></a>Gestire gli aggiornamenti di Windows

Microsoft Teams Rooms viene eseguito su Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) e riceve le stesse build del sistema operativo e degli aggiornamenti di Windows come desktop standard.

Gli aggiornamenti di Windows possono essere gestiti in diversi modi:

## <a name="hands-off-approach"></a>Approccio hands-off 
- Gli aggiornamenti possono essere scaricati direttamente dagli aggiornamenti di Windows automaticamente e installati durante le ore non lavorative. Se non viene apportata alcuna modifica alla configurazione, questo è lo stato predefinito.
- Gli aggiornamenti non rinviabili installeranno automaticamente il primo giorno del rilascio. 
- Gli aggiornamenti qualitativi e i driver verranno scaricati e installati automaticamente il primo giorno. 
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Aggiornamenti di Windows per le aziende](/windows/deployment/update/waas-manage-updates-wufb) (oggetto Criteri di gruppo o Intune)   
- Gli aggiornamenti vengono scaricati da WU o WSUS, ma con ritardi configurati oltre la data di rilascio originale della KB. 
- In combinazione con più criteri dell'unità organizzativa o filtrati, ciò consente la creazione di "anelli" di distribuzione, in cui gli amministratori possono specificare quali dispositivi installano prima gli aggiornamenti qualitativi e quali verranno installati in un secondo momento. In questo modo è possibile testare l'affidabilità e le prestazioni in un sottoinsieme di sistemi prima di eseguire aggiornamenti nell'intera distribuzione, ad esempio senza l'overhead della gestione degli aggiornamenti di Windows in Microsoft Endpoint Configuration Manager.
- WSUS e Gli aggiornamenti [](/windows/deployment/update/waas-integrate-wufb) di Windows per le aziende possono essere configurati contemporaneamente se si desidera sia la gestione della larghezza di banda che il controllo fornito da Windows Updates for Business.
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Molto simile a Windows Update per le aziende, ma con l'opzione aggiuntiva di selezionare kb specifiche all'interno di ogni "anello" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, anziché basarsi solo su un ritardo. 
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito.


### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

A differenza degli aggiornamenti qualitativi e non rimandabili, gli "aggiornamenti delle funzionalità" di Windows 10 (versioni principali del sistema operativo) verranno installati solo dopo che Microsoft ha verificato e convalidato una determinata funzionalità di aggiornamento con Microsoft Teams Rooms. Anche se viene rilasciato al canale Semi-Annual (o Mirato se hai sistemi impostati su tale canale per il test) o anche manualmente spinti dai tuoi tentativi o configurazioni, l'installazione non sarà consentita fino a quando il blocco alla fine non verrà rimosso.

Microsoft Teams Room "out-of-box", con l'approccio hands off, non installerà un Windows Update o riavvierà automaticamente un dispositivo a causa di un Windows Update. I sistemi possono tuttavia scaricare un aggiornamento e attendere il riavvio successivo per installarlo. A meno che qualcuno non lo riavvii manualmente, l'installazione deve avvenire al riavvio automatico notturno. Gli aggiornamenti di Windows devono essere trasparenti nella sala, l'interfaccia utente non deve mai essere interrotta dagli aggiornamenti di Windows.

Se scegli di aggiungere un dominio, usa Microsoft Endpoint Configuration Manager o WSUS e presta particolare attenzione ai criteri o alle azioni che potrebbero causare l'installazione di un aggiornamento o l'esecuzione di un riavvio durante l'orario di ufficio. Se nella distribuzione sono presenti sistemi che si riavviano durante l'uso o che avvisano gli aggiornamenti di Windows tramite l'interfaccia utente, è necessario esaminare la configurazione.