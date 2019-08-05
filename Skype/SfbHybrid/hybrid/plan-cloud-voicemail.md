---
title: Pianificare il servizio di segreteria cloud per gli utenti locali | PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Questo articolo descrive i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio Microsoft Cloud Voicemail. Per informazioni sulla configurazione della segreteria telefonica cloud, vedere Configurazione della segreteria telefonica cloud.
ms.openlocfilehash: 0071154ab1b9c1211725dd9b6addc2dfd5449e15
ms.sourcegitcommit: 46fb558814cb6bd7d70729eac590afd51fc6606e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2019
ms.locfileid: "36185531"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Pianificare il servizio cloud Voicemail per gli utenti locali

## <a name="overview"></a>Panoramica

Questo articolo descrive i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio Microsoft Cloud Voicemail per gli utenti locali. Per informazioni sulla configurazione della segreteria telefonica cloud, vedere [configurare il servizio cloud Voicemail](configure-cloud-voicemail.md).

Cloud Voicemail prende la posizione di messaggistica UNIFICAta di Exchange per fornire funzionalità di messaggistica vocale per gli utenti di Skype for business 2019 Voice che dispongono di cassette postali su Exchange Server 2019 o Exchange Online. Cloud Voicemail offre i vantaggi seguenti per gli utenti locali e online:

- Funzionalità di risposta e deposito della segreteria telefonica con trascrizione avanzata vocale

- Accesso alla segreteria telefonica nella cassetta postale di Exchange dell'utente usando i client Skype for business online o Outlook

- Possibilità di usare il portale basato sul Web di Office 365 per gestire le opzioni della segreteria telefonica

- Supporto per le cassette postali di Exchange in locale o nel cloud

- Uso dei messaggi di saluto degli utenti esistenti dalla messaggistica unificata di Exchange Online

Per altre informazioni sul confronto delle caratteristiche, vedere [pianificare la migrazione a Skype for Business Server e Exchange Server](plan-um-migration.md).

Skype for Business Server 2019 continua a usare la messaggistica unificata di Exchange per gli utenti le cui cassette postali si trovano nelle versioni precedenti di Exchange Server (2013, 2016).  Capire quale soluzione vocale verrà usata in base a Exchange Server e la versione di Skype for Business Server è una parte importante della pianificazione della migrazione a Skype for Business Server 2019 o Exchange Server 2019. Per altre informazioni sulla migrazione e l'interoperabilità, vedere [pianificare la migrazione a Skype for Business Server e Exchange Server](plan-um-migration.md).

Con Cloud voicemail, le attività di amministrazione sono molto semplificate perché:

- Non è necessario configurare il ruolo di messaggistica unificata di Exchange.
- Le attività di configurazione per la segreteria telefonica cloud sono più semplici.
- Gli aggiornamenti della funzionalità della segreteria telefonica vengono recapitati direttamente nel cloud, in modo che gli utenti abbiano sempre accesso alle funzionalità e agli aggiornamenti più recenti con meno dipendenza dagli aggiornamenti cumulativi (CUs).
- Si ha lo stesso set di controlli per cassette postali di Exchange locali e online. Per altre informazioni su questi controlli, vedere [configurare la segreteria telefonica del sistema telefonico](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

Il diagramma seguente mostra la segreteria telefonica cloud in una distribuzione ibrida:

![Segreteria telefonica cloud di SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Le chiamate senza risposta vengono gestite nel modo seguente:  

1. Per gli utenti ospitati in Skype for business 2019 in locale, le chiamate senza risposta vengono inviate dal server Skype for business locale al servizio online cloud Voicemail.
2. Il servizio elabora la segreteria telefonica, inclusa la trascrizione.
3. Il servizio depositerà quindi la segreteria telefonica nella cassetta postale di Exchange dell'utente, indipendentemente dal fatto che la cassetta postale sia locale o online.  
4. Gli utenti possono accedere alla segreteria telefonica sia dal client Skype for business che da Outlook.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che si disponga già di Skype for Business Server distribuito in una topologia supportata.  I requisiti dipendono dallo scenario:

- Se si sta già usando la messaggistica unificata di Exchange Online e si esegue l'aggiornamento a Skype for business 2019, sarà necessario modificare i criteri di segreteria telefonica ospitata e verificare che i provider di hosting siano impostati correttamente. Per altre informazioni, vedere [configurare il servizio di segreteria telefonica cloud](configure-cloud-voicemail.md).

- Se si usa la messaggistica unificata di Exchange in locale oppure si ha una combinazione di utenti che usano la messaggistica unificata di Exchange Online e in locale, è necessario modificare sia il proprio criterio di hosting della segreteria telefonica ospitata che il provider.  Per altre informazioni, vedere [configurare il servizio di segreteria telefonica cloud](configure-cloud-voicemail.md).

- Per una nuova configurazione di cloud voicemail, seguire i passaggi descritti in configurare il [servizio di segreteria telefonica cloud](configure-cloud-voicemail.md).

Oltre ai requisiti descritti sopra, i requisiti seguenti devono essere configurati per la connessione al servizio Microsoft Cloud Voicemail:

- Connettività ibrida. Se è già stato implementato Skype for Business Server e si vuole abilitare il cloud Voicemail per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di domini divisi.

   Per altre informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).

- Gli utenti locali devono essere abilitati per VoIP aziendale e la segreteria telefonica ospitata in Skype for Business Server.

- Un URL di servizi Web Exchange (EWS) esterno e l'individuazione automatica devono essere configurati o alcune funzionalità per la segreteria telefonica cloud saranno limitate.

- Se si dispone di una distribuzione locale solo&#x2014;ovvero solo i server Exchange e Skype for business locali&#x2014;ma si vuole sfruttare i vantaggi del cloud voicemail, non saranno necessarie altre licenze.

## <a name="migration-and-interoperability"></a>Migrazione e interoperabilità

Se si prevede di distribuire Skype for Business Server 2019 e/o Exchange Server 2019, è necessario pianificare con attenzione la migrazione per garantire un servizio continuo per la messaggistica vocale. Tieni presente quanto segue:

- Exchange Server 2019 non fornisce più la funzionalità di messaggistica unificata di Exchange
- Skype for Business Server 2019 non si integra più con la messaggistica unificata di Exchange Online

L'interoperabilità delle versioni e le topologie supportate per la segreteria telefonica cloud sono elencate nella tabella seguente, che confronta le versioni di Skype for Business Server a cui l'utente può partecipare con la versione possibile che fornisce la cassetta postale di Exchange. Cloud Voicemail funziona solo con Skype for Business Server e Exchange Server 2019 o Exchange Online.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Messaggistica unificata di Exchange Server | Messaggistica unificata di Exchange Server | Cloud Voicemail | Cloud Voicemail |
| Skype for Business Server 2015 | Messaggistica unificata di Exchange Server | Messaggistica unificata di Exchange Server | Segreteria telefonica Cloud<sup>1</sup> | Cloud Voicemail <br> Messaggistica unificata<sup></sup> di Exchange Online |
| Lync Server 2013 <br>  | Messaggistica unificata di Exchange Server | Messaggistica unificata di Exchange Server | Non supportato | Cloud Voicemail <br> Messaggistica unificata<sup></sup> di Exchange Online |

<sup>1</sup> l'opzione non è ancora visibile? Attualmente viene implementato e potrebbe non essere ancora disponibile nell'organizzazione. Vedere il passaggio 6, valutare la possibilità di optare per il [supporto della migrazione della messaggistica unificata di Exchange](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support
) per l'opt-in per la connettività pianificata a cloud Voicemail.

<sup>2</sup> fino a deprecated. Per altre informazioni, vedere Supporto per la [migrazione della messaggistica unificata di Exchange Online](../../sfbserver2019/plan/exchange-unified-messaging-online-migration-support.md) . 

Microsoft consiglia i percorsi di migrazione seguenti:

- Se si esegue l'aggiornamento a Skype for Business Server 2019, è possibile usare la messaggistica unificata di Exchange in Exchange Server 2013 o 2016, ma è necessario eseguire l'aggiornamento a cloud voicemail se si usa Exchange Server 2019.
- Se si esegue l'aggiornamento a Exchange Server 2019 e si usano versioni precedenti della messaggistica UNIFICAta di Exchange Server per Skype for Business Server, Microsoft consiglia di eseguire l'aggiornamento a Skype for Business Server 2019 prima dell'aggiornamento delle cassette postali.  In caso contrario, le funzionalità di messaggistica vocale andranno perse.
- Se si esegue l'aggiornamento a Skype for Business Server 2019 e si usa Skype for Business Server 2015 configurato per la segreteria telefonica con la messaggistica unificata di Exchange Online, la segreteria telefonica degli utenti eseguirà automaticamente la migrazione dalla messaggistica unificata di Exchange Online alla segreteria telefonica cloud quando l'account Skype for Business Server 2019. 

Per altre informazioni sulla pianificazione della migrazione, vedere [pianificare la migrazione a Skype for Business Server e Exchange Server](plan-um-migration.md).
