---
title: Pianificare una coda di chiamate cloud
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
description: Panoramica dell'utilizzo di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110492"
---
# <a name="plan-cloud-call-queues"></a>Pianificare le code delle chiamate cloud

La coda delle chiamate cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi le inserisce in una coda di attesa durante la ricerca di un elenco preconfigurato di agenti per rispondere a queste chiamate. È possibile definire il set di agenti nelle liste di distribuzione abilitate alla posta o nei gruppi di sicurezza. L'organizzazione può avere una o più code di chiamata. Le code di chiamata vengono in genere utilizzate in combinazione con gli operatori automatici.

Inoltre, le code delle chiamate cloud possono fornire:

- Musica mentre i chiamanti sono in attesa di attesa
- Impostazioni personalizzate per le opzioni di dimensione massima, timeout e gestione delle chiamate della coda di chiamata

A ogni coda di chiamata viene assegnato un **account** di risorsa (vedere [Configurare](configure-onprem-ra.md)gli account delle risorse) nel sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamata nell'interfaccia di amministrazione di Microsoft Teams. Per ulteriori dettagli sulle code di chiamata e sulle opzioni e le funzionalità disponibili per le code di chiamata, vedere Create [a Cloud call queue.](/MicrosoftTeams/create-a-phone-system-call-queue)

> [!NOTE]
> È possibile assegnare più numeri di telefono a una coda di chiamata, ma devono essere numeri di servizio Microsoft, numeri di instradamento diretto o numeri ibridi.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che Skype for Business Server 2019 sia già stato distribuito in una topologia supportata.  I requisiti dipendono dal proprio scenario:

- Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in [Configure resource accounts](configure-onprem-ra.md). Dovrai creare account delle risorse online o in Skype for Business Server 2019 e potrebbe anche essere necessario associare un numero di telefono alla coda di chiamata.

Oltre ai requisiti indicati in precedenza, è necessario configurare i requisiti seguenti per la connessione al servizio di coda delle chiamate di Microsoft Cloud:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare le code di chiamata cloud per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e Configurare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](configure-hybrid-connectivity.md)

- Se stai assegnando un numero di telefono a un account della risorsa, ora puoi usare la licenza utente virtuale sistema telefonico gratuita. In questo modo sono disponibili funzionalità del sistema telefonico per i numeri di telefono a livello dell'organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.

- Creare un account di risorsa [locale](configure-onprem-ra.md) per ogni coda di chiamata e assegnare una licenza e un numero di telefono, se necessario.  

Quando si dispone di una struttura solida che soddisfa le proprie esigenze e di uno script che guida i clienti in modo efficiente, passare a [Configurare gli account delle risorse.](configure-onprem-ra.md)

## <a name="see-also"></a>Vedere anche

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[Gestire gli account di risorsa in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)