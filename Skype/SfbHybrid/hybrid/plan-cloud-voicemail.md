---
title: Pianificare il servizio cloud Voicemail per gli utenti locali | PBX Skype for Business Server 2019
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
description: In questo articolo vengono illustrati i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio Microsoft Cloud Voicemail. Per informazioni sulla configurazione del messaggio vocale cloud, vedere Configuring cloud Voicemail.
ms.openlocfilehash: 30a4983c79f4a7cddd274c272b5a094c17653bbb
ms.sourcegitcommit: 7c08d88dcaa85e34e93131bb9a5a64597c6d8155
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210632"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Pianificare il servizio di segreteria cloud per gli utenti locali

## <a name="overview"></a>Panoramica

In questo articolo vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio segreteria telefonica di Microsoft Cloud per gli utenti locali. Per informazioni sulla configurazione del servizio di segreteria cloud, vedere [Configure cloud Voicemail Service](configure-cloud-voicemail.md).

Cloud Voicemail prende il posto della messaggistica unificata di Exchange (UM) nel fornire la funzionalità di messaggistica vocale per gli utenti di Skype for business 2019 Voice che dispongono di cassette postali su Exchange Server 2019 o Exchange Online. Cloud Voicemail offre i vantaggi seguenti sia per gli utenti locali che per quelli online:

- Funzionalità di segreteria telefonica e deposito con una trascrizione avanzata vocale

- Accesso alla segreteria telefonica nella cassetta postale di Exchange dell'utente utilizzando i client Skype for business online o Outlook

- La possibilità di utilizzare il portale basato sul Web di Office 365 per gestire le opzioni della segreteria telefonica

- Supporto per le cassette postali di Exchange in locale o nel cloud

- Utilizzo dei messaggi di saluto degli utenti esistenti dalla messaggistica unificata di Exchange Online

Per ulteriori informazioni sul confronto delle funzionalità, vedere [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Skype for Business Server 2019 continua a utilizzare la messaggistica unificata di Exchange per gli utenti le cui cassette postali si trovano nelle versioni precedenti di Exchange Server (2013, 2016).  È importante comprendere quale soluzione di segreteria telefonica verrà utilizzata sulla base del server Exchange e la versione di Skype for Business Server è una parte essenziale della pianificazione della migrazione su Skype for Business Server 2019 o Exchange Server 2019. Per ulteriori informazioni sulla migrazione e sull'interoperabilità, vedere [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Con il messaggio vocale cloud, le attività di amministrazione sono notevolmente semplificate perché:

- Non è necessario configurare il ruolo di messaggistica unificata di Exchange.
- Le attività di installazione per la segreteria telefonica cloud sono più semplici.
- Gli aggiornamenti alla funzionalità della segreteria telefonica vengono recapitati direttamente nel cloud, per consentire agli utenti di accedere sempre alle funzionalità più recenti e agli aggiornamenti con meno dipendenza dagli aggiornamenti cumulativi (CUs).
- Si dispone dello stesso set di controlli per le cassette postali locali e di Exchange Online. Per ulteriori informazioni su questi controlli, vedere [configurare la segreteria telefonica del sistema telefonico](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

Nel diagramma seguente viene illustrata la segreteria telefonica cloud in una distribuzione ibrida:

![Segreteria telefonica cloud di questo](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Le chiamate senza risposta vengono gestite come indicato di seguito:  

1. Per gli utenti ospitati in Skype for business 2019 in locale, le chiamate senza risposta vengono inviate dal server Skype for business locale al servizio cloud Voicemail online.
2. Il servizio elabora la segreteria telefonica, inclusa la trascrizione.
3. Il servizio depositerà quindi la segreteria telefonica nella cassetta postale di Exchange dell'utente, se la cassetta postale è online o locale.  
4. Gli utenti possono accedere alla segreteria telefonica dal client Skype for business o Outlook.

## <a name="requirements"></a>Requisiti

I requisiti seguenti presumono che sia già stato distribuito Skype for Business Server in una topologia supportata.  I requisiti dipendono dallo scenario:

- Se si sta già utilizzando la messaggistica unificata di Exchange Online e si esegue l'aggiornamento a Skype for business 2019, sarà necessario modificare i criteri di segreteria telefonica ospitata e verificare che i provider di hosting siano impostati correttamente. Per ulteriori informazioni, vedere [Configure cloud Voicemail Service](configure-cloud-voicemail.md).

- Se si utilizza la messaggistica unificata di Exchange in locale oppure se si dispone di una combinazione di utenti che utilizzano la messaggistica unificata di Exchange Online e in locale, è necessario modificare sia il criterio di hosting della segreteria telefonica ospitata sia il provider host.  Per ulteriori informazioni, vedere [Configure cloud Voicemail Service](configure-cloud-voicemail.md).

- Per una nuova configurazione del servizio di segreteria cloud, seguire i passaggi descritti in [Configure cloud Voicemail Service](configure-cloud-voicemail.md).

Oltre ai requisiti di cui sopra, è necessario configurare i requisiti seguenti per la connessione al servizio segreteria telefonica di Microsoft Cloud:

- Connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare la segreteria telefonica cloud per gli utenti locali, è necessario verificare di disporre della connettività ibrida configurata tra gli ambienti locali e online. A volte viene chiamata configurazione di un dominio diviso.

   Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).

- Gli utenti locali devono essere abilitati per VoIP aziendale e per la segreteria telefonica ospitata in Skype for Business Server.

- Un URL di servizi Web Exchange (EWS) esterno e l'individuazione automatica devono essere configurati o alcune funzionalità di segreteria telefonica cloud saranno limitate.

- Se si dispone di una distribuzione solo locale&#x2014;che è solo server Exchange e Skype for business in locale&#x2014;ma si vuole usufruire della segreteria telefonica cloud, è necessaria una licenza di sistema telefonico.

## <a name="migration-and-interoperability"></a>Migrazione e interoperabilità

Se si prevede di distribuire Skype for Business Server 2019 e/o Exchange Server 2019, è necessario pianificare attentamente la migrazione per garantire il servizio continuato per la messaggistica vocale. Tenere presente quanto segue:

- Exchange Server 2019 non fornisce più la funzionalità di messaggistica unificata di Exchange
- Skype for Business Server 2019 non si integra più con la messaggistica unificata di Exchange Online

La funzionalità di interoperabilità della versione e le topologie supportate per il messaggio vocale cloud sono elencate nella tabella seguente, che confronta le versioni di Skype for Business Server a cui l'utente potrebbe essere ospitato con la versione possibile che fornisce la propria cassetta postale di Exchange. Se si desidera utilizzare Skype for business 2019 con Exchange Online o Exchange Server 2019, è necessario utilizzare il messaggio vocale cloud.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Messaggistica unificata di Exchange Server | Messaggistica unificata di Exchange Server | Cloud Voicemail | Cloud Voicemail |
| Skype for Business Server 2015 | Messaggistica unificata di Exchange Server | Messaggistica unificata di Exchange Server | Cloud Voicemail | Cloud Voicemail |
| Lync Server 2013 <br>  | Messaggistica unificata di Exchange Server | Messaggistica unificata di Exchange Server | Non supportata | Cloud Voicemail |

Microsoft consiglia i percorsi di migrazione seguenti:

- Se si esegue l'aggiornamento a Skype for Business Server 2019, è possibile utilizzare la messaggistica unificata di Exchange in Exchange Server 2013 o 2016, ma è necessario eseguire l'aggiornamento a cloud voicemail se si utilizza Exchange Server 2019.
- Se si esegue l'aggiornamento a Exchange Server 2019 e si utilizzano versioni precedenti della messaggistica UNIFICAta di Exchange Server per Skype for Business Server, Microsoft consiglia di eseguire l'aggiornamento a Skype for Business Server 2019 prima dell'aggiornamento della cassetta postale.  In caso contrario, le funzionalità di messaggistica vocale andranno perse.
- Se si esegue l'aggiornamento a Skype for Business Server 2019 e Skype for Business Server 2015 è configurato per la segreteria telefonica con la messaggistica unificata di Exchange Online, la segreteria telefonica degli utenti eseguirà la migrazione automatica dalla messaggistica unificata di Exchange Online alla segreteria telefonica del cloud quando il relativo account viene spostato in Skype for 2019 business 

Per ulteriori informazioni sulla pianificazione della migrazione, vedere [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).
