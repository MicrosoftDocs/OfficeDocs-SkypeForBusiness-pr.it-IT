---
title: Gestire gli aggiornamenti di Windows per le sale di Microsoft Teams
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
description: Gestire gli aggiornamenti di Windows per le sale di Microsoft Teams
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832876"
---
# <a name="manage-windows-updates"></a>Gestire gli aggiornamenti di Windows

Le sale di Microsoft teams vengono eseguite su Windows 10 Enterprise o Windows 10 Enterprise (VL) e ricevono gli stessi aggiornamenti di Windows e le build del sistema operativo come desktop standard.

Gli aggiornamenti di Windows possono essere gestiti in pochi modi diversi:

## <a name="hands-off-approach"></a>Approccio pratico 
- Gli aggiornamenti possono essere scaricati direttamente dagli aggiornamenti di Windows automaticamente e installati durante le ore di disattivazione. Se non viene apportata alcuna modifica alla configurazione, questo è lo stato predefinito.
- Gli aggiornamenti non rinviabili installeranno il giorno-1 del rilascio automaticamente. 
- Gli aggiornamenti e i driver di qualità scaricheranno automaticamente e installeranno il primo giorno. 
- Aggiornamenti delle funzionalità. Vedere altre note in basso. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Aggiornamenti di Windows per le aziende](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO o Intune)   
- Gli aggiornamenti vengono scaricati da WU o da WSUS, ma con ritardi configurati oltre la data di rilascio originale della KB. 
- In combinazione con più criteri di unità organizzativa o filtrati, questo consente la creazione di "anelli" di distribuzione, in cui gli amministratori possono specificare i dispositivi che installino prima gli aggiornamenti della qualità e quali verranno installati in un secondo momento. In questo modo è possibile testare l'affidabilità e le prestazioni su un sottoinsieme di sistemi prima di distribuire gli aggiornamenti nell'intera distribuzione senza l'overhead di gestire gli aggiornamenti di Windows in Microsoft endpoint Configuration Manager, ad esempio.
- È possibile configurare WSUS e gli aggiornamenti di Windows per [le](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) aziende contemporaneamente se si desidera che sia disponibile sia la gestione della larghezza di banda sia il controllo relativo agli aggiornamenti di Windows per le aziende.
- Aggiornamenti delle funzionalità. Vedere altre note in basso.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Analogamente a Windows Update for business, ma con l'opzione aggiuntiva di indirizzare specifici KB all'interno di ogni "anello" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito singolarmente e testato a volontà, anziché basarsi solo su un ritardo. 
- Aggiornamenti delle funzionalità. Vedere altre note in basso.


### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

A differenza degli aggiornamenti di qualità e non rinviabili, Windows 10 "aggiornamenti delle funzionalità" (Major OS releases) viene installato solo dopo che Microsoft ha testato e convalidato una determinata funzionalità degli aggiornamenti con le sale di Microsoft teams. Anche se viene rilasciata nel canale Semi-Annual (o mirata se si dispone di sistemi impostati su quel canale per il testing) o addirittura spinto manualmente dai propri tentativi o configurazioni, non consentirà l'installazione fino a quando non viene rimosso il blocco alla fine.

La sala Microsoft Teams "out-of-box", utilizzando l'approccio delle mani disattivate, non installerà un Windows Update o riavvierà un dispositivo automaticamente a causa di un aggiornamento di Windows. Tuttavia, i sistemi possono scaricare un aggiornamento e attendere il riavvio successivo per installarlo. A meno che qualcuno non lo riavvii manualmente, l'installazione dovrebbe avvenire al riavvio automatico notturno. Gli aggiornamenti di Windows devono essere trasparenti nella sala, l'interfaccia utente non deve mai essere interrotta dagli aggiornamenti di Windows.

Se si sceglie di aggiungere domini, utilizzare Gestione configurazione endpoint Microsoft o WSUS e prestare particolare attenzione ai criteri o alle azioni che potrebbero causare l'installazione di un aggiornamento o la forzatura di un riavvio durante l'orario di ufficio. Se si dispone di sistemi nel riavvio della distribuzione durante l'utilizzo o gli avvisi relativi agli aggiornamenti di Windows sull'interfaccia utente, sarà necessario esaminare la configurazione.
