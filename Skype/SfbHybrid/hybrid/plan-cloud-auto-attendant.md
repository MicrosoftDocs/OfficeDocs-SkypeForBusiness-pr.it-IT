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
description: Panoramica dell'utilizzo di un operatore automatico cloud con Skype for Business Server 2019
ms.openlocfilehash: b144576b3e572137a512881f4bdcd1ab0e06d0ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110352"
---
# <a name="plan-cloud-auto-attendants"></a>Pianificare gli operatori automatici cloud

L'operatore automatico utilizzato con la messaggistica unificata di Exchange (Exchange Server 2013 o Exchange Server 2016) non è più disponibile Exchange Server 2019 o Exchange Online. Se l'implementazione di Skype for Business Server 2019 si integra con una di queste versioni di Exchange, dovrai usare le funzionalità cloud voice online associate al sistema telefonico. Per informazioni sullo spostamento dei servizi di messaggistica unificata di Exchange ospitati su Exchange Server 2013 e 2016 nel cloud, vedere Plan [for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)

Questo significa intrinsecamente che si avrà un'implementazione ibrida di Skype for Business Server 2019 se si desidera utilizzare le funzionalità di messaggistica unificata come gli operatori automatici. Per informazioni dettagliate, vedere Configurare la connettività ibrida tra [Skype for Business Server e Microsoft 365 o Office 365.](configure-hybrid-connectivity.md)

Un operatore automatico è un servizio cloud che accetta le chiamate dei clienti e riproduce i messaggi di saluto, fornisce loro opzioni di menu e interagisce con i chiamanti utilizzando il riconoscimento vocale o la tastiera del telefono per instradare le chiamate alla destinazione giusta. A ogni operatore automatico viene assegnato un *account* di risorsa (vedere [Configurare](configure-onprem-ra.md)gli account delle risorse) nel sistema Skype for Business Server 2019 che verrà collegato direttamente a un operatore automatico nell'interfaccia di amministrazione di Microsoft Teams. Per ulteriori informazioni sugli operatori automatici e sulle opzioni e le funzionalità disponibili per gli operatori automatici, vedere What [are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)

> [!NOTE]
> È possibile assegnare più numeri di servizio Microsoft, numeri di instradamento diretto o numeri ibridi a un operatore automatico.

Una chiamata in arrivo a un operatore automatico cloud può assumere uno dei diversi percorsi, come illustrato di seguito:

![Diagramma per gli operatori automatici](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype for Business Server 2019
2. Tramite [session border controller](/MicrosoftTeams/direct-routing-border-controllers.md) e [routing diretto](/MicrosoftTeams/direct-routing-plan.md)
3. Tramite un numero online in Microsoft 365 o Office 365.

Vedere anche:

- [Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Risposta e routing automatico delle chiamate in arrivo](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che Skype for Business Server 2019 sia già stato distribuito in una topologia supportata.  I requisiti dipendono dal proprio scenario:

- Se si utilizza già la messaggistica unificata di Exchange online o locale e si esegue l'aggiornamento a Skype for Business 2019, sarà necessario acquisire la struttura degli operatori automatici e crearli di nuovo nel cloud utilizzando gli operatori automatici cloud. Per ulteriori informazioni, vedere [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Per una nuova configurazione degli operatori automatici cloud, seguire i passaggi descritti in  [Configure resource accounts](configure-onprem-ra.md).

Oltre ai requisiti precedenti, è necessario configurare i requisiti seguenti per la connessione al servizio operatore automatico Microsoft Cloud:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare l'operatore automatico cloud per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e Configurare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](configure-hybrid-connectivity.md)

- Se si assegna un numero di telefono all'operatore automatico, è necessaria una licenza di [Office 365 Enterprise E5.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Creare un [account di risorsa](/MicrosoftTeams/manage-resource-accounts.md) online o un [account](configure-onprem-ra.md) di risorsa locale per ogni operatore automatico e assegnare numeri di telefono e licenze. 

## <a name="migration-and-interoperability"></a>Migrazione e interoperabilità

Se si prevede di distribuire Skype for Business Server 2019 e/o Exchange Server 2019, è necessario pianificare attentamente la migrazione per garantire il supporto continuo per gli operatori automatici. Tenere presente quanto segue:

- Exchange Server 2019 non fornisce più la funzionalità di messaggistica unificata di Exchange
- La messaggistica unificata di Exchange è in modalità ritiro
- Skype for Business Server 2019 non si integra più con la messaggistica unificata di Exchange Online

Gli operatori automatici cloud possono essere configurati con Skype for Business Server 2019, 2015 e 2013.

Microsoft consiglia i percorsi di migrazione seguenti:

- Se si esegue l'aggiornamento a Skype for Business Server 2019, è possibile utilizzare la messaggistica unificata di Exchange in Exchange Server 2013 o 2016, ma è necessario eseguire l'aggiornamento all'operatore automatico cloud se si utilizza Exchange Server 2019.

- Se si esegue l'aggiornamento a Exchange Server 2019 e si utilizzano versioni precedenti della messaggistica unificata di Exchange Server per la messaggistica vocale di Skype for Business Server, Microsoft consiglia di eseguire l'aggiornamento a Skype for Business Server 2019 prima dell'aggiornamento delle cassette postali.  In caso contrario, le funzionalità di messaggistica vocale andranno perse.

Per ulteriori informazioni sulla pianificazione della migrazione, vedere [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrazione di un sistema di operatore automatico di messaggistica unificata di Exchange implementato in precedenza

Attualmente non è possibile eseguire la migrazione automatica nel cloud di un sistema di operatore automatico di messaggistica unificata creato in Exchange 2013 o 2016. Per creare di nuovo manualmente un sistema di operatore automatico, è necessario:

1. Utilizzare i comandi di PowerShell dell'amministratore di Exchange per esaminare la struttura del vecchio sistema di operatore automatico, inclusi eventuali operatori automatici annidati e code di chiamata.  
2. Creare copie di script di sintesi vocale o messaggi registrati associati a ogni nodo dell'operatore automatico di messaggistica unificata.
3. Creare endpoint locali per ogni nodo dell'operatore automatico, inclusa l'assegnazione di numeri di telefono di prova e licenze agli oggetti. Tieni presente che ora hai la possibilità di assegnare licenze per i numeri di telefono locali usate dai servizi online come Sistema telefonico.
4. Implementare un nuovo servizio operatore automatico cloud con Microsoft Teams e Sistema telefonico. Per [informazioni dettagliate sull'implementazione, vedere Configure resource accounts.](configure-onprem-ra.md) In questo modo, caricare gli script di sintesi vocale o i messaggi registrati associati a ogni nodo dell'operatore automatico di messaggistica unificata.
5. Testare la funzionalità dell'operatore automatico Cloud.
6. Riassegnare il numero di telefono assegnato al vecchio operatore automatico di messaggistica unificata di Exchange all'operatore automatico cloud principale appena creato.

Per [informazioni dettagliate su questa procedura, vedere Moving an Exchange UM auto attendant or call queue to Phone System.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

Quando si dispone di una struttura solida che soddisfa le proprie esigenze e di uno script che guida i clienti in modo efficiente, passare a [Configurare gli account delle risorse.](configure-onprem-ra.md)

> [!CAUTION]
> Come accennato in [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)lo spostamento degli operatori automatici di messaggistica unificata di Exchange creati in Server 2015 nei server che eseguono Server 2019 è sconsigliato. Per il momento, è necessario mantenerli in un pool di Skype for Business Server 2015 in esecuzione in modalità coesistenza.

## <a name="see-also"></a>Vedere anche

[Pianificare la migrazione per Skype for Business Server ed Exchange Server](plan-um-migration.md)

[Configurare gli account delle risorse](configure-onprem-ra.md)

[Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Cosa sono gli operatori automatici cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/microsoftteams/create-a-phone-system-auto-attendant)

Messaggistica unificata di Exchange: [rispondere e instradare automaticamente le chiamate in arrivo](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](plan-hybrid-connectivity.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[KB4480742: Le chiamate all'accesso sottoscrittore o all'operatore automatico non riescono con la velocità occupata e l'errore "500 Server Interno" dopo lo spostamento degli oggetti contatto in Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)