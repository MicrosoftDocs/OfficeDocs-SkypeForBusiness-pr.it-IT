---
title: Pianificare un operatore automatico cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica dell'uso di un operatore automatico cloud con Skype for Business Server 2019
ms.openlocfilehash: 1a5f1aad4cd983f1f3839f47c54404d168ecf7f0
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2019
ms.locfileid: "36185537"
---
# <a name="plan-cloud-auto-attendants"></a>Pianificare gli operatori automatici del cloud

L'operatore automatico usato con la messaggistica unificata di Exchange (Exchange Server 2013 o Exchange Server 2016) non è più disponibile in Exchange Server 2019 o Exchange Online. Se l'implementazione di Skype for Business Server 2019 si integra con una di queste versioni di Exchange, è necessario usare le funzionalità per la voce del cloud online associate al sistema telefonico. Per informazioni su come spostare i servizi di messaggistica unificata di Exchange in Exchange Server 2013 e 2016 nel cloud, vedere [pianificare la migrazione a Skype for Business Server e Exchange Server](plan-um-migration.md) .

Questo significa intrinsecamente che si avrà un'implementazione ibrida di Skype for Business Server 2019 se si vuole usare le caratteristiche di messaggistica unificata come gli operatori automatici. Per informazioni dettagliate, vedere [configurare la connettività ibrida tra Skype for Business Server e Office 365](configure-hybrid-connectivity.md) .

Un operatore automatico è un servizio cloud che accetta le chiamate dei clienti e Riproduci messaggi di saluto, li offre le opzioni di menu e si interagisce con i chiamanti usando il riconoscimento vocale o il tastierino per instradare le chiamate verso la destinazione corretta. A ogni operatore automatico viene assegnato un **account di risorse** (vedere Configurare gli[account delle risorse](configure-onprem-ra.md)) nel sistema Skype for Business Server 2019 che verrà collegato direttamente a un operatore automatico nell'interfaccia di amministrazione di Microsoft teams. [Quali sono gli operatori automatici di cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) per ulteriori dettagli sugli operatori automatici e sulle opzioni e le caratteristiche esistenti per gli operatori automatici.

> [!NOTE]
> È possibile assegnare più numeri di servizio Microsoft o numeri ibridi a un operatore automatico.

Una chiamata in arrivo a un operatore automatico cloud può eseguire uno dei diversi percorsi, come illustrato di seguito:

![Diagramma per gli operatori automatici](../../SfBServer2019/media/AA-plan-concept.png)

1. Tramite Skype for Business Server 2019
2. Tramite un [controller di bordo della sessione](/MicrosoftTeams/direct-routing-border-controllers.md) e un [routing diretto](/MicrosoftTeams/direct-routing-plan.md)
3. Tramite un numero homed online in Office 365.

Vedere anche:

- [Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Rispondere e instradare automaticamente le chiamate in arrivo](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che si disponga già di Skype for Business Server 2019 distribuito in una topologia supportata.  I requisiti dipendono dallo scenario:

- Se si sta già usando la messaggistica unificata di Exchange Online o in locale e si esegue l'aggiornamento a Skype for business 2019, sarà necessario acquisire la struttura degli operatori automatici e ricrearli nel cloud con gli operatori automatici di cloud. Per altre informazioni, vedere [spostamento di un operatore automatico di messaggistica unificata di Exchange o di una coda di chiamata nel sistema telefonico](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Per una nuova configurazione degli operatori automatici del cloud, seguire i passaggi descritti in configurare gli [account delle risorse](configure-onprem-ra.md).

Oltre ai requisiti descritti sopra, i requisiti seguenti devono essere configurati per la connessione al servizio operatore automatico cloud Microsoft:

- Connettività ibrida. Se è già stato implementato Skype for Business Server e si vuole abilitare l'operatore automatico cloud per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di domini divisi.

   Per altre informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).

- Se si sta assegnando un numero di telefono all'operatore automatico, sarà necessaria una licenza di [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) .
- Creare un [account di risorse](/MicrosoftTeams/manage-resource-accounts.md) locale per ogni operatore automatico e assegnare numeri di telefono e licenze. 

## <a name="migration-and-interoperability"></a>Migrazione e interoperabilità

Se si prevede di distribuire Skype for Business Server 2019 e/o Exchange Server 2019, è necessario pianificare con attenzione la migrazione per garantire il supporto continuo per gli operatori automatici. Tieni presente quanto segue:

- Exchange Server 2019 non fornisce più la funzionalità di messaggistica unificata di Exchange
- La messaggistica unificata di Exchange Online è in modalità pensionamento
- Skype for Business Server 2019 non si integra più con la messaggistica unificata di Exchange Online

Gli operatori automatici cloud possono essere configurati con Skype for Business Server 2019, 2015 e 2013.

Microsoft consiglia i percorsi di migrazione seguenti:

- Se si esegue l'aggiornamento a Skype for Business Server 2019, è possibile usare la messaggistica unificata di Exchange in Exchange Server 2013 o 2016, ma è necessario eseguire l'aggiornamento a cloud Auto Attendant se si usa Exchange Server 2019.

- Se si esegue l'aggiornamento a Exchange Server 2019 e si usano versioni precedenti della messaggistica UNIFICAta di Exchange Server per Skype for Business Server, Microsoft consiglia di eseguire l'aggiornamento a Skype for Business Server 2019 prima dell'aggiornamento delle cassette postali.  In caso contrario, le funzionalità di messaggistica vocale andranno perse.

Per altre informazioni sulla pianificazione della migrazione, vedere [pianificare la migrazione a Skype for Business Server e Exchange Server](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrazione di un sistema di operatore automatico di messaggistica unificata di Exchange implementato in precedenza

Attualmente non è supportata la migrazione automatica al cloud di un sistema di operatore automatico di messaggistica unificata creato in Exchange 2013 o 2016. Per ricreare manualmente un sistema di operatore automatico, è necessario:

1. Usare i comandi di PowerShell per l'amministrazione di Exchange per esaminare la struttura del sistema di operatore automatico precedente, inclusi gli operatori automatici annidati e le code di chiamata.  
2. Creare copie di script di sintesi vocale o di messaggi registrati associati a ogni nodo dell'operatore automatico di messaggistica unificata.
3. Creare sugli endpoint locali per ogni nodo operatore automatico, ad esempio assegnando i numeri di telefono e le licenze di test agli oggetti. Tieni presente che ora hai la possibilità di assegnare licenze di numeri di telefono locali usate da servizi online come il sistema telefonico.
4. Implementare un nuovo servizio di operatore automatico cloud con Skype for business online e il sistema telefonico. Vedere [configurare gli account delle risorse](configure-onprem-ra.md) per i dettagli di implementazione. A questo scopo, carica gli script di sintesi vocale o i messaggi registrati associati a ogni nodo operatore automatico di messaggistica unificata.
5. Verificare la funzionalità dell'operatore automatico cloud.
6. Riassegnare il numero di telefono assegnato al vecchio operatore automatico di messaggistica unificata di Exchange all'operatore automatico cloud principale appena creato.

Per informazioni dettagliate su questa procedura, vedere [spostamento di un operatore automatico di messaggistica unificata di Exchange o coda di chiamata nel sistema telefonico](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) .

## <a name="additional-planning-resources"></a>Risorse di pianificazione aggiuntive

Esempio di esercitazione intitolato [Small Business-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) durante il processo di raccolta di informazioni sulle esigenze degli utenti, la pianificazione di una struttura di operatori automatici e gli utenti (e possibilmente le code di chiamata), la scrittura delle istruzioni del menu e implementazione del piano nell'interfaccia di amministrazione online. esaminare l'esercitazione e usare gli esercizi disponibili per creare il piano.

Quando si ha una struttura solida che soddisfa le proprie esigenze e uno script che guida in modo efficiente i clienti, procedere alla [configurazione degli account delle risorse](configure-onprem-ra.md).

> [!CAUTION]
> Come accennato in [KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), lo spostamento tra gli operatori automatici di messaggistica unificata di Exchange creati in server 2015 per server che utilizzano server 2019 è scoraggiato. Per il momento, devi tenerli in un pool di Skype for Business Server 2015 in esecuzione in modalità di coesistenza.

## <a name="see-also"></a>Vedere anche

[Pianificare la migrazione a Skype for Business Server e Exchange Server](plan-um-migration.md)

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitare la registrazione di una richiesta personalizzata con l'interfaccia utente telefonica](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant)

Messaggistica unificata [di Exchange: rispondere e instradare automaticamente le chiamate in arrivo](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Pianificare la connettività ibrida tra Skype for Business Server e Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Office 365](configure-hybrid-connectivity.md)

[KB4480742: le chiamate all'accesso del Sottoscrittore o all'operatore automatico non riescono con l'errore Fast busy e "500 Internal Server" dopo lo spostamento di oggetti contatto in Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
