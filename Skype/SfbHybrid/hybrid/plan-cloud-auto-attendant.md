---
title: Pianificare un operatore automatico cloud
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
description: Panoramica sull'utilizzo di un operatore automatico cloud con Skype for Business Server 2019
ms.openlocfilehash: 2cb4c54e4c70e9187e44c5de3cb70fac85be30a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150477"
---
# <a name="plan-cloud-auto-attendants"></a>Pianificare gli operatori automatici del cloud

L'operatore automatico utilizzato con la messaggistica unificata di Exchange (Exchange Server 2013 o Exchange Server 2016) non è più disponibile in Exchange Server 2019 o Exchange Online. Se l'implementazione di Skype for Business Server 2019 si integra con una di queste versioni di Exchange, è necessario utilizzare le funzionalità di VoIP del cloud online associate al sistema telefonico. Vedere [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md) per informazioni sullo spostamento di servizi di messaggistica unificata di Exchange ospitati su exchange Server 2013 e 2016 nel cloud.

Questo significa intrinsecamente che si avrà un'implementazione ibrida di Skype for Business Server 2019 se si desidera utilizzare le funzionalità di messaggistica unificata come gli operatori automatici. Per informazioni dettagliate, vedere [configurare la connettività ibrida tra Skype for Business Server e Office 365](configure-hybrid-connectivity.md) .

Un operatore automatico è un servizio cloud che accetta le chiamate ai clienti e i messaggi di saluto, fornisce loro le opzioni di menu e interagiscono con i chiamanti che utilizzano la voce o il tastierino per instradare le chiamate verso la destinazione corretta. A ciascun operatore automatico viene assegnato un **account risorse** (vedere[Configure Resource accounts](configure-onprem-ra.md)) sul sistema Skype for Business Server 2019 che verrà collegato direttamente a un operatore automatico nell'interfaccia di amministrazione di Microsoft teams. Vedere [che cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) per ulteriori dettagli sugli operatori automatici e sulle opzioni e caratteristiche disponibili per gli operatori automatici.

> [!NOTE]
> È possibile assegnare più numeri di servizio Microsoft o numeri ibridi a un operatore automatico.

Una chiamata in arrivo a un operatore automatico cloud può eseguire uno dei diversi percorsi, come illustrato di seguito:

![Diagramma per gli operatori automatici](../../SfBServer2019/media/AA-plan-concept.png)

1. Tramite Skype for Business Server 2019
2. Tramite un [Session border controller](/MicrosoftTeams/direct-routing-border-controllers.md) e [Direct routing](/MicrosoftTeams/direct-routing-plan.md)
3. Tramite un numero ospitato online in Office 365.

Vedere anche:

- [Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Risposta e routing automatico delle chiamate in arrivo](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presumono che si disponga già di Skype for Business Server 2019 distribuito in una topologia supportata.  I requisiti dipendono dallo scenario:

- Se si sta già utilizzando la messaggistica unificata di Exchange Online o in locale e si esegue l'aggiornamento a Skype for business 2019, sarà necessario acquisire la struttura degli operatori automatici e ricrearli nel cloud utilizzando gli operatori automatici del cloud. Per ulteriori informazioni, vedere [spostamento di un operatore automatico di messaggistica unificata di Exchange o di una coda di chiamata al sistema telefonico](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Per una nuova configurazione degli operatori automatici del cloud, seguire i passaggi descritti in [Configure Resource accounts](configure-onprem-ra.md).

Oltre ai requisiti di cui sopra, è necessario configurare i requisiti seguenti per la connessione al servizio operatore automatico cloud Microsoft:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare l'operatore automatico cloud per gli utenti locali, è necessario verificare di disporre della connettività ibrida configurata tra gli ambienti locali e online. A volte viene chiamata configurazione di un dominio diviso.

   Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).

- Se si assegna un numero di telefono all'operatore automatico, sarà necessaria una licenza di [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) .
- Creare [un account delle risorse online o](/MicrosoftTeams/manage-resource-accounts.md) di una [risorsa](configure-onprem-ra.md)locale per ogni operatore automatico e assegnare numeri di telefono e licenze. 

## <a name="migration-and-interoperability"></a>Migrazione e interoperabilità

Se si prevede di distribuire Skype for Business Server 2019 e/o Exchange Server 2019, è necessario pianificare attentamente la migrazione per garantire il supporto continuativo per gli operatori automatici. Tenere presente quanto segue:

- Exchange Server 2019 non fornisce più la funzionalità di messaggistica unificata di Exchange
- La messaggistica unificata di Exchange è in modalità pensionamento
- Skype for Business Server 2019 non si integra più con la messaggistica unificata di Exchange Online

Gli operatori automatici cloud possono essere configurati con Skype for Business Server 2019, 2015 e 2013.

Microsoft consiglia i percorsi di migrazione seguenti:

- Se si esegue l'aggiornamento a Skype for Business Server 2019, è possibile utilizzare la messaggistica unificata di Exchange in Exchange Server 2013 o 2016, ma è necessario eseguire l'aggiornamento a cloud Auto Attendant se si utilizza Exchange Server 2019.

- Se si esegue l'aggiornamento a Exchange Server 2019 e si utilizzano versioni precedenti della messaggistica UNIFICAta di Exchange Server per Skype for Business Server, Microsoft consiglia di eseguire l'aggiornamento a Skype for Business Server 2019 prima dell'aggiornamento della cassetta postale.  In caso contrario, le funzionalità di messaggistica vocale andranno perse.

Per ulteriori informazioni sulla pianificazione della migrazione, vedere [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrazione di un sistema di messaggistica unificata di Exchange in precedenza implementato

Attualmente non è supportata la migrazione automatica al cloud di un sistema di operatore automatico di messaggistica unificata creato in Exchange 2013 o 2016. Per ricreare manualmente un sistema di operatore automatico, è necessario eseguire le operazioni seguenti:

1. Utilizzare i comandi di Exchange Admin PowerShell per esaminare la struttura del sistema di operatore automatico obsoleto, inclusi gli eventuali operatori automatici e le code di chiamata nidificati.  
2. Creare copie degli script di sintesi vocale o dei messaggi registrati associati a ciascun nodo dell'operatore automatico di messaggistica unificata.
3. Creare gli endpoint locali per ogni nodo operatore automatico, inclusa l'assegnazione di un numero di telefono di prova e di licenze agli oggetti. Si noti che ora è possibile assegnare licenze di numeri di telefono locali utilizzate dai servizi online come sistema telefonico.
4. Implementare un nuovo servizio di operatore automatico cloud con Skype for business online e il sistema telefonico. Vedere [Configure Resource accounts](configure-onprem-ra.md) for implementation details. Quando si esegue questa operazione, caricare gli script di sintesi vocale o i messaggi registrati associati a ciascun nodo dell'operatore automatico di messaggistica unificata.
5. Testare la funzionalità dell'operatore automatico cloud.
6. Riassegnare il numero di telefono assegnato al vecchio operatore automatico di messaggistica unificata di Exchange all'operatore automatico cloud principale appena creato.

Per informazioni dettagliate su questi passaggi, vedere [spostamento di un operatore automatico di messaggistica unificata di Exchange o coda di chiamata al sistema telefonico](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) .

## <a name="additional-planning-resources"></a>Risorse di pianificazione aggiuntive

Il tutorial intitolato [Small Business example-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) passa attraverso il processo di raccolta delle informazioni sulle esigenze degli utenti, la pianificazione di una struttura di operatori automatici e degli utenti (e possibilmente code di chiamata), la scrittura delle istruzioni di menu e l'implementazione del piano nell'interfaccia di amministrazione dei team. Esaminare l'esercitazione e utilizzare gli esercizi disponibili per creare il piano.

Quando si dispone di una struttura solida in grado di soddisfare le proprie esigenze e uno script che guida i clienti in modo efficiente, procedere alla [configurazione degli account delle risorse](configure-onprem-ra.md).

> [!CAUTION]
> Come accennato in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), lo spostamento degli operatori automatici di messaggistica unificata di Exchange creati nel server 2015 nei server che eseguono il server 2019 è sconsigliato. Per il momento, è necessario tenerli in un pool Skype for Business Server 2015 in esecuzione in modalità coesistenza.

## <a name="see-also"></a>Vedere anche

[Pianificare la migrazione di Skype for Business Server e Exchange Server](plan-um-migration.md)

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Che cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant)

Messaggistica unificata [di Exchange: rispondere e instradare automaticamente le chiamate in arrivo](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Pianificare la connettività ibrida tra Skype for Business Server e Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Office 365](configure-hybrid-connectivity.md)

[KB4480742: le chiamate all'accesso sottoscrittore o all'operatore automatico hanno esito negativo con un errore di Fast busy e "500 Internal Server" dopo lo spostamento degli oggetti contatto in Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
