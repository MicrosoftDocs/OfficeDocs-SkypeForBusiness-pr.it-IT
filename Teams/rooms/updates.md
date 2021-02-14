---
title: Gestire gli aggiornamenti di Windows per le sale di Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: L'amministratore può imparare a gestire gli aggiornamenti di Windows e gli aggiornamenti delle funzionalità di Windows per le sale di Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e52c1fdf3bb35be6869320aa57e6f5aff5fd0773
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905308"
---
# <a name="manage-windows-updates"></a>Gestire gli aggiornamenti di Windows

Microsoft Teams Rooms viene eseguito in Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) e riceve le stesse build di Windows Updates e OS di un computer desktop standard.

Gli aggiornamenti di Windows possono essere gestiti come descritto nelle sezioni seguenti:

## <a name="hands-off-approach"></a>Approccio hands-off 

- Per impostazione predefinita, gli aggiornamenti vengono scaricati direttamente dagli aggiornamenti di Windows automaticamente e installati durante gli orari non lavorativi.
- Gli aggiornamenti non deferrable vengono installati automaticamente dal primo giorno del rilascio.
- Gli aggiornamenti qualitativi e i driver scaricano e installano automaticamente il primo giorno.
- Aggiornamenti delle caratteristiche. Vedere le note seguenti.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Aggiornamenti di Windows per le aziende (GPO o Intune)  

- [Download di Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- Gli aggiornamenti vengono scaricati da Windows Update o Windows Server Update Services, ma con ritardi configurati oltre la data di rilascio originale.
- È possibile usare più unità organizzative o criteri filtrati per creare "anelli" di distribuzione in cui gli amministratori possono specificare quali dispositivi installare per primi gli aggiornamenti qualitativi e quali in un secondo momento. L'affidabilità e le prestazioni possono essere testate in un sottoinsieme di sistemi prima di distribuzione degli aggiornamenti nell'intera distribuzione senza l'overhead della gestione degli aggiornamenti di Windows in Configuration Manager.
- Windows Update Services e [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) Windows Update for Business possono essere configurati contemporaneamente, se si desidera la gestione della larghezza di banda e il controllo fornito da Windows Updates for Business.
- Aggiornamenti delle caratteristiche. Vedere le note seguenti.

## <a name="wsusconfiguration-manager"></a>Windows Server Update Services/Configuration Manager

- [Download di Windows Server Update Services/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Come Windows Update per le aziende, ma con la possibilità aggiuntiva di mirare kb specifiche all'interno di ogni "anello" o nell'intera distribuzione. Ogni aggiornamento può essere distribuito singolarmente e testato a p pmento, invece di affidarsi solo a un ritardo.
- Aggiornamenti delle caratteristiche. Vedere le note seguenti.

### <a name="feature-updates"></a>Aggiornamenti delle caratteristiche

A differenza degli aggiornamenti di qualità e non Deferrable, gli "aggiornamenti delle funzionalità" di Windows 10 (versioni principali del sistema operativo) verranno installati solo dopo che Microsoft testerà e convalida una determinata funzionalità degli aggiornamenti con Microsoft Teams Room. Anche se l'aggiornamento viene rilasciato nel canale Semi-Annual (o mirato se si hanno sistemi impostati su quel canale per i test) o inserito manualmente, un dispositivo Microsoft Room Systems non consente l'installazione dell'aggiornamento non testato.

La funzionalità Sale di Microsoft Teams funziona "predefinita" con un approccio hands-off e non installa Windows Update né riavvia automaticamente un dispositivo per Windows Update. I sistemi scaricano un aggiornamento e aspettano il prossimo riavvio per installarlo. A meno che un utente non la riavvii manualmente, l'installazione avviene solo al riavvio automatico sereno. Gli aggiornamenti di Windows devono essere trasparenti nella stanza e il normale funzionamento non dovrebbe mai essere interrotto dagli aggiornamenti di Windows.

Se si sceglie di aggiungere dispositivi per l'aggiunta a un dominio, usare Gestione configurazione endpoint Microsoft o Windows Server Update Services. Prestare particolare attenzione ai criteri o alle azioni che causano un aggiornamento del dispositivo o un riavvio forzato durante gli orari di ufficio. I sistemi nella distribuzione non devono essere riavviati durante l'uso o sono avvisati degli aggiornamenti di Windows nell'interfaccia utente durante le ore di utilizzo. Se si verifica questo comportamento, rivedere la configurazione.