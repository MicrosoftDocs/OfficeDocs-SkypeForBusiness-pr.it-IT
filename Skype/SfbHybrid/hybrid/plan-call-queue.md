---
title: Pianificare una coda di chiamata cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica sull'utilizzo di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221306"
---
# <a name="plan-cloud-call-queues"></a>Pianificare le code di chiamata cloud

La coda di chiamata cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi inserisce tali chiamate in una coda di attesa durante la ricerca di un elenco di agenti preconfigurato per rispondere alle chiamate. È possibile definire il set di agenti nelle liste di distribuzione o nei gruppi di sicurezza abilitati alla posta elettronica. L'organizzazione può disporre di una o più code di chiamata. Le code di chiamata vengono in genere utilizzate in combinazione con gli operatori automatici.

Inoltre, le code di chiamata cloud possono fornire:

- Musica durante l'attesa dei chiamanti
- Impostazioni personalizzate per la dimensione massima della coda di chiamata, il timeout e le opzioni di gestione delle chiamate

A ogni coda di chiamata viene assegnato un **account risorse** (vedere [Configure Resource accounts](configure-onprem-ra.md)) sul sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamata nell'interfaccia di amministrazione di Microsoft teams. Per ulteriori informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue) e quali opzioni e caratteristiche esistono per le code di chiamata.

> [!NOTE]
> È possibile assegnare più numeri di telefono a una coda di chiamata, ma devono essere numeri di servizio Microsoft, numeri di routing diretti o numeri ibridi.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presumono che si disponga già di Skype for Business Server 2019 distribuito in una topologia supportata.  I requisiti dipendono dallo scenario:

- Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in [Configure Resource accounts](configure-onprem-ra.md). Sarà necessario creare gli account delle risorse online o in Skype for Business Server 2019 e potrebbe anche essere necessario associare un numero di telefono alla coda di chiamata.

Oltre ai requisiti di cui sopra, è necessario configurare i requisiti seguenti per la connessione al servizio code di chiamata Microsoft Cloud:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare le code di chiamata cloud per gli utenti locali, è necessario verificare di disporre della connettività ibrida configurata tra gli ambienti locali e online. A volte viene chiamata configurazione di un dominio diviso.

   Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e microsoft 365 o office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md).

- Se si assegna un numero di telefono a un account delle risorse, è ora possibile utilizzare la licenza per l'utente virtuale del sistema telefonico senza costi. Questo fornisce funzionalità del sistema telefonico ai numeri di telefono a livello di organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.

- Creare un [account delle risorse](configure-onprem-ra.md) locale per ogni coda di chiamata e assegnare una licenza e un numero di telefono, se necessario.  

## <a name="additional-planning-resources"></a>Risorse di pianificazione aggiuntive

L'esercitazione intitolata [Small Business example-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) passa attraverso il processo di raccolta di informazioni sulle esigenze degli utenti, la pianificazione di una struttura di operatori automatici e degli utenti (e possibilmente code di chiamata), la scrittura delle istruzioni di menu e l'implementazione del piano nell'interfaccia di amministrazione online. esaminare l'esercitazione e utilizzare gli esercizi che non è possibile creare il piano.

Quando si dispone di una struttura solida in grado di soddisfare le proprie esigenze e uno script che guida i clienti in modo efficiente, procedere alla [configurazione degli account delle risorse](configure-onprem-ra.md).

## <a name="see-also"></a>Vedere anche

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[Gestire gli account di risorsa in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
