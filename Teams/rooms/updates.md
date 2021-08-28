---
title: Gestire Windows aggiornamenti per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Gli amministratori possono informazioni su come gestire gli aggiornamenti Windows e Windows delle funzionalità per Microsoft Teams Rooms.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28f5d9def3a5217d1d34343e27cbaddb6a3433b9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602121"
---
# <a name="manage-windows-updates"></a>Gestire Windows aggiornamenti

Microsoft Teams Rooms viene eseguito in Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) e riceve le stesse build Windows Updates e OS di un computer desktop standard.

Windows Gli aggiornamenti possono essere gestiti come descritto nelle sezioni seguenti:

## <a name="hands-off-approach"></a>Approccio hands-off 

- Per impostazione predefinita, gli aggiornamenti vengono scaricati direttamente Windows aggiornamenti automatici e installati durante le ore non lavorative.
- Aggiornamenti non rinviabili installano automaticamente il primo giorno del rilascio.
- Aggiornamenti qualitativi e driver scaricano e installano automaticamente il primo giorno.
- Aggiornamenti delle funzionalità. Vedere le note seguenti.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Aggiornamenti per le aziende (oggetto Criteri di gruppo o Intune)  

- [download Windows aggiornamenti per le](/windows/deployment/update/waas-manage-updates-wufb) aziende
- Gli aggiornamenti vengono scaricati Windows update o WSUS, ma con ritardi configurati oltre la data di rilascio originale.
- È possibile usare più unità organizzative o criteri filtrati per creare "anelli" di distribuzione in cui gli amministratori possono specificare quali dispositivi installare prima gli aggiornamenti qualitativi e quali installare in un secondo momento. L'affidabilità e le prestazioni possono essere testate in un sottoinsieme di sistemi prima di eseguire la distribuzione degli aggiornamenti nell'intera distribuzione senza l'overhead della gestione Windows aggiornamenti in Configuration Manager.
- Wsus e Windows aggiornamenti per le [](/windows/deployment/update/waas-integrate-wufb) aziende possono essere configurati contemporaneamente se si vuole che la gestione della larghezza di banda e il controllo Windows aggiornamenti per le aziende.
- Aggiornamenti delle funzionalità. Vedere le note seguenti.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Download di WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Molto simile Windows Update for Business, ma con l'opzione aggiuntiva di scegliere come target specifici KB all'interno di ogni "anello" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, invece di basarsi solo su un ritardo.
- Aggiornamenti delle funzionalità. Vedere le note seguenti.

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

A differenza degli aggiornamenti qualitativi e non rinviabili, Windows 10 "Aggiornamenti delle funzionalità" (rilasci principali del sistema operativo) verrà installato solo dopo i test microsoft e la convalida di una determinata funzionalità di aggiornamento con Microsoft Teams Rooms. Anche se l'aggiornamento viene rilasciato nel canale Semi-Annual (o Mirato se si hanno sistemi impostati su tale canale per i test) o inseriti manualmente, un dispositivo Microsoft Room Systems non consente l'installazione dell'aggiornamento non testato.

Microsoft Teams Rooms funzioni "out-of-box" con un approccio hands-off e non installa un Windows Update o riavvia automaticamente un dispositivo per un Windows Update. I sistemi scaricano un aggiornamento e aspettano il prossimo riavvio per installarlo. A meno che qualcuno non lo riavvii manualmente, l'installazione viene eseguita solo al riavvio automatico notturno. Windows Gli aggiornamenti devono essere trasparenti nella chat room e il normale funzionamento non deve mai essere interrotto Windows aggiornamenti.

Se si sceglie di aggiungere un dominio ai dispositivi, usare Microsoft Endpoint Configuration Manager o WSUS. Prestare particolare attenzione ai criteri o alle azioni che causano un aggiornamento del dispositivo o un riavvio forzato durante l'orario di ufficio. I sistemi nella distribuzione non devono essere riavviati durante l'uso o devono essere avvisati degli aggiornamenti Windows durante l'interfaccia utente durante le ore di utilizzo, esaminare la configurazione in caso di questo comportamento.