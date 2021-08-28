---
title: Pianificare Cloud Voicemail servizio per gli utenti locali| PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: In questo articolo vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del Microsoft Cloud Voicemail servizio. Per informazioni sulla configurazione Cloud Voicemail, vedere Configuring Cloud Voicemail.
ms.openlocfilehash: df9675c7ebe36f73190240dc612ce83dd0de2263
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594870"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Pianificare Cloud Voicemail per gli utenti locali

## <a name="overview"></a>Panoramica

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In questo articolo vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio di Microsoft Cloud Voicemail per gli utenti locali. Per informazioni sulla configurazione di Cloud Voicemail, vedere [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

Cloud Voicemail prende il posto di Exchange Messaggistica unificata nel fornire funzionalità di messaggistica vocale per gli utenti vocali di Skype for Business 2019 che dispongono di cassette postali su Exchange Server 2019 o Exchange Online. Cloud Voicemail offre i vantaggi seguenti sia per gli utenti locali che per gli utenti online:

- Funzionalità di segreteria telefonica e deposito con trascrizione vocale avanzata

- Accesso alla segreteria telefonica nella cassetta postale Exchange'utente tramite Skype for Business Online o Outlook client

- Possibilità di utilizzare il interfaccia di amministrazione di Microsoft 365 per gestire le opzioni della segreteria telefonica

- Supporto per Exchange cassette postali locali o nel cloud

- Utilizzo dei messaggi di saluto degli utenti esistenti Exchange Online messaggistica unificata

> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021, dopo di che gli utenti non potranno più accedere alla segreteria telefonica nella propria cassetta postale Exchange tramite il client Skype for Business Online.

Per ulteriori informazioni sul confronto delle funzionalità, vedere [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Skype for Business Server 2019 continua a utilizzare la messaggistica unificata di Exchange per gli utenti le cui cassette postali sono in versioni precedenti di Exchange Server (2013, 2016).  Comprendere quale soluzione di segreteria telefonica verrà utilizzata in base alla versione Exchange Server e Skype for Business Server è una parte importante della pianificazione della migrazione a Skype for Business Server 2019 o Exchange Server 2019. Per ulteriori informazioni sulla migrazione e l'interoperabilità, vedere [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Con Cloud Voicemail, le attività di amministrazione sono notevolmente semplificate perché:

- Non è necessario configurare il ruolo Exchange messaggistica unificata.
- Le attività di configurazione per Cloud Voicemail sono più semplici.
- Gli aggiornamenti alla funzionalità di segreteria telefonica vengono recapitati direttamente nel cloud, quindi gli utenti hanno sempre accesso alle funzionalità e agli aggiornamenti più recenti con una minore dipendenza dagli aggiornamenti cumulativi.
- Si dispone dello stesso set di controlli sia per le cassette postali locali che per Exchange online. Per ulteriori informazioni su questi controlli, vedere [Set up Sistema telefonico voicemail](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

Il diagramma seguente mostra Cloud Voicemail in una distribuzione ibrida:

![SfB Cloud Voicemail](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Le chiamate senza risposta vengono gestite come segue:  

1. Per gli utenti ospitati in Skype for Business 2019 locale, le chiamate senza risposta vengono inviate dal Skype for Business Server locale al servizio di Cloud Voicemail online.
2. Il servizio elabora la segreteria telefonica, inclusa la trascrizione.
3. Il servizio deposita quindi la segreteria telefonica nella Exchange dell'utente, indipendentemente dal fatto che la cassetta postale sia locale o online.  
4. Gli utenti possono accedere alla segreteria telefonica dal Skype for Business o Outlook client.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che siano già Skype for Business Server distribuiti in una topologia supportata.  I requisiti dipendono dal proprio scenario:

- Se si utilizza già la messaggistica unificata di Exchange online e si esegue l'aggiornamento a Skype for Business 2019, sarà necessario modificare i criteri della segreteria telefonica ospitata e verificare che i provider di hosting siano impostati correttamente. Per ulteriori informazioni, vedere [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Se si utilizza la messaggistica unificata di Exchange locale o si dispone di una combinazione di utenti che utilizzano la messaggistica unificata di Exchange online e locale, sarà necessario modificare sia il criterio segreteria telefonica ospitata che il provider di hosting.  Per ulteriori informazioni, vedere [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Per una nuova configurazione di Cloud Voicemail, seguire i passaggi descritti in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

Oltre ai requisiti sopra indicati, è necessario configurare i requisiti seguenti per la connessione al Microsoft Cloud Voicemail servizio:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare Cloud Voicemail per gli utenti locali, è necessario assicurarsi di disporre della connettività ibrida impostata tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and Configure hybrid connectivity between Skype for Business Server and [Office 365](configure-hybrid-connectivity.md).

- Gli utenti locali devono essere abilitati per VoIP aziendale e segreteria telefonica ospitata in Skype for Business Server.

- È necessario configurare un URL Exchange Web Services (EWS) esterno e l'individuazione automatica oppure alcune funzionalità Cloud Voicemail saranno limitate.

- Se si dispone di un server Exchange locale, configurare Cloud Voicemail utilizzando la procedura descritta in [Set up Cloud Voicemail for Exchange Server Mailbox Users](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).

## <a name="migration-and-interoperability"></a>Migrazione e interoperabilità

Se si prevede di distribuire Skype for Business Server 2019 e/o Exchange Server 2019, è necessario pianificare attentamente la migrazione per garantire un servizio continuo per la messaggistica vocale. Tenere presente quanto segue:

- Exchange Server 2019 non fornisce più la funzionalità Exchange messaggistica unificata
- Skype for Business Server 2019 non si integra più con Exchange Online messaggistica unificata

L'interoperabilità delle versioni e le topologie supportate per Cloud Voicemail sono elencate nella tabella seguente, che confronta le versioni di Skype for Business Server in cui l'utente potrebbe essere ospitata con la versione possibile che fornisce la propria cassetta postale Exchange. È necessario usare Cloud Voicemail se si vuole usare Skype for Business 2019 con Exchange Online o Exchange Server 2019.

| Skype/Lync | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server Messaggistica unificata | Exchange Server Messaggistica unificata | Cloud Voicemail | Cloud Voicemail |
| Skype for Business Server 2015 | Exchange Server Messaggistica unificata | Exchange Server Messaggistica unificata | Non supportato | Cloud Voicemail |
| Lync Server 2013 <br>  | Exchange Server Messaggistica unificata | Exchange Server Messaggistica unificata | Non supportato | Cloud Voicemail |

Microsoft consiglia i percorsi di migrazione seguenti:

- Se si esegue l'aggiornamento a Skype for Business Server 2019, è possibile utilizzare la messaggistica unificata di Exchange Exchange Server 2013 o 2016, ma è necessario eseguire l'aggiornamento a Cloud Voicemail se si utilizza Exchange Server 2019.
- Se si esegue l'aggiornamento a Exchange Server 2019 e si utilizzano versioni precedenti della messaggistica unificata di Exchange Server per la messaggistica vocale di Skype for Business Server, Microsoft consiglia di eseguire l'aggiornamento a Skype for Business Server 2019 prima dell'aggiornamento delle cassette postali.  In caso contrario, le funzionalità di messaggistica vocale andranno perse.
- Se si esegue l'aggiornamento Skype for Business Server Skype for Business Server 2019 e Skype for Business Server 2015 è configurato per la segreteria telefonica con la messaggistica unificata di Exchange Online, la segreteria telefonica degli utenti eseguirà automaticamente la migrazione dalla messaggistica unificata di Exchange Online Cloud Voicemail quando l'account viene spostato Skype for Business Server 2019. 

Per ulteriori informazioni sulla pianificazione della migrazione, vedere [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).