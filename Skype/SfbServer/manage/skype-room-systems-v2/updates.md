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
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832876"
---
# <a name="manage-windows-updates"></a>Gestire gli aggiornamenti di Windows

Microsoft Teams Rooms viene eseguito su Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) e riceve le stesse build del sistema operativo e degli aggiornamenti di Windows come desktop standard.

Gli aggiornamenti di Windows possono essere gestiti in diversi modi:

## <a name="hands-off-approach"></a>Approccio hands-off 
- Gli aggiornamenti possono essere scaricati direttamente dagli aggiornamenti di Windows automaticamente e installati durante le ore non lavorative. Se non viene apportata alcuna modifica alla configurazione, questo è lo stato predefinito.
- Gli aggiornamenti non rinviabili installeranno automaticamente il primo giorno del rilascio. 
- Gli aggiornamenti qualitativi e i driver scaricheranno e installeranno automaticamente il primo giorno. 
- Aggiornamenti delle funzionalità. Vedi altre note di seguito. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Aggiornamenti di Windows per le aziende](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (oggetto Criteri di gruppo o Intune)   
- Gli aggiornamenti vengono scaricati da Wu o wsus, ma con ritardi configurati oltre la data di rilascio originale della Kb. 
- In combinazione con più criteri di unità organizzative o filtrati, ciò consente la creazione di "anelli" di distribuzione, in cui gli amministratori possono specificare quali dispositivi installano prima gli aggiornamenti qualitativi e quali verranno installati in un secondo momento. In questo modo è possibile testare l'affidabilità e le prestazioni in un sottoinsieme di sistemi prima di eseguire l'implementazione degli aggiornamenti nell'intera distribuzione senza il sovraccarico della gestione degli aggiornamenti di Windows in Microsoft Endpoint Configuration Manager, ad esempio.
- WSUS e gli aggiornamenti [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) di Windows per le aziende possono essere configurati contemporaneamente se desideri sia la gestione della larghezza di banda che il controllo fornito da Windows Updates for Business.
- Aggiornamenti delle funzionalità. Vedi altre note di seguito.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Proprio come Windows Update per le aziende, ma con l'opzione aggiuntiva di selezionare kb specifiche all'interno di ogni "anello" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, anziché basarsi solo su un ritardo. 
- Aggiornamenti delle funzionalità. Vedi altre note di seguito.


### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

A differenza degli aggiornamenti qualitativi e non rinviabili, gli "aggiornamenti delle funzionalità" di Windows 10 (versioni principali del sistema operativo) verranno installati solo dopo i test di Microsoft e la convalida di una determinata funzionalità di aggiornamento con Microsoft Teams Rooms. Anche se viene rilasciato al canale Semi-Annual (o mirato se hai sistemi impostati su tale canale per i test) o anche manualmente spinti dai tuoi tentativi o configurazioni, l'installazione non sarà consentita fino a quando il blocco sul nostro end non verrà rimosso.

Microsoft Teams Room "out-of-box", con l'approccio hands off, non installerà un Windows Update o riavvierà automaticamente un dispositivo a causa di un Windows Update. I sistemi possono tuttavia scaricare un aggiornamento e attendere il successivo riavvio per installarlo. A meno che qualcuno non la riavvii manualmente, l'installazione deve avvenire al riavvio automatico notturno. Gli aggiornamenti di Windows devono essere trasparenti nella sala riunioni, l'interfaccia utente non deve mai essere interrotta dagli aggiornamenti di Windows.

Se scegli di aggiungere un dominio, usa Microsoft Endpoint Configuration Manager o WSUS e presta particolare attenzione ai criteri o alle azioni che potrebbero causare l'installazione di un aggiornamento nel dispositivo o la forzatura di un riavvio durante l'orario di ufficio. Se nella distribuzione sono presenti sistemi che si riavviano durante l'uso o che inviano avvisi sugli aggiornamenti di Windows tramite l'interfaccia utente, è necessario esaminare la configurazione.
