---
title: Gestire Windows aggiornamenti per Microsoft Teams Rooms
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: Gestire Windows aggiornamenti per Microsoft Teams Rooms
ms.openlocfilehash: 1a5e665546c00525939585f4655fcdf404e5786f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859993"
---
# <a name="manage-windows-updates"></a>Gestire Windows aggiornamenti

Microsoft Teams Rooms viene eseguito su Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) e riceve gli stessi aggiornamenti Windows e build del sistema operativo come desktop standard.

Windows Gli aggiornamenti possono essere gestiti in diversi modi:

## <a name="hands-off-approach"></a>Approccio hands-off 
- Gli aggiornamenti possono essere scaricati direttamente Windows aggiornamenti automatici e installati durante le ore non lavorative. Se non viene apportata alcuna modifica alla configurazione, questo è lo stato predefinito.
- Gli aggiornamenti non rinviabili installeranno automaticamente il primo giorno del rilascio. 
- Gli aggiornamenti qualitativi e i driver verranno scaricati e installati automaticamente il primo giorno. 
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows aggiornamenti per le aziende](/windows/deployment/update/waas-manage-updates-wufb) (oggetto Criteri di gruppo o Intune)   
- Gli aggiornamenti vengono scaricati da WU o WSUS, ma con ritardi configurati oltre la data di rilascio originale della KB. 
- In combinazione con più criteri dell'unità organizzativa o filtrati, ciò consente la creazione di "anelli" di distribuzione, in cui gli amministratori possono specificare quali dispositivi installano prima gli aggiornamenti qualitativi e quali verranno installati in un secondo momento. In questo modo è possibile testare l'affidabilità e le prestazioni in un sottoinsieme di sistemi prima di eseguire aggiornamenti nell'intera distribuzione senza l'overhead della gestione degli aggiornamenti di Windows in Microsoft Endpoint Configuration Manager, ad esempio.
- WSUS e Windows aggiornamenti per le [](/windows/deployment/update/waas-integrate-wufb) aziende possono essere configurati contemporaneamente se si desidera sia la gestione della larghezza di banda che il controllo Windows Aggiornamenti per le aziende.
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Molto simile Windows Update for Business, ma con l'opzione aggiuntiva di selezionare kb specifiche all'interno di ogni "anello" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, anziché basarsi solo su un ritardo. 
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito.


### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

A differenza degli aggiornamenti qualitativi e non rimandabili, Windows 10 "Aggiornamenti delle funzionalità" (versioni principali del sistema operativo) verranno installati solo dopo che Microsoft ha verificato e convalidato una determinata funzionalità di aggiornamento con Microsoft Teams Rooms. Anche se viene rilasciato al canale Semi-Annual (o Mirato se hai sistemi impostati su tale canale per i test) o anche manualmente spinti dai tuoi tentativi o configurazioni, non consentirà l'installazione fino a quando il blocco non verrà rimosso.

Microsoft Teams La sala "predefinita", con l'approccio hands off, non installerà un aggiornamento di Windows né riavvierà automaticamente un dispositivo a causa di un aggiornamento Windows automatico. I sistemi possono tuttavia scaricare un aggiornamento e attendere il riavvio successivo per installarlo. A meno che qualcuno non lo riavvii manualmente, l'installazione deve avvenire al riavvio automatico notturno. Windows Gli aggiornamenti devono essere trasparenti nella sala, l'interfaccia utente non deve mai essere interrotta da Windows aggiornamenti.

Se scegli di aggiungere un dominio, usa Microsoft Endpoint Configuration Manager o WSUS e presta particolare attenzione ai criteri o alle azioni che potrebbero causare l'installazione di un aggiornamento o la forzatura di un riavvio durante l'orario di ufficio. Se nella distribuzione sono presenti sistemi che si riavviano durante l'uso o che inviano avvisi sugli aggiornamenti Windows tramite l'interfaccia utente, è necessario esaminare la configurazione.