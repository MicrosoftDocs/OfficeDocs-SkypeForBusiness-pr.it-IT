---
title: Pianificare la migrazione a Skype for Business Server e Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: Questo argomento illustra le informazioni che è necessario prendere in considerazione quando si decide di eseguire la migrazione delle distribuzioni esistenti di Skype for Business Server o Exchange Server alla versione più recente o a Skype for business online o Exchange Online.
ms.openlocfilehash: b1e7f52da2f036ebf88b4a8986650bfbc20c38b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "36185429"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Pianificare la migrazione a Skype for Business Server e Exchange Server

Questo argomento illustra le informazioni che è necessario prendere in considerazione quando si decide di eseguire la migrazione delle distribuzioni esistenti di Skype for Business Server o Exchange Server alla versione più recente o a Skype for business online o Exchange Online. Che cosa è possibile eseguire la migrazione e quando, dipende molto da ciò che è già stato configurato nell'organizzazione. Alcune caratteristiche, come l'operatore automatico dell'organizzazione, non sono disponibili presso la disponibilità generale (GA), ma verranno più avanti in 2018.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifiche alle funzionalità in Exchange 2019 e Skype for Business Server 2019

Con Exchange 2019 e Skype for Business Server 2019, apportiamo alcune modifiche alle funzionalità supportate.

### <a name="unified-messaging-support-in-exchange-2019"></a>Supporto della messaggistica unificata in Exchange 2019

La messaggistica unificata è stata deprecata in Exchange 2019. Questo significa che Exchange 2019 non offre più le caratteristiche seguenti:

- Casella vocale
- Operatore automatico

Se il ruolo di messaggistica unificata è stato distribuito in Exchange 2013 o nel servizio di messaggistica unificata in Exchange 2016 e si vuole eseguire l'aggiornamento a Exchange 2019, è necessario eseguire la migrazione della segreteria telefonica al servizio Microsoft Cloud voicemail in Office 365. Se si vuole eseguire la migrazione della segreteria telefonica a cloud voicemail, vedere la sezione Exchange [2013/exchange 2016 e Skype for business 2015 a exchange 2019 e Skype for business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) .
> [!IMPORTANT]
> Se gli utenti dei server Exchange 2013 o Exchange 2016 dispongono di cassette postali abilitate per la messaggistica unificata, non spostarle in Exchange 2019 prima di aggiornare i server Skype for business a Skype for Business Server 2019 e trasferire gli utenti per evitare un'interruzione di messaggistica vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Supporto PBX in Exchange 2019 e Skype for Business Server 2019

Cloud Voicemail non offre la funzionalità di messaggistica vocale per i PBX (Private Branch Exchange). Se si usa la messaggistica unificata di Exchange Server per i PBX e si vuole eseguire l'aggiornamento a Exchange Server 2019, è necessario adottare una delle tre opzioni elencate nel post di Blog [nuova data per la sospensione del supporto per i controller di bordo della sessione in Exchange Messaggistica unificata online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) nel [Blog del team di Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Supporto della messaggistica unificata di Exchange online in Skype for Business Server 2019

Con Skype for Business Server 2019, stiamo passando dalla messaggistica unificata di Exchange Online alla segreteria telefonica cloud. Quando un utente viene spostato in un server Skype for business 2019, inizierà automaticamente a usare Cloud Voicemail quando è configurato per la segreteria telefonica ospitata. Se si usa la messaggistica unificata di Exchange Online, non è necessario fare altro che trasferire un utente in Skype for Business Server 2019 per iniziare a usare Cloud Voicemail. Ci sono tuttavia alcune modifiche alle funzionalità che è necessario tenere presenti:

- L'operatore automatico dell'organizzazione (il sostituto dell'operatore automatico nella messaggistica unificata di Exchange Online) non è disponibile in GA, ma sarà disponibile più avanti in 2018.
- Le impostazioni della segreteria telefonica dell'utente in Outlook sul Web non si applicano alla segreteria telefonica cloud.

## <a name="on-premises-um-migration-scenarios"></a>Scenari di migrazione di messaggistica unificata locale

Supportiamo gli scenari seguenti che consentono di eseguire la migrazione degli utenti sia a Exchange 2019 che a cloud Voicemail. Più avanti in 2018 verranno supportati altri scenari che consentono di eseguire la migrazione da altre versioni di Exchange e da Skype for Business Server. Verranno fornite anche funzionalità aggiuntive come l'operatore automatico dell'organizzazione.

- Exchange 2013/Exchange 2016 e Skype for Business Server 2015 a Exchange 2019 e Skype for Business Server 2019
- Skype for Business Server 2015 per Skype for Business Server 2019 con Exchange 2013/Exchange 2016

Gli scenari seguenti richiedono che non esistano configurazioni PBX o SBC come parte della distribuzione corrente e si presuppone che la messaggistica unificata sia stata configurata nei server di Exchange locali. Ognuna di queste soluzioni presuppone inoltre che sia stata decisa la configurazione di una distribuzione ibrida tra i server Skype for business locali e Office 365. Per altre informazioni sulle distribuzioni ibride di Skype for business, vedere [pianificare la connettività ibrida](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype for business 2015 a Exchange 2019 e Skype for business 2019

In questo scenario si vuole eseguire la migrazione dei server Exchange 2013, Exchange 2016 e Skype for business 2015 in Exchange 2019 e Skype for business 2019.

Come accennato in precedenza in questo argomento, Exchange 2019 non include più il servizio di messaggistica unificata. Ciò significa che, per tutte le cassette postali che si vuole trasferire in Exchange 2019, è necessario usare il messaggio vocale cloud per sostituire le funzionalità fornite dal servizio di messaggistica unificata. Quando si configura Skype for Business Server 2019 e una distribuzione ibrida tra it e Office 365, i servizi vocali di messaggistica unificata di Exchange vengono sostituiti da cloud Voicemail.

L'ordine in cui si trasferiscono gli utenti a Exchange 2019 e Skype for Business Server 2019 è fondamentale per garantire che la funzionalità della segreteria telefonica rimanga disponibile per tutti gli utenti. La posizione di elaborazione della segreteria telefonica dipende anche dalla posizione in cui si trovano le cassette postali e gli utenti di Exchange e Skype for business. Ecco la tabella seguente per vedere quali combinazioni di Exchange e Skype for Business Server sono supportate e dove viene elaborato il messaggio vocale.

| Cassetta postale situata in:            | Utente che si trova in Skype for Business Server 2015 | Utente che si trova in Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Messaggistica unificata di Exchange                             | Messaggistica unificata di Exchange                              |
| Exchange 2019                  | Non supportato                           | Cloud Voicemail                          |

Prima di iniziare la migrazione a Skype for Business Server 2019 ed Exchange 2019, tieni presente quanto segue:

- Cloud Voicemail non supporta l'operatore automatico dell'organizzazione in GA. Se si vuole che le cassette postali spostate nel cloud Voicemail continuino a essere disponibili tramite operatore automatico, è necessario mantenere almeno un server Exchange 2013 o Exchange 2016 che esegua il ruolo o il servizio di messaggistica unificata disponibile.
- È necessario configurare almeno un server Skype for business 2019 **e** trasferire gli utenti nel server prima di trasferire le cassette postali in Exchange 2019. In caso contrario, le cassette postali non saranno in grado di ricevere messaggi della segreteria telefonica.
- Le chiamate inviate alla segreteria telefonica verranno trasferite alla segreteria telefonica cloud in cui verranno registrate. Una volta terminata la chiamata, il messaggio della segreteria telefonica verrà inviato alla cassetta postale del destinatario nel server di Exchange 2019 locale. È necessario prendere in considerazione questo traffico vocale per determinare se la connettività Internet è sufficiente per supportare la segreteria telefonica cloud.

Ecco i passaggi di alto livello per completare la migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione di distribuzione ibrida per includere il nuovo server Skype for business 2019.
3. Installare e configurare Exchange Server 2019 in un nuovo server.
4. Trasferire gli utenti dal server Skype for business 2015 al server Skype for business 2019.
5. Impostare i criteri di segreteria telefonica ospitata per ogni utente spostati in Skype for Business Server 2019 per usare la segreteria telefonica cloud.
6. Trasferire le cassette postali dal server Exchange 2013 o Exchange 2016 al server Exchange 2019.
7. Rimuovere i server di Skype for business 2015 dopo che l'ultimo utente è stato spostato.
8. Rimuovere la Commissione dei server Exchange 2013 o Exchange 2016 dopo che l'ultima cassetta postale è stata spostata.

    > [!IMPORTANT]
    > Se si basa su un operatore automatico, è possibile conservare almeno un Exchange 2013 o Exchange 2016 in uso e disponibile.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 per Skype for Business Server 2019 con Exchange 2013/Exchange 2016

In questo scenario si vuole eseguire la migrazione del server Skype for business 2015 esistente a Skype for Business Server 2019, ma rimanere in Exchange 2013 o Exchange 2016.

Quando Skype for Business Server 2015 e Skype for Business Server 2019 coesistono nella stessa organizzazione, funzionano perfettamente con la messaggistica unificata di Exchange e il cloud Voicemail per assicurarsi che la segreteria telefonica venga recapitata correttamente alle cassette postali di Exchange. Se i processi di messaggistica unificata di Exchange o cloud Voicemail il messaggio vocale dipende dal fatto che l'utente si trovi in Skype for Business Server 2015 o Skype for Business Server 2019:

- Se un utente si trova in Skype for Business Server 2015, la messaggistica unificata di Exchange elaborerà il messaggio della segreteria telefonica.
- Se un utente si trova in Skype for Business Server 2019, il messaggio della segreteria telefonica verrà elaborato da cloud Voicemail.

Indipendentemente dal fatto che Exchange UM o cloud Voicemail processi il messaggio della segreteria telefonica, il messaggio verrà archiviato nella cassetta postale di Exchange dell'utente.

Prima di iniziare la migrazione a Skype for Business Server 2019, tieni presente quanto segue:

- Cloud Voicemail non supporta l'operatore automatico dell'organizzazione in GA. Se si vuole che le cassette postali spostate nel cloud Voicemail continuino a essere disponibili tramite operatore automatico, è necessario mantenere almeno un server Exchange 2013 o Exchange 2016 che esegua il ruolo o il servizio di messaggistica unificata disponibile.
- Le chiamate inviate alla segreteria telefonica verranno trasferite alla segreteria telefonica cloud in cui verranno registrate. Una volta terminata la chiamata, il messaggio della segreteria telefonica verrà inviato alla cassetta postale del destinatario nel server Exchange locale. È necessario prendere in considerazione questo traffico vocale per determinare se la connettività Internet è sufficiente per supportare la segreteria telefonica cloud.

Ecco i passaggi di alto livello per completare la migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione di distribuzione ibrida per includere il nuovo server Skype for business 2019.
3. Trasferire gli utenti dal server Skype for business 2015 al server Skype for business 2019.
4. Impostare i criteri di segreteria telefonica ospitata per ogni utente spostati in Skype for Business Server 2019 per usare la segreteria telefonica cloud.
5. Rimuovere i server di Skype for business 2015 dopo che l'ultimo utente è stato spostato.

    > [!IMPORTANT]
    > Se si basa su un operatore automatico, è possibile conservare almeno un Exchange 2013 o Exchange 2016 in uso e disponibile.
