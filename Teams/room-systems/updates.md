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
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243279"
---
# <a name="manage-windows-updates"></a>Gestire gli aggiornamenti di Windows

Microsoft teams Rooms viene eseguito in Windows 10 Enterprise o Windows 10 Enterprise (contratto multilicenza) e riceve gli stessi aggiornamenti di Windows e le build del sistema operativo come desktop standard.

Gli aggiornamenti di Windows possono essere gestiti in diversi modi:

## <a name="hands-off-approach"></a>Approccio hands-off 

- Gli aggiornamenti possono essere scaricati direttamente dagli aggiornamenti di Windows automaticamente e installati durante le ore lavorative. Questa è la configurazione predefinita.
- Gli aggiornamenti non differibili installano il giorno-uno della versione automatica.
- Gli aggiornamenti di qualità e i driver scaricano e installano automaticamente un giorno.
- Aggiornamenti delle caratteristiche. Vedere le note seguite.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Aggiornamenti di Windows per le aziende (GPO o Intune)  

- Download [di Windows Updates for business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- Gli aggiornamenti vengono scaricati da WU o da WSUS, ma con ritardi configurati oltre la data di rilascio originale della Knowledge base.
- Usato con più criteri per le UO o i filtri filtrati, è possibile creare "anelli" di distribuzione in cui gli amministratori possono specificare i dispositivi prima di installare gli aggiornamenti di qualità e quelli che vengono installati in seguito. In questo modo è possibile eseguire test di affidabilità e prestazioni su un sottoinsieme di sistemi prima di distribuire gli aggiornamenti in tutta la distribuzione senza l'overhead di gestire gli aggiornamenti di Windows in SCCM ad esempio.
- Gli aggiornamenti di WSUS e Windows per le aziende possono essere configurati [contemporaneamente](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) se si vuole che la gestione della larghezza di banda e il controllo vengano forniti dagli aggiornamenti di Windows per le aziende.
- Aggiornamenti delle caratteristiche. Vedere le note seguite.

## <a name="wsussccm"></a>WSUS/SCCM

- Download di [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Molto simile a Windows Update for business, ma con l'opzione aggiuntiva di destinazione di KB specifici all'interno di ogni "Ring" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, anziché basarsi solo su un ritardo.
- Aggiornamenti delle caratteristiche. Vedere le note seguite.

### <a name="feature-updates"></a>Aggiornamenti delle caratteristiche

A differenza degli aggiornamenti di qualità e non differibili, gli aggiornamenti delle funzionalità di Windows 10 (Major OS release) verranno installati solo dopo che Microsoft verifica e convalida una determinata funzionalità degli aggiornamenti con le sale di Microsoft teams. Anche se l'aggiornamento viene rilasciato sul canale semestrale (o mirato se si dispone di sistemi impostati su tale canale per il testing) o manualmente, un dispositivo Microsoft room Systems non consentirà l'installazione dell'aggiornamento non testato.

Microsoft teams Rooms "out-of-box", con l'approccio hands off, non installa un Windows Update o riavvia automaticamente un dispositivo per un Windows Update. I sistemi possono scaricare un aggiornamento e attendere il riavvio successivo per installarlo. A meno che non venga riavviato manualmente, l'installazione deve avvenire durante il riavvio automatico notturno. Gli aggiornamenti di Windows devono essere trasparenti nella sala, ma l'interfaccia utente non deve mai essere interrotta dagli aggiornamenti di Windows.

Se si sceglie di eseguire il dominio in dispositivi collegati, usare SCCM o WSUS. Prestare particolare attenzione ai criteri o alle azioni che potrebbero causare l'installazione di un aggiornamento o la forzatura di un riavvio durante l'orario di ufficio. I sistemi della distribuzione non devono essere riavviati durante l'uso o l'avviso relativo agli aggiornamenti di Windows sull'interfaccia utente durante le ore di utilizzo, rivedere la configurazione se si verifica questo comportamento.