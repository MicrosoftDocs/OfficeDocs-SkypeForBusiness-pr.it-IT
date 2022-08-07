---
title: Gestire windows Aggiornamenti per Microsoft Teams Rooms
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
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: Amministrazione informazioni su come gestire gli aggiornamenti delle funzionalità di Windows Aggiornamenti e Windows per Microsoft Teams Rooms.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272181"
---
# <a name="manage-windows-updates"></a>Gestire Windows Aggiornamenti

Microsoft Teams Rooms viene eseguito in Windows 10 Enterprise IoT o Windows 10 Enterprise (contratto multilicenza) e riceve le stesse build di Windows Aggiornamenti e del sistema operativo di un computer desktop standard.

Windows Aggiornamenti può essere gestito come descritto nelle sezioni seguenti:

## <a name="hands-off-approach"></a>Approccio hands-off 

- Per impostazione predefinita, gli aggiornamenti vengono scaricati direttamente da Windows Aggiornamenti automaticamente e installati durante le ore non lavorative.
- I Aggiornamenti non rinviabili installano automaticamente il primo giorno del rilascio.
- La qualità Aggiornamenti e i driver scaricano e installano automaticamente il primo giorno.
- Feature Aggiornamenti. Vedere le note che seguono.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Aggiornamenti for Business (oggetto Criteri di gruppo o Intune)  

- Download [di Windows Aggiornamenti for Business](/windows/deployment/update/waas-manage-updates-wufb)
- Aggiornamenti vengono scaricati da Windows Update o dal Windows Server Update Services, ma con ritardi configurati oltre la data di rilascio originale.
- È possibile usare più unità organizzative o criteri filtrati per creare "anelli" di distribuzione in cui gli amministratori possono specificare quali Teams Rooms dispositivi installano la qualità Aggiornamenti e quali installare in seguito. Affidabilità e prestazioni possono essere testate in un sottoinsieme di dispositivi prima di implementare gli aggiornamenti nell'intera distribuzione senza l'overhead della gestione di Windows Aggiornamenti in Configuration Manager.
- WSUS e Windows Aggiornamenti for Business possono essere [configurati contemporaneamente](/windows/deployment/update/waas-integrate-wufb) se si desidera sia la gestione della larghezza di banda che il controllo fornito da Windows Aggiornamenti for Business.
- Aggiornamenti delle funzionalità. Vedere le note che seguono.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- Download [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- In modo analogo a Windows Update for Business, ma con l'opzione aggiuntiva di assegnare kb specifiche all'interno di ogni "anello" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente a volontà, invece di fare affidamento solo su un ritardo.
- Aggiornamenti delle funzionalità. Vedere le note che seguono.

### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

A differenza degli aggiornamenti qualitativi e non rinviabili, Windows 10 "Feature Aggiornamenti" (versioni principali del sistema operativo) verranno installate solo dopo che Microsoft avrà testato e convalidato una determinata funzionalità degli aggiornamenti con Microsoft Teams Rooms. Anche se l'aggiornamento viene rilasciato nel canale Semi-Annual (o Mirato se hai sistemi impostati su quel canale per il test) o viene eseguito manualmente, Microsoft Teams Rooms non consente l'installazione dell'aggiornamento non testato.

Microsoft Teams Rooms funzioni "predefinite" con un approccio hands-off. Teams Rooms scaricare un aggiornamento e attendere il successivo riavvio per installarlo. A meno che qualcuno non lo riavvii manualmente, l'installazione avviene solo al riavvio automatico notturno. Windows Aggiornamenti deve essere trasparente nella stanza e il normale funzionamento non dovrebbe mai essere interrotto da Windows Aggiornamenti.

Se scegli di aggiungere dispositivi a un dominio, puoi usare Microsoft Endpoint Configuration Manager o WSUS. Prestare particolare attenzione ai criteri o alle azioni che provocano un aggiornamento del dispositivo o un riavvio forzato durante l'orario di ufficio. Teams Rooms non deve riavviare durante l'uso o avvisi su Windows Aggiornamenti sull'interfaccia utente durante le ore di utilizzo. Se si verifica questo comportamento, rivedere la configurazione.
