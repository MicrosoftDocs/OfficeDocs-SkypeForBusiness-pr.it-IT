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
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: Questo argomento illustra gli aspetti da considerare quando si decide di eseguire la migrazione delle distribuzioni di Skype for Business Server o Exchange Server esistenti all'ultima versione o a Skype for Business Online o Exchange Online.
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486991"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Pianificare la migrazione per Skype for Business Server ed Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Questo argomento illustra gli aspetti da considerare quando si decide di eseguire la migrazione delle distribuzioni di Skype for Business Server o Exchange Server esistenti in Exchange Online. Ciò di cui è possibile eseguire la migrazione e quando dipende in larga misura da ciò che è già stato configurato nell'organizzazione.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifiche delle funzionalità in Exchange 2019 e Skype for Business Server 2019

Con Exchange 2019 e Skype for Business Server 2019, verranno apportate alcune modifiche alle funzionalità supportate.

### <a name="unified-messaging-support-in-exchange-2019"></a>Supporto della messaggistica unificata in Exchange 2019

La messaggistica unificata è stata deprecata in Exchange 2019. Ciò significa che Exchange 2019 non offre più le funzionalità seguenti:

- Messaggi vocali
- Operatore automatico

Se il ruolo di messaggistica unificata è stato distribuito in Exchange 2013 o nel servizio di messaggistica unificata in Exchange 2016 e si vuole eseguire l'aggiornamento a Exchange 2019, è necessario eseguire la migrazione della segreteria telefonica al servizio Microsoft Cloud Voicemail in Microsoft 365 o Office 365. Se si vuole eseguire la migrazione della segreteria telefonica a Cloud Voicemail, vedere la sezione [Exchange 2013/Exchange 2016 e Skype for Business 2015 a Exchange 2019 e Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) di seguito.
> [!IMPORTANT]
> Se gli utenti nei server Exchange 2013 o Exchange 2016 dispongono di cassette postali abilitate per la messaggistica unificata, non spostarle in Exchange 2019 prima di aggiornare i server Skype for Business a Skype for Business Server 2019 e spostare gli utenti in tali server per evitare un'interruzione della messaggistica vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Supporto PBX in Exchange 2019 e Skype for Business Server 2019

Cloud Voicemail non fornisce funzionalità di messaggistica vocale a Private Branch Exchange (PBX). Se si usa Exchange Server Messaggistica unificata per PBX e si vuole eseguire l'aggiornamento a Exchange Server 2019, è necessario adottare una delle tre opzioni elencate nel post di blog New date for discontinuation of support for Session Border Controllers in Exchange Online Unified Messaging on the Exchange Team Blog.If you're using Exchange Server Unified Messaging for PBXs and you want to upgrade to Exchange Server 2019, you'll need to adopt one the three options listed in the blog post [New date for discontinuation of support for Session Border Controllers in Exchange Online Unified Messaging](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) on the [Exchange Team Blog.If](https://blogs.technet.microsoft.com/exchange/) you're using Exchange Server Unified Messaging for PBXs and you want to upgrade to Exchange Server 2019, you'll need to adopt one of the three options listed in the blog post New date for discontinuation of support for Session Border Controllers in Exchange Online Unified Messaging on the Exchange Team Blog.

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>supporto della messaggistica unificata Exchange Online in Skype for Business Server 2019

Con Skype for Business Server 2019, si passa dalla messaggistica unificata Exchange Online alla Cloud Voicemail. Quando un utente viene spostato in un server Skype for Business 2019, inizierà automaticamente a usare Cloud Voicemail se configurato per la segreteria telefonica ospitata. Se attualmente si usa Exchange Online messaggistica unificata, non è necessario eseguire altre operazioni oltre a spostare un utente in Skype for Business Server 2019 per iniziare a usare Cloud Voicemail. Esistono tuttavia alcune modifiche alla funzionalità di cui è necessario tenere conto:

- L'operatore automatico dell'organizzazione sostituisce l'operatore automatico nella messaggistica unificata Exchange Online.
- Le impostazioni della segreteria telefonica utente in Outlook sul Web non si applicano a Cloud Voicemail.

## <a name="on-premises-um-migration-scenarios"></a>Scenari di migrazione della messaggistica unificata locale

Sono supportabili gli scenari seguenti che consentono di eseguire la migrazione degli utenti sia a Exchange 2019 che a Cloud Voicemail.

- Da Exchange 2013/Exchange 2016 e Skype for Business Server 2015 a Exchange 2019 e Skype for Business Server 2019
- Skype for Business Server 2015 a Skype for Business Server 2019 con Exchange 2013/Exchange 2016

Gli scenari seguenti richiedono che non siano presenti configurazioni PBX o SBC nell'ambito della distribuzione corrente e presuppongono che la messaggistica unificata sia configurata nei server Exchange locali. Ognuna di queste soluzioni presuppone anche che si sia deciso di configurare una distribuzione ibrida tra i server Skype for Business locali e Microsoft 365 o Office 365. Per altre informazioni sulle distribuzioni ibride Skype for Business, vedere [Pianificare la connettività ibrida](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype for Business 2015 a Exchange 2019 e Skype for Business 2019

In questo scenario si vuole eseguire la migrazione dei server Exchange 2013, Exchange 2016 e Skype for Business 2015 esistenti a Exchange 2019 e Skype for Business 2019.

Come accennato in precedenza in questo argomento, Exchange 2019 non include più il servizio di messaggistica unificata. Ciò significa che, per tutte le cassette postali che si desidera spostare in Exchange 2019, è necessario usare Cloud Voicemail per sostituire la funzionalità fornita dal servizio di messaggistica unificata. Quando si configura Skype for Business Server 2019 e una distribuzione ibrida tra questa e Microsoft 365 o Office 365, Cloud Voicemail sostituisce questi servizi di messaggistica unificata di Exchange.

L'ordine in cui si spostano gli utenti in Exchange 2019 e Skype for Business Server 2019 è fondamentale per garantire che la funzionalità della segreteria telefonica rimanga disponibile per tutti gli utenti. La posizione in cui viene elaborata la segreteria telefonica è determinata anche dalla posizione in cui si trovano le cassette postali e gli utenti di Exchange e Skype for Business. Esaminare la tabella seguente per vedere quali combinazioni di Exchange e Skype for Business Server sono supportate e dove viene elaborata la segreteria telefonica.

| Cassetta postale situata in:            | Utente situato in Skype for Business Server 2015 | Utente situato in Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Messaggistica unificata                             | Messaggistica unificata                              |
| Exchange 2019                  | Non supportato                           | Cloud Voicemail                          |

Prima di iniziare la migrazione a Skype for Business Server 2019 ed Exchange 2019, tenere presente quanto segue:

- È necessario configurare almeno un server Skype for Business 2019 **e** spostare gli utenti in tale server prima di spostare le cassette postali in Exchange 2019. Se non si esegue questa operazione, le cassette postali non saranno in grado di ricevere messaggi vocali.
- Le chiamate inviate alla segreteria telefonica verranno trasferite a Cloud Voicemail in cui verranno registrate. Al termine della chiamata, il messaggio della segreteria telefonica verrà inviato alla cassetta postale del destinatario nel server Exchange 2019 locale. È necessario tenere conto di questo traffico vocale quando si determina se la connettività Internet è sufficiente per supportare Cloud Voicemail.

Ecco i passaggi generali per completare questa migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione della distribuzione ibrida per includere il nuovo server Skype for Business 2019.
3. Installare e configurare Exchange Server 2019 in un nuovo server.
4. Spostare gli utenti dal server Skype for Business 2015 al server Skype for Business 2019.
5. Impostare i criteri di segreteria telefonica ospitata per ogni utente spostato in Skype for Business Server 2019 per usare Cloud Voicemail.
6. Spostare le cassette postali dal server Exchange 2013 o Exchange 2016 al server Exchange 2019.
7. Rimuovere le autorizzazioni dai server Skype for Business 2015 dopo che l'ultimo utente è stato spostato.
8. Rimuovere i server Exchange 2013 o Exchange 2016 dopo che l'ultima cassetta postale è stata rimossa.


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 a Skype for Business Server 2019 con Exchange 2013/Exchange 2016

In questo scenario si vuole eseguire la migrazione del server Skype for Business 2015 esistente a Skype for Business Server 2019, ma rimanere in Exchange 2013 o Exchange 2016.

Quando Skype for Business Server 2015 e Skype for Business Server 2019 coesistono nella stessa organizzazione, funzionano senza problemi con la messaggistica unificata di Exchange e Cloud Voicemail per garantire che la segreteria telefonica venga recapitata correttamente alle cassette postali di Exchange. Se la messaggistica unificata di Exchange o Cloud Voicemail elabora la segreteria telefonica dipende dal fatto che l'utente si trovi in Skype for Business Server 2015 o Skype for Business Server 2019:

- Se un utente si trova in Skype for Business Server 2015, la messaggistica unificata di Exchange e processerà il messaggio della segreteria telefonica.
- Se un utente si trova in Skype for Business Server 2019, Cloud Voicemail e processerà il messaggio della segreteria telefonica.

Indipendentemente dal fatto che la messaggistica unificata di Exchange o Cloud Voicemail elabori il messaggio della segreteria telefonica, il messaggio verrà archiviato nella cassetta postale di Exchange dell'utente.

Prima di iniziare la migrazione a Skype for Business Server 2019, tenere presente quanto segue:

- Le chiamate inviate alla segreteria telefonica verranno trasferite a Cloud Voicemail in cui verranno registrate. Al termine della chiamata, il messaggio della segreteria telefonica verrà inviato alla cassetta postale del destinatario nel server Exchange locale. È necessario tenere conto di questo traffico vocale quando si determina se la connettività Internet è sufficiente per supportare Cloud Voicemail.

Ecco i passaggi generali per completare questa migrazione.

1. Installare e configurare Skype for Business Server 2019 in un nuovo server.
2. Aggiornare la configurazione della distribuzione ibrida per includere il nuovo server Skype for Business 2019.
3. Spostare gli utenti dal server Skype for Business 2015 al server Skype for Business 2019.
4. Impostare i criteri di segreteria telefonica ospitata per ogni utente spostato in Skype for Business Server 2019 per usare Cloud Voicemail.
5. Rimuovere le autorizzazioni dai server Skype for Business 2015 dopo che l'ultimo utente è stato spostato.

