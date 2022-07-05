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
ms.localizationpriority: medium
ms.collection: ''
description: Panoramica dell'uso di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615422"
---
# <a name="plan-cloud-call-queues"></a>Pianificare le code delle chiamate cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

La coda di chiamate cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi inserisce queste chiamate in una coda di attesa durante la ricerca di un elenco pre-configurato di agenti per rispondere a queste chiamate. È possibile definire il set di agenti nelle liste di distribuzione abilitate per la posta elettronica o nei gruppi di sicurezza. L'organizzazione può avere una o più code di chiamata. Le code di chiamata vengono in genere usate in combinazione con gli operatori automatici.

Inoltre, le code di chiamate cloud possono fornire:

- Musica mentre i chiamanti sono in attesa in attesa
- Impostazioni personalizzate per le opzioni di dimensioni massime della coda di chiamate, timeout e gestione delle chiamate

A ogni coda di chiamate viene assegnato un **account di risorsa** (vedere [Configurare gli account delle risorse](configure-onprem-ra.md)) nel sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamate nell'interfaccia di amministrazione di Microsoft Teams. Per altre informazioni sulle code di chiamata e sulle opzioni e le funzionalità disponibili per le code di chiamate, vedere [Creare una coda di chiamate cloud](/MicrosoftTeams/create-a-phone-system-call-queue) .

> [!NOTE]
> È possibile assegnare più numeri di telefono a una coda di chiamate, ma devono essere numeri di servizio Microsoft, numeri di routing diretto o numeri ibridi.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che sia già stato distribuito Skype for Business Server 2019 in una topologia supportata.  I requisiti dipendono dallo scenario:

- Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in [Configurare gli account delle risorse](configure-onprem-ra.md). Sarà necessario creare account di risorse online o in Skype for Business Server 2019 e potrebbe anche essere necessario associare un numero di telefono alla coda delle chiamate.

Oltre ai requisiti precedenti, è necessario configurare i requisiti seguenti per connettersi al servizio code di chiamate di Microsoft Cloud:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si vuole abilitare le code di chiamata cloud per gli utenti locali, è necessario assicurarsi di avere la connettività ibrida configurata tra gli ambienti locali e online. Questa configurazione viene talvolta definita configurazione di dominio diviso.

   Per altre informazioni, vedere [Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e [Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md).

- Se si assegna un numero di telefono a un account di risorsa, è ora possibile usare la licenza gratuita **Telefono di Microsoft Teams Account risorse**. Ciò offre funzionalità di sistema telefonico ai numeri di telefono a livello aziendale e consente di creare funzionalità di operatore automatico e coda di chiamata.

- Creare un [account di risorsa](configure-onprem-ra.md) locale per ogni coda di chiamate e assegnare una licenza e un numero di telefono, se necessario.  

Quando si dispone di una struttura solida che soddisfa le proprie esigenze e di uno script che guida i clienti in modo efficiente, passare a  [Configurare gli account delle risorse](configure-onprem-ra.md).

## <a name="see-also"></a>Vedere anche

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[Gestire gli account di risorsa in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)