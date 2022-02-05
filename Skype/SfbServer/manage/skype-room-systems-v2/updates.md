---
title: Gestire Windows aggiornamenti per Microsoft Teams Rooms
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: null
description: Gestire Windows aggiornamenti per Microsoft Teams Rooms
---

# <a name="manage-windows-updates"></a>Gestire Windows aggiornamenti

Microsoft Teams Rooms viene eseguito Windows 10 Enterprise IoT o Windows 10 Enterprise (VL) e riceve le stesse build Windows Updates e OS come desktop standard.

Windows gli aggiornamenti possono essere gestiti in diversi modi:

## <a name="hands-off-approach"></a>Approccio hands-off 
- Gli aggiornamenti possono essere scaricati direttamente Windows aggiornamenti automatici e installati durante le ore non lavorative. Se non viene apportata alcuna modifica alla configurazione, questo è lo stato predefinito.
- Gli aggiornamenti non rinviabili installeranno automaticamente il primo giorno del rilascio. 
- Gli aggiornamenti qualitativi e i driver verranno scaricati e installati automaticamente il primo giorno. 
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows aggiornamenti per le aziende](/windows/deployment/update/waas-manage-updates-wufb) (oggetto Criteri di gruppo o Intune)   
- Gli aggiornamenti vengono scaricati da WU o WSUS, ma con ritardi configurati oltre la data di rilascio originale della KB. 
- In combinazione con più criteri dell'unità organizzativa o filtrati, ciò consente la creazione di "anelli" di distribuzione, in cui gli amministratori possono specificare quali dispositivi installano prima gli aggiornamenti qualitativi e quali verranno installati in un secondo momento. In questo modo è possibile testare l'affidabilità e le prestazioni in un sottoinsieme di sistemi prima di eseguire aggiornamenti nell'intera distribuzione senza l'overhead della gestione degli aggiornamenti Windows in Microsoft Endpoint Configuration Manager, ad esempio.
- WSUS e Windows aggiornamenti per le aziende possono essere configurati contemporaneamente se si desidera sia la gestione della larghezza di banda che il controllo Windows Aggiornamenti per le aziende.[](/windows/deployment/update/waas-integrate-wufb)
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Proprio come Windows Update for Business, ma con l'opzione aggiuntiva di scegliere come target specifici KB all'interno di ogni "anello" o dell'intera distribuzione. Ogni aggiornamento può essere distribuito e testato singolarmente, anziché basarsi solo su un ritardo. 
- Aggiornamenti delle funzionalità. Vedi note aggiuntive di seguito.


### <a name="feature-updates"></a>Aggiornamenti delle funzionalità

A differenza degli aggiornamenti qualitativi e non rinviabili, Windows 10 "Feature Updates" (versioni principali del sistema operativo) verrà installato solo dopo che Microsoft ha verificato e convalidato una determinata funzionalità di aggiornamento con Microsoft Teams Rooms. Anche se viene rilasciato al canale Semi-Annual (o Mirato se hai sistemi impostati su tale canale per i test) o anche manualmente spinti dai tuoi tentativi o configurazioni, l'installazione non sarà consentita fino a quando il blocco alla fine non verrà rimosso.

Microsoft Teams Room "out-of-box", usando l'approccio hands off, non installerà un aggiornamento di Windows né riavvierà automaticamente un dispositivo a causa di un aggiornamento Windows automatico. I sistemi possono tuttavia scaricare un aggiornamento e attendere il riavvio successivo per installarlo. A meno che qualcuno non lo riavvii manualmente, l'installazione deve avvenire al riavvio automatico notturno. Windows gli aggiornamenti devono essere trasparenti nella sala, l'interfaccia utente non deve mai essere interrotta da Windows aggiornamenti.

Se si sceglie di aggiungere un dominio, utilizzare Microsoft Endpoint Configuration Manager o WSUS e prestare particolare attenzione ai criteri o alle azioni che potrebbero causare l'installazione di un aggiornamento o la forzatura di un riavvio durante l'orario di ufficio. Se nella distribuzione sono presenti sistemi che si riavviano durante l'uso o che inviano avvisi sugli aggiornamenti Windows tramite l'interfaccia utente, è necessario esaminare la configurazione.