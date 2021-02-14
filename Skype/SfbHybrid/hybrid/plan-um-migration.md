---
title: Pianificare la migrazione per Skype for Business Server ed Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: Questo argomento illustra cosa è necessario considerare quando si decide di eseguire la migrazione delle distribuzioni esistenti di Skype for Business Server o Exchange Server alla versione più recente o a Skype for Business online o Exchange Online.
ms.openlocfilehash: cb6d58cf839b6260bc8889817ea568528e4832f4
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359042"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Pianificare la migrazione per Skype for Business Server ed Exchange Server

Questo argomento illustra cosa è necessario considerare quando si decide di eseguire la migrazione delle distribuzioni esistenti di Skype for Business Server o Exchange Server a Exchange Online. Cosa è possibile migrare e quando, dipende molto da ciò che è già stato configurato nell'organizzazione.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifiche delle funzionalità in Exchange 2019 e Skype for Business Server 2019

Con Exchange 2019 e Skype for Business Server 2019, stiamo apportando alcune modifiche alle funzionalità supportate.

### <a name="unified-messaging-support-in-exchange-2019"></a>Supporto della messaggistica unificata in Exchange 2019

La messaggistica unificata è stata deprecata in Exchange 2019. Ciò significa che Exchange 2019 non offre più le seguenti funzionalità:

- Messaggi vocali
- Operatore automatico

Se è stato distribuito il ruolo di messaggistica unificata in Exchange 2013 o il servizio di messaggistica unificata in Exchange 2016 e si desidera eseguire l'aggiornamento a Exchange 2019, sarà necessario eseguire la migrazione della segreteria telefonica al servizio Microsoft Cloud Voicemail in Microsoft 365 o Office 365. Se si desidera eseguire la migrazione della segreteria telefonica a Cloud Voicemail, vedere la sezione [Exchange 2013/Exchange 2016 e Skype for Business 2015 a Exchange 2019 e Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) di seguito.
> [!IMPORTANT]
> Se gli utenti sui server Exchange 2013 o Exchange 2016 dispongono di cassette postali abilitate alla messaggistica unificata, non spostarli in Exchange 2019 prima di aggiornare i server Skype for Business a Skype for Business Server 2019 e spostare gli utenti su di essi per evitare un'interruzione della messaggistica vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Supporto PBX in Exchange 2019 e Skype for Business Server 2019

Cloud Voicemail non fornisce funzionalità di messaggistica vocale ai sistemi PBX (Private Branch Exchange). Se si utilizza la messaggistica unificata di Exchange Server per sistemi PBX e si desidera eseguire l'aggiornamento a Exchange Server 2019, è necessario adottare una delle tre opzioni elencate nel post di blog Nuova data per la sospensione del supporto per session [border controller](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) nella messaggistica unificata di Exchange Online sul blog del team di [Exchange.](https://blogs.technet.microsoft.com/exchange/)

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Supporto della messaggistica unificata di Exchange Online in Skype for Business Server 2019

Con Skype for Business Server 2019, si sta passando dalla messaggistica unificata di Exchange Online alla segreteria telefonica cloud. Quando un utente viene spostato in un server Skype for Business 2019, inizierà automaticamente a usare Cloud Voicemail quando è configurato per la segreteria telefonica ospitata. Se attualmente si utilizza la messaggistica unificata di Exchange Online, non è necessario eseguire altre attività oltre a spostare un utente in Skype for Business Server 2019 per iniziare a usare Cloud Voicemail. Esistono tuttavia alcune modifiche alle funzionalità di cui è necessario tenere conto:

- La Operatore automatico organizzativa è la sostituzione dell'operatore automatico nella messaggistica unificata di Exchange Online.
- Le impostazioni della segreteria telefonica dell'utente in Outlook sul Web non si applicano alla segreteria telefonica cloud.

## <a name="on-premises-um-migration-scenarios"></a>Scenari di migrazione della messaggistica unificata locale

Sono supportati i seguenti scenari che consentono di eseguire la migrazione degli utenti sia a Exchange 2019 che a Cloud Voicemail.

- Da Exchange 2013/Exchange 2016 e Skype for Business Server 2015 a Exchange 2019 e Skype for Business Server 2019
- Da Skype for Business Server 2015 a Skype for Business Server 2019 con Exchange 2013/Exchange 2016

I seguenti scenari richiedono che non esistano configurazioni PBX o SBC nell'ambito della distribuzione corrente e presuppongono che la messaggistica unificata sia configurata sui server Exchange locali. Ognuna di queste soluzioni presuppone inoltre che si sia deciso di configurare una distribuzione ibrida tra i server Skype for Business locali e Microsoft 365 o Office 365. Per ulteriori informazioni sulle distribuzioni ibride di Skype for Business, vedere [Pianificare la connettività ibrida.](plan-hybrid-connectivity.md)

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Da Exchange 2013/Exchange 2016 e Skype for Business 2015 a Exchange 2019 e Skype for Business 2019

In questo scenario, si desidera eseguire la migrazione dei server Exchange 2013, Exchange 2016 e Skype for Business 2015 esistenti a Exchange 2019 e Skype for Business 2019.

Come accennato in precedenza in questo argomento, Exchange 2019 non include più il servizio di messaggistica unificata. Ciò significa che, per tutte le cassette postali che si desidera spostare in Exchange 2019, è necessario utilizzare Cloud Voicemail per sostituire la funzionalità fornita dal servizio di messaggistica unificata. Quando si configura Skype for Business Server 2019 e una distribuzione ibrida tra esso e Microsoft 365 o Office 365, Cloud Voicemail sostituisce questi servizi di segreteria telefonica di messaggistica unificata di Exchange.

L'ordine in cui si spostano gli utenti in Exchange 2019 e Skype for Business Server 2019 è fondamentale per garantire che la funzionalità della segreteria telefonica rimanga disponibile per tutti gli utenti. La posizione in cui viene elaborata la segreteria telefonica dipende anche dalla posizione delle cassette postali e degli utenti di Exchange e Skype for Business. Dai un'occhiata alla tabella seguente per vedere quali combinazioni di Exchange e Skype for Business Server sono supportate e dove viene elaborata la segreteria telefonica.

| Cassetta postale che si trova in:            | Utente che si trova su Skype for Business Server 2015 | Utente che si trova su Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Messaggistica unificata                             | Messaggistica unificata                              |
| Exchange 2019                  | Non supportato                           | Cloud Voicemail                          |

Prima di iniziare la migrazione a Skype for Business Server 2019 ed Exchange 2019, tenere presente quanto segue:

- La segreteria telefonica cloud non supporta l'organizzazione Operatore automatico a GA. Se si desidera che le cassette postali spostate in Cloud Voicemail continuino a essere disponibili tramite l'operatore automatico, è necessario mantenere disponibile almeno un server Exchange 2013 o Exchange 2016 che esegue il ruolo o il servizio di messaggistica unificata.
- È necessario configurare almeno un **server** Skype for Business 2019 e spostare gli utenti su tale server prima di spostare le loro cassette postali in Exchange 2019. In caso negativo, le cassette postali non saranno in grado di ricevere messaggi vocali.
- Le chiamate inviate alla segreteria telefonica verranno trasferite alla segreteria telefonica cloud in cui verranno registrate. Al termine della chiamata, il messaggio della segreteria telefonica verrà inviato alla cassetta postale del destinatario sul server Exchange 2019 locale. È necessario prendere in considerazione questo traffico vocale per determinare se la connettività Internet è sufficiente per supportare Cloud Voicemail.

Ecco i passaggi di alto livello per completare questa migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione della distribuzione ibrida per includere il nuovo server Skype for Business 2019.
3. Installare e configurare Exchange Server 2019 in un nuovo server.
4. Spostare gli utenti dal server Skype for Business 2015 al server Skype for Business 2019.
5. Impostare il criterio segreteria telefonica ospitata per ogni utente spostato in Skype for Business Server 2019 per usare Cloud Voicemail.
6. Spostare le cassette postali dal server Exchange 2013 o Exchange 2016 al server Exchange 2019.
7. Rimuovere le autorizzazioni dei server Skype for Business 2015 dopo che l'ultimo utente è stato spostato.
8. Rimuovere le autorizzazioni dei server Exchange 2013 o Exchange 2016 dopo che l'ultima cassetta postale è stata rimossa.

    > [!IMPORTANT]
    > Se si fa affidamento su un operatore automatico, mantenere in esecuzione e disponibile almeno un operatore automatico di Exchange 2013 o Exchange 2016.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Da Skype for Business Server 2015 a Skype for Business Server 2019 con Exchange 2013/Exchange 2016

In questo scenario, si desidera eseguire la migrazione del server Skype for Business 2015 esistente a Skype for Business Server 2019, ma rimanere in Exchange 2013 o Exchange 2016.

Quando Skype for Business Server 2015 e Skype for Business Server 2019 coesistono nella stessa organizzazione, lavorano senza problemi con la messaggistica unificata di Exchange e la segreteria telefonica cloud per garantire che la segreteria telefonica venga recapitata correttamente alle cassette postali di Exchange. L'elaborazione della segreteria telefonica cloud o della messaggistica unificata di Exchange dipende dal fatto che l'utente si trovi in Skype for Business Server 2015 o Skype for Business Server 2019:

- Se un utente si trova in Skype for Business Server 2015, la messaggistica unificata di Exchange eelaborare il messaggio della segreteria telefonica.
- Se un utente si trova in Skype for Business Server 2019, Cloud Voicemail eelaborare il messaggio della segreteria telefonica.

Indipendentemente dal fatto che la messaggistica unificata di Exchange o Cloud Voicemail esecu il messaggio vocale, il messaggio verrà archiviato nella cassetta postale di Exchange dell'utente.

Prima di iniziare la migrazione a Skype for Business Server 2019, tenere presente quanto segue:

- La segreteria telefonica cloud non supporta l'organizzazione Operatore automatico a GA. Se si desidera che le cassette postali spostate in Cloud Voicemail continuino a essere disponibili tramite l'operatore automatico, è necessario mantenere disponibile almeno un server Exchange 2013 o Exchange 2016 che esegue il ruolo o il servizio di messaggistica unificata.
- Le chiamate inviate alla segreteria telefonica verranno trasferite alla segreteria telefonica cloud in cui verranno registrate. Al termine della chiamata, il messaggio della segreteria telefonica verrà inviato alla cassetta postale del destinatario sul server Exchange locale. È necessario prendere in considerazione questo traffico vocale per determinare se la connettività Internet è sufficiente per supportare Cloud Voicemail.

Ecco i passaggi di alto livello per completare questa migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione della distribuzione ibrida per includere il nuovo server Skype for Business 2019.
3. Spostare gli utenti dal server Skype for Business 2015 al server Skype for Business 2019.
4. Impostare il criterio segreteria telefonica ospitata per ogni utente spostato in Skype for Business Server 2019 per usare Cloud Voicemail.
5. Rimuovere le autorizzazioni dei server Skype for Business 2015 dopo che l'ultimo utente è stato spostato.

    > [!IMPORTANT]
    > Se si fa affidamento su un operatore automatico, mantenere in esecuzione e disponibile almeno un operatore automatico di Exchange 2013 o Exchange 2016.
