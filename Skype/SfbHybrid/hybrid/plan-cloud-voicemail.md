---
title: Pianificare il servizio Cloud Voicemail per gli utenti locali| PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: In questo articolo vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio Microsoft Cloud Voicemail. Per informazioni sulla configurazione di Cloud Voicemail, vedere Configuring Cloud Voicemail.
ms.openlocfilehash: 4ae274f33d2b7d52c486cd9031d01bc3a532a6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110282"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Pianificare il servizio Cloud Voicemail per gli utenti locali

## <a name="overview"></a>Panoramica

In questo articolo vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio Microsoft Cloud Voicemail per gli utenti locali. Per informazioni sulla configurazione di Cloud Voicemail, vedere [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

Cloud Voicemail prende il posto della messaggistica unificata di Exchange nel fornire funzionalità di messaggistica vocale per gli utenti vocali di Skype for Business 2019 che dispongono di cassette postali su Exchange Server 2019 o Exchange Online. Cloud Voicemail offre i vantaggi seguenti sia per gli utenti locali che per gli utenti online:

- Funzionalità di segreteria telefonica e deposito con trascrizione vocale avanzata

- Accesso alla segreteria telefonica nella cassetta postale di Exchange dell'utente tramite i client Skype for Business online o Outlook

- Possibilità di usare l'interfaccia di amministrazione di Microsoft 365 per gestire le opzioni della segreteria telefonica

- Supporto per le cassette postali di Exchange in locale o nel cloud

- Utilizzo dei messaggi di saluto degli utenti esistenti dalla messaggistica unificata di Exchange Online

> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021, dopo di che gli utenti non potranno più accedere alla segreteria telefonica nella cassetta postale di Exchange tramite il client Skype for Business online.

Per ulteriori informazioni sul confronto delle funzionalità, vedere [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Skype for Business Server 2019 continua a utilizzare la messaggistica unificata di Exchange per gli utenti le cui cassette postali sono in versioni precedenti di Exchange Server (2013, 2016).  Comprendere quale soluzione di segreteria telefonica verrà utilizzata in base alla versione di Exchange Server e Skype for Business Server è una parte importante della pianificazione della migrazione a Skype for Business Server 2019 o Exchange Server 2019. Per ulteriori informazioni sulla migrazione e l'interoperabilità, vedere [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Con Cloud Voicemail, le attività di amministrazione sono notevolmente semplificate perché:

- Non è necessario configurare il ruolo di messaggistica unificata di Exchange.
- Le attività di configurazione per Cloud Voicemail sono più semplici.
- Gli aggiornamenti alla funzionalità di segreteria telefonica vengono recapitati direttamente nel cloud, quindi gli utenti hanno sempre accesso alle funzionalità e agli aggiornamenti più recenti con una minore dipendenza dagli aggiornamenti cumulativi .
- Si dispone dello stesso set di controlli per le cassette postali di Exchange locali e online. Per ulteriori informazioni su questi controlli, vedere [Set up Phone System voicemail](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

Il diagramma seguente mostra Cloud Voicemail in una distribuzione ibrida:

![SfB Cloud Voicemail](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Le chiamate senza risposta vengono gestite come segue:  

1. Per gli utenti ospitati in Skype for Business 2019 in locale, le chiamate senza risposta vengono inviate da Skype for Business Server locale al servizio di segreteria telefonica cloud online.
2. Il servizio elabora la segreteria telefonica, inclusa la trascrizione.
3. Il servizio deposita quindi la segreteria telefonica nella cassetta postale di Exchange dell'utente, indipendentemente dal fatto che la cassetta postale sia locale o online.  
4. Gli utenti possono accedere alla segreteria telefonica dal proprio client Skype for Business o Outlook.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che Skype for Business Server sia già stato distribuito in una topologia supportata.  I requisiti dipendono dal proprio scenario:

- Se si utilizza già la messaggistica unificata di Exchange online e si esegue l'aggiornamento a Skype for Business 2019, sarà necessario modificare i criteri di segreteria telefonica ospitata e verificare che i provider di hosting siano impostati correttamente. Per ulteriori informazioni, vedere [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Se si utilizza la messaggistica unificata di Exchange in locale o si dispone di una combinazione di utenti che utilizzano la messaggistica unificata di Exchange online e locale, sarà necessario modificare sia i criteri di segreteria telefonica ospitata che il provider di hosting.  Per ulteriori informazioni, vedere [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Per una nuova configurazione di Cloud Voicemail, seguire i passaggi descritti in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

Oltre ai requisiti precedenti, i requisiti seguenti devono essere configurati per connettersi al servizio Microsoft Cloud Voicemail:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare Cloud Voicemail per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e Configurare la connettività ibrida tra Skype for Business Server e [Office 365.](configure-hybrid-connectivity.md)

- Gli utenti locali devono essere abilitati per VoIP aziendale e segreteria telefonica ospitata in Skype for Business Server.

- È necessario configurare un URL e l'individuazione automatica dei servizi Web Exchange esterni oppure alcune funzionalità di Cloud Voicemail saranno limitate.

- Se si dispone di un server Exchange locale, configurare Cloud Voicemail utilizzando la procedura descritta in [Set up Cloud Voicemail for Exchange Server Mailbox Users](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).

## <a name="migration-and-interoperability"></a>Migrazione e interoperabilità

Se si prevede di distribuire Skype for Business Server 2019 e/o Exchange Server 2019, è necessario pianificare con attenzione la migrazione per garantire un servizio continuo per la messaggistica vocale. Tenere presente quanto segue:

- Exchange Server 2019 non fornisce più la funzionalità di messaggistica unificata di Exchange
- Skype for Business Server 2019 non si integra più con la messaggistica unificata di Exchange Online

L'interoperabilità delle versioni e le topologie supportate per Cloud Voicemail sono elencate nella tabella seguente, che confronta le versioni di Skype for Business Server su cui l'utente potrebbe essere ospitata con la versione possibile che fornisce la propria cassetta postale di Exchange. Devi usare Cloud Voicemail se vuoi usare Skype for Business 2019 con Exchange Online o Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server messaggistica unificata | Exchange Server messaggistica unificata | Cloud Voicemail | Cloud Voicemail |
| Skype for Business Server 2015 | Exchange Server messaggistica unificata | Exchange Server messaggistica unificata | Non supportato | Cloud Voicemail |
| Lync Server 2013 <br>  | Exchange Server messaggistica unificata | Exchange Server messaggistica unificata | Non supportato | Cloud Voicemail |

Microsoft consiglia i percorsi di migrazione seguenti:

- Se si esegue l'aggiornamento a Skype for Business Server 2019, è possibile utilizzare la messaggistica unificata di Exchange in Exchange Server 2013 o 2016, ma è necessario eseguire l'aggiornamento a Cloud Voicemail se si utilizza Exchange Server 2019.
- Se si esegue l'aggiornamento a Exchange Server 2019 e si utilizzano versioni precedenti della messaggistica unificata di Exchange Server per la messaggistica vocale di Skype for Business Server, Microsoft consiglia di eseguire l'aggiornamento a Skype for Business Server 2019 prima dell'aggiornamento delle cassette postali.  In caso contrario, le funzionalità di messaggistica vocale andranno perse.
- Se si esegue l'aggiornamento a Skype for Business Server 2019 e Skype for Business Server 2015 è configurato per la segreteria telefonica con la messaggistica unificata di Exchange Online, la segreteria telefonica degli utenti eseguirà automaticamente la migrazione dalla messaggistica unificata di Exchange Online alla segreteria telefonica cloud quando l'account viene spostato in Skype for Business Server 2019. 

Per ulteriori informazioni sulla pianificazione della migrazione, vedere [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).