---
title: Gestire gli aggiornamenti di Windows per Microsoft teams rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Gestire gli aggiornamenti di Windows per Microsoft teams rooms
ms.openlocfilehash: 87aab8b4c0d299b682f450d6d53ace33fc7a464b
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269041"
---
# <a name="manage-windows-updates"></a>Gestire gli aggiornamenti di Windows

Microsoft teams Rooms viene eseguito in Windows 10 Enterprise o Windows 10 Enterprise (contratto multilicenza) e riceve gli stessi aggiornamenti di Windows e le build del sistema operativo come computer desktop standard.

Gli aggiornamenti di Windows possono essere gestiti come descritto nelle sezioni seguenti:

## <a name="hands-off-approach"></a>Approccio hands-off 

- Per impostazione predefinita, gli aggiornamenti vengono scaricati direttamente dagli aggiornamenti di Windows automaticamente e installati durante le ore lavorative.
- Gli aggiornamenti non differibili installano il giorno-uno della versione automatica.
- Gli aggiornamenti di qualità e i driver scaricano e installano automaticamente un giorno.
- Aggiornamenti delle caratteristiche. Vedere le note seguite.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Aggiornamenti di Windows per le aziende (GPO o Intune)  

- Download [di Windows Updates for business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- Gli aggiornamenti vengono scaricati da Windows Update o da WSUS, ma con ritardi configurati oltre la data di rilascio originale.
- È possibile usare più unità organizzative o filtri filtrati per creare "anelli" di distribuzione in cui gli amministratori possono specificare i dispositivi prima di installare gli aggiornamenti di qualità e quelli installati in un secondo momento. L'affidabilità e le prestazioni possono essere testate su un sottoinsieme di sistemi prima di distribuire gli aggiornamenti in tutta la distribuzione senza l'overhead di gestire gli aggiornamenti di Windows in SCCM.
- Gli aggiornamenti di WSUS e Windows per le aziende possono essere [configurati contemporaneamente](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) se si vuole che la gestione della larghezza di banda e il controllo vengano forniti dagli aggiornamenti di Windows per le aziende.
- Aggiornamenti delle caratteristiche. Vedere le note seguite.

## <a name="wsussccm"></a>WSUS/SCCM

- Download di [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Molto simile a Windows Update for business, ma con l'opzione aggiuntiva di destinazione di KB specifici all'interno di ogni "Ring" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, anziché basarsi solo su un ritardo.
- Aggiornamenti delle caratteristiche. Vedere le note seguite.

### <a name="feature-updates"></a>Aggiornamenti delle caratteristiche

A differenza degli aggiornamenti di qualità e non differibili, gli aggiornamenti delle funzionalità di Windows 10 (Major OS release) verranno installati solo dopo che Microsoft verifica e convalida una determinata funzionalità degli aggiornamenti con le sale di Microsoft teams. Anche se l'aggiornamento viene rilasciato sul canale semestrale (o mirato se si dispone di sistemi impostati su tale canale per il testing) o manualmente, un dispositivo Microsoft room Systems non consentirà l'installazione dell'aggiornamento non testato.

Microsoft teams Rooms funziona "out-of-box" con un approccio hands-off e non installa un Windows Update o riavvia automaticamente un dispositivo per Windows Update. I sistemi scaricano un aggiornamento e attendono il riavvio successivo per installarlo. A meno che qualcuno non lo riavvii manualmente, l'installazione avviene solo durante il riavvio notturno automatico. Gli aggiornamenti di Windows devono essere trasparenti nella sala e il normale funzionamento non deve mai essere interrotto dagli aggiornamenti di Windows.

Se si sceglie di accedere ai dispositivi di dominio, usare SCCM o WSUS. Prestare particolare attenzione ai criteri o alle azioni che causano l'aggiornamento di un dispositivo o il riavvio forzato durante le ore lavorative. I sistemi della distribuzione non devono essere riavviati durante l'uso o l'avviso relativo agli aggiornamenti di Windows sull'interfaccia utente durante le ore di utilizzo, rivedere la configurazione se si verifica questo comportamento.