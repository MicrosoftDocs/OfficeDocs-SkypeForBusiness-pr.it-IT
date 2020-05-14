---
title: Pianificare la migrazione di Skype for Business Server e Exchange Server
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
description: In questo argomento vengono illustrate le operazioni da prendere in considerazione quando si decide di eseguire la migrazione delle distribuzioni esistenti di Skype for Business Server o Exchange Server alla versione più recente o a Skype for business online o Exchange Online.
ms.openlocfilehash: fec12eb5b386222ad0a69115ca3fc9e2de9e2fea
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221266"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Pianificare la migrazione di Skype for Business Server e Exchange Server

In questo argomento vengono illustrate le operazioni da prendere in considerazione quando si decide di eseguire la migrazione delle distribuzioni esistenti di Skype for Business Server o Exchange Server alla versione più recente o a Skype for business online o Exchange Online. Che cosa è possibile eseguire la migrazione e quando, dipende molto da ciò che è stato già configurato nell'organizzazione.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifiche alle funzionalità in Exchange 2019 e Skype for Business Server 2019

Con Exchange 2019 e Skype for Business Server 2019, vengono apportate alcune modifiche alle funzionalità supportate.

### <a name="unified-messaging-support-in-exchange-2019"></a>Supporto della messaggistica unificata in Exchange 2019

La messaggistica unificata (UM) è stata deprecata in Exchange 2019. Questo significa che Exchange 2019 non è più in grado di offrire le caratteristiche seguenti:

- Segreteria telefonica
- Operatore automatico

Se è stato distribuito il ruolo di messaggistica unificata in Exchange 2013 o il servizio di messaggistica unificata in Exchange 2016 e si desidera eseguire l'aggiornamento a Exchange 2019, è necessario eseguire la migrazione della segreteria telefonica al servizio Microsoft Cloud voicemail in Microsoft 365 o Office 365. Se si desidera eseguire la migrazione della segreteria telefonica alla segreteria telefonica cloud, consultare la sezione Exchange [2013/exchange 2016 e Skype for business 2015 a exchange 2019 e Skype for business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) .
> [!IMPORTANT]
> Se gli utenti dei server Exchange 2013 o Exchange 2016 dispongono di cassette postali abilitate alla messaggistica unificata, non spostarli in Exchange 2019 prima di aggiornare i server Skype for business a Skype for Business Server 2019 e spostare gli utenti in modo da evitare un'interruzione della messaggistica vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Supporto PBX in Exchange 2019 e Skype for Business Server 2019

Cloud Voicemail non fornisce funzionalità di messaggistica vocale per i sistemi PBX (Private Branch Exchange). Se si utilizza la messaggistica unificata di Exchange Server per i sistemi PBX e si desidera eseguire l'aggiornamento a Exchange Server 2019, è necessario adottare una delle tre opzioni elencate nel post di Blog [nuovo data per la sospensione del supporto per Session Border Controllers nella messaggistica unificata di Exchange Online nel](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) [Blog del team di Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Supporto per la messaggistica unificata di Exchange online in Skype for Business Server 2019

Con Skype for Business Server 2019, ci muoviamo dalla messaggistica unificata di Exchange Online alla segreteria telefonica cloud. Quando un utente viene spostato in un server Skype for business 2019, inizierà automaticamente a utilizzare la segreteria telefonica cloud quando viene configurato per la segreteria telefonica ospitata. Se si sta attualmente utilizzando la messaggistica unificata di Exchange Online, non è necessario eseguire altre attività se non spostare un utente in Skype for Business Server 2019 per iniziare a usare Cloud Voicemail. Tuttavia, esistono alcune modifiche alla funzionalità che è necessario tenere presenti:

- Operatore automatico organizzativo è la sostituzione per l'operatore automatico nella messaggistica unificata di Exchange Online.
- Le impostazioni della segreteria telefonica degli utenti in Outlook sul Web non si applicano alla segreteria telefonica cloud.

## <a name="on-premises-um-migration-scenarios"></a>Scenari di migrazione della messaggistica unificata locale

Sono supportati gli scenari seguenti che consentono di eseguire la migrazione degli utenti sia a Exchange 2019 che alla segreteria telefonica cloud.

- Exchange 2013/Exchange 2016 e Skype for Business Server 2015 a Exchange 2019 e Skype for Business Server 2019
- Skype for Business Server 2015 to Skype for Business Server 2019 con Exchange 2013/Exchange 2016

Negli scenari seguenti è necessario che non esistano configurazioni PBX o SBC come parte della distribuzione corrente e si presuppone che la messaggistica unificata sia configurata nei server Exchange locali. Ognuna di queste soluzioni presuppone inoltre che sia stata decisa la configurazione di una distribuzione ibrida tra i server Skype for business locali e Microsoft 365 o Office 365. Per ulteriori informazioni sulle distribuzioni ibride di Skype for business, vedere [pianificare la connettività ibrida](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype for business 2015 a Exchange 2019 e Skype for business 2019

In questo scenario, si desidera eseguire la migrazione dei server Exchange 2013, Exchange 2016 e Skype for business 2015 esistenti a Exchange 2019 e Skype for business 2019.

Come accennato in precedenza in questo argomento, Exchange 2019 non include più il servizio di messaggistica unificata. Ciò significa che, per tutte le cassette postali che si desidera spostare in Exchange 2019, è necessario utilizzare il servizio di segreteria telefonica cloud per sostituire la funzionalità fornita da un Service di messaggistica unificata. Quando si configura Skype for Business Server 2019 e una distribuzione ibrida tra it e Microsoft 365 o Office 365, i servizi vocali di messaggistica unificata di Exchange vengono sostituiti da cloud Voicemail.

L'ordine in cui si spostano gli utenti in Exchange 2019 e Skype for Business Server 2019 è fondamentale per garantire che la funzionalità della segreteria telefonica rimanga disponibile per tutti gli utenti. L'elaborazione della segreteria telefonica è determinata anche dalla posizione in cui si trovano le cassette postali e gli utenti di Exchange e Skype for business. Consultare la seguente tabella per vedere quali combinazioni di Exchange e Skype for Business Server sono supportate e dove viene elaborato il messaggio vocale.

| Cassetta postale che si trova su:            | Utente che si trova su Skype for Business Server 2015 | Utente che si trova su Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Messaggistica unificata                             | Messaggistica unificata                              |
| Exchange 2019                  | Non supportato                           | Cloud Voicemail                          |

Prima di iniziare la migrazione a Skype for Business Server 2019 ed Exchange 2019, tenere presente quanto segue:

- Il servizio segreteria telefonica cloud non supporta l'operatore automatico dell'organizzazione in GA. Se si desidera che le cassette postali spostate nel cloud Voicemail continuino a essere disponibili tramite operatore automatico, è necessario mantenere almeno un server Exchange 2013 o Exchange 2016 che esegua il ruolo o il servizio di messaggistica unificata disponibile.
- È necessario configurare almeno un server Skype for business 2019 **e** spostare gli utenti su tale server prima di spostare le cassette postali in Exchange 2019. La mancata esecuzione di questa operazione comporta che le cassette postali non siano in grado di ricevere messaggi vocali.
- Le chiamate inviate alla segreteria telefonica verranno trasferite alla segreteria telefonica cloud in cui verranno registrate. Una volta terminata la chiamata, il messaggio di segreteria telefonica verrà inviato alla cassetta postale del destinatario sul server Exchange 2019 locale. È necessario prendere in considerazione il traffico vocale quando si determina se la connettività Internet è sufficiente per supportare la segreteria telefonica cloud.

Di seguito vengono illustrati i passaggi di alto livello per completare la migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione della distribuzione ibrida per includere il nuovo server Skype for business 2019.
3. Installare e configurare Exchange Server 2019 in un nuovo server.
4. Spostare gli utenti dal server Skype for business 2015 al server Skype for business 2019.
5. Impostare i criteri di segreteria telefonica ospitata per ogni utente spostati in Skype for Business Server 2019 per l'utilizzo del messaggio vocale cloud.
6. Spostare le cassette postali dal server Exchange 2013 o Exchange 2016 al server Exchange 2019.
7. Rimuovere i server Skype for business 2015 dopo che l'ultimo utente è stato spostato fuori di essi.
8. Rimuovere le autorizzazioni dei server Exchange 2013 o Exchange 2016 dopo che l'ultima cassetta postale è stata spostata.

    > [!IMPORTANT]
    > Se si utilizza un operatore automatico, mantenere almeno un Exchange 2013 o Exchange 2016 in esecuzione e disponibile.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 to Skype for Business Server 2019 con Exchange 2013/Exchange 2016

In questo scenario, si desidera eseguire la migrazione del server Skype for business 2015 esistente a Skype for Business Server 2019, ma rimanere su Exchange 2013 o Exchange 2016.

Quando Skype for Business Server 2015 e Skype for Business Server 2019 coesistono nella stessa organizzazione, funzionano perfettamente con la messaggistica unificata di Exchange e la segreteria telefonica sul cloud per garantire che la segreteria telefonica sia recapitata correttamente alle cassette postali di Exchange. Se la messaggistica unificata di Exchange o il cloud Voicemail elabora la segreteria telefonica dipende dal fatto che l'utente si trovi su Skype for Business Server 2015 o su Skype for Business Server 2019:

- Se un utente si trova su Skype for Business Server 2015, la messaggistica unificata di Exchange elaborerà il messaggio di segreteria telefonica.
- Se un utente si trova su Skype for Business Server 2019, la segreteria telefonica cloud elaborerà il messaggio di segreteria telefonica.

Indipendentemente dal fatto che la messaggistica unificata di Exchange o il messaggio di posta elettronica del cloud processi la segreteria telefonica, il messaggio verrà archiviato nella cassetta postale di Exchange dell'utente.

Prima di iniziare la migrazione a Skype for Business Server 2019, tenere presente quanto segue:

- Il servizio segreteria telefonica cloud non supporta l'operatore automatico dell'organizzazione in GA. Se si desidera che le cassette postali spostate nel cloud Voicemail continuino a essere disponibili tramite operatore automatico, è necessario mantenere almeno un server Exchange 2013 o Exchange 2016 che esegua il ruolo o il servizio di messaggistica unificata disponibile.
- Le chiamate inviate alla segreteria telefonica verranno trasferite alla segreteria telefonica cloud in cui verranno registrate. Una volta terminata la chiamata, il messaggio di segreteria telefonica verrà inviato alla cassetta postale del destinatario sul server Exchange locale. È necessario prendere in considerazione il traffico vocale quando si determina se la connettività Internet è sufficiente per supportare la segreteria telefonica cloud.

Di seguito vengono illustrati i passaggi di alto livello per completare la migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione della distribuzione ibrida per includere il nuovo server Skype for business 2019.
3. Spostare gli utenti dal server Skype for business 2015 al server Skype for business 2019.
4. Impostare i criteri di segreteria telefonica ospitata per ogni utente spostati in Skype for Business Server 2019 per l'utilizzo del messaggio vocale cloud.
5. Rimuovere i server Skype for business 2015 dopo che l'ultimo utente è stato spostato fuori di essi.

    > [!IMPORTANT]
    > Se si utilizza un operatore automatico, mantenere almeno un Exchange 2013 o Exchange 2016 in esecuzione e disponibile.
