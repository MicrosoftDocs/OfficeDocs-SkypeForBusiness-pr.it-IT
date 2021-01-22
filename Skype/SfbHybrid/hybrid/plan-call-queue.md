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
description: Panoramica dell'utilizzo di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918742"
---
# <a name="plan-cloud-call-queues"></a>Pianificare le code delle chiamate cloud

La coda delle chiamate cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi le inserisce in una coda di attesa durante la ricerca di un elenco preconfigurato di agenti per rispondere a queste chiamate. È possibile definire il set di agenti nelle liste di distribuzione abilitate alla posta elettronica o nei gruppi di sicurezza. L'organizzazione può avere una o più code di chiamata. Le code di chiamata vengono in genere utilizzate in combinazione con gli operatori automatici.

Inoltre, le code di chiamata cloud possono fornire:

- Musica mentre i chiamanti sono in attesa di attesa
- Impostazioni personalizzate per le dimensioni massime, il timeout e le opzioni di gestione delle chiamate della coda di chiamata

A ogni coda di chiamata viene assegnato un **account** di risorsa (vedere Configurare gli account delle [risorse)](configure-onprem-ra.md)nel sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamata nell'interfaccia di amministrazione di Microsoft Teams. Per [ulteriori informazioni sulle](/MicrosoftTeams/create-a-phone-system-call-queue) code di chiamata e sulle opzioni e le funzionalità disponibili per le code di chiamata, vedere Creare una coda di chiamata cloud.

> [!NOTE]
> È possibile assegnare più numeri di telefono a una coda di chiamata, ma devono essere numeri di servizio Microsoft, numeri di instradamento diretto o numeri ibridi.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che Skype for Business Server 2019 sia già stato distribuito in una topologia supportata.  I requisiti dipendono dal proprio scenario:

- Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in [Configurare gli account delle risorse.](configure-onprem-ra.md) You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.

Oltre ai requisiti indicati in precedenza, è necessario configurare i requisiti seguenti per la connessione al servizio di coda di chiamata di Microsoft Cloud:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare le code di chiamata cloud per gli utenti locali, è necessario assicurarsi di disporre della connettività ibrida impostata tra gli ambienti locali e online. A volte viene definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e Configurare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](configure-hybrid-connectivity.md)

- Se si assegna un numero di telefono a un account di risorsa, è ora possibile utilizzare la licenza utente virtuale sistema telefonico gratuita. Ciò offre funzionalità di Sistema telefonico ai numeri di telefono a livello dell'organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.

- Creare un account di risorsa [locale](configure-onprem-ra.md) per ogni coda di chiamata e assegnare una licenza e un numero di telefono, se necessario.  

Quando si dispone di una struttura solida che soddisfa le proprie esigenze e di uno script che guida i clienti in modo efficiente, passare [a Configurare gli account delle risorse.](configure-onprem-ra.md)

## <a name="see-also"></a>Vedere anche

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[Gestire gli account di risorsa in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
