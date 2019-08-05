---
title: Pianificare una coda di chiamata cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica dell'uso di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185543"
---
# <a name="plan-cloud-call-queues"></a>Pianificare le code delle chiamate cloud

La coda delle chiamate cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi inserisce queste chiamate in una coda di attesa durante la ricerca di un elenco preconfigurato di agenti per rispondere a queste chiamate. Puoi definire il set di agenti in liste di distribuzione o gruppi di sicurezza abilitati alla posta elettronica. L'organizzazione può avere una o più code di chiamata. Le code di chiamata vengono in genere usate in combinazione con gli operatori automatici.

Inoltre, le code delle chiamate cloud possono prevedere:

- Musica quando i chiamanti attendono il blocco
- Impostazioni personalizzate per le opzioni di gestione delle chiamate e delle dimensioni massime della coda di chiamata

A ogni coda di chiamata viene assegnato un **account di risorse** (vedere [configurare gli account delle risorse](configure-onprem-ra.md)) nel sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamata nell'interfaccia di amministrazione di Microsoft teams. Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue) e quali sono le opzioni e le funzionalità disponibili per le code di chiamata.

> [!NOTE]
> È possibile assegnare più numeri di telefono a una coda di chiamata, ma devono essere numeri di servizio Microsoft o numeri ibridi.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che si disponga già di Skype for Business Server 2019 distribuito in una topologia supportata.  I requisiti dipendono dallo scenario:

- Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in configurare gli [account risorse](configure-onprem-ra.md). Sarà necessario creare gli account delle risorse online o in Skype for Business Server 2019 e potrebbe essere necessario associare un numero di telefono alla coda di chiamata.

Oltre ai requisiti descritti sopra, i requisiti seguenti devono essere configurati per la connessione al servizio code di chiamata Microsoft Cloud:

- Connettività ibrida. Se è già stato implementato Skype for Business Server e si vogliono abilitare le code di chiamata cloud per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di domini divisi.

   Per altre informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).

- Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi. In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.

- Creare un [account di risorse](configure-onprem-ra.md) locale per ogni coda di chiamata e assegnare una licenza e un numero di telefono, se necessario.  

## <a name="additional-planning-resources"></a>Risorse di pianificazione aggiuntive

Esempio di esercitazione intitolato [Small Business-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) durante il processo di raccolta di informazioni sulle esigenze degli utenti, la pianificazione di una struttura di operatori automatici e gli utenti (e possibilmente le code di chiamata), la scrittura delle istruzioni del menu e implementazione del piano nell'interfaccia di amministrazione online. esaminare l'esercitazione e usare gli esercizi che non creano il piano.

Quando si ha una struttura solida che soddisfa le proprie esigenze e uno script che guida in modo efficiente i clienti, procedere alla [configurazione degli account delle risorse](configure-onprem-ra.md).

## <a name="see-also"></a>Vedere anche

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitare la registrazione di una richiesta personalizzata con l'interfaccia utente telefonica](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Pianificare la connettività ibrida tra Skype for Business Server e Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Office 365](configure-hybrid-connectivity.md)

[Gestire gli account delle risorse in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
