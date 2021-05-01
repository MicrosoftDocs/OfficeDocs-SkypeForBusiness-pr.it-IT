---
title: Messaggistica protetta per le organizzazioni del settore sanitario che usano Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Informazioni su come personalizzare i criteri di messaggistica protetta per Microsoft Teams che possono includere conferme di lettura e notifiche di priorità.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790628"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Messaggistica protetta per le organizzazioni del settore sanitario

I criteri di messaggistica vengono usati per controllare quali caratteristiche di chat e messaggistica dei canali sono disponibili per gli utenti in Microsoft Teams e fanno parte della distribuzione globale di messaggistica protetta per organizzazioni del settore sanitario come ospedali, cliniche o studi medici, in cui è fondamentale che un messaggio sia prelevato ed analizzato immediatamente, in quanto è fondamentale sapere quando vengono letti i messaggi cruciali.

È possibile usare il criterio globale(predefinito a livello di organizzazione) o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Dopo aver creato un criterio personalizzato, assegnarlo a un utente o a un gruppo di utenti dell'organizzazione. Ad esempio, si può scegliere di consentire solo a determinati ruoli di usare queste caratteristiche (forse solo medici e infermieri) e altri lavoratori (ad esempio il personale delle imprese di pulizia o di cucina) per ottenere un set più limitato di caratteristiche. Decidere quali sono le esigenze dell'organizzazione. Le indicazioni riportate di seguito sono solo un suggerimento.

I criteri possono essere gestiti facilmente [nell'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com) accedendo con credenziali di amministratore e scegliendo **Criteri di messaggistica** nel riquadro di spostamento sinistro.

 ![Screenshot della pagina Criteri di messaggistica](../../media/hc-messaging-policy-admin-center.png)

Per modificare i criteri di messaggistica predefiniti esistenti per l'organizzazione, fare clic su **Globale (impostazione predefinita a livello di organizzazione)** e quindi apportare le modifiche desiderate. Per creare nuovi criteri di messaggistica personalizzati, fare clic su **Aggiungi** e quindi selezionare le impostazioni. Al termine, scegliere **Salva**.

![Screenshot Impostazioni dei criteri di messaggistica](../../media/hc-messaging-policy.png)

Le impostazioni seguenti sono di particolare interesse per le applicazioni dell'assistenza sanitaria e devono essere considerate quando si progettano criteri personalizzati usati nel campo dell’assistenza sanitaria:

## <a name="read-receipts"></a>Conferme di lettura

Le conferme di lettura consentono al mittente di un messaggio di chat di sapere quando il messaggio è stato letto dal destinatario in 1:1 e le chat di gruppo comprendenti fino a 20 persone. Usare questa impostazione per specificare se le conferme di lettura devono essere controllate dall'utente, attivate per tutti gli utenti o disattivate per tutti gli utenti. Le conferme di lettura dei messaggi sono importanti nelle organizzazioni del settore dell'assistenza sanitaria perché consentono di sapere con la massima sicurezza se un messaggio è stato letto oppure no.

Per le applicazioni dell'assistenza sanitaria, scegliere **Controllate dall’utente** o **Abilitate per tutti**. Tenere presente che, quando si usa l'impostazione **Abilitate per tutti i**, l'unico modo per impostare le conferme per l'intero tenant è impostare un solo criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "Globale (impostazione predefinita a livello di organizzazione)") o fare in modo che tutti i criteri di messaggistica nel tenant usino le stesse impostazioni per le ricevute. La caratteristica conferme di lettura è più efficace se è **abilitata per tutti**.

*Esempio di utilizzo senza conferme di lettura:* Giorgio Righi, un paziente ad alto rischio, viene ricoverato in ospedale.  A Sofia Verdi, un'infermiera che lavora nel team interdisciplinare (IDT) di operatori sanitari, tra cui diversi specialisti, è assegnata la responsabilità di questo paziente in qualità di coordinatore sanitario.  Sofia invia messaggi di posta elettronica e altri messaggi istantanei a gruppi di infermieri e medici che usano diversi client e app di messaggistica e spesso non riceve alcuna risposta o indicazione se un messaggio è stato letto dai membri del team. A causa di problemi nei processi di comunicazione, i farmaci di Giorgio non vengono somministrati correttamente e la sua degenza viene prolungata.

*Esempio di utilizzo con conferme di lettura:* Giorgio Righi, un paziente ad alto rischio, viene ricoverato in ospedale.  A Sofia Verdi, un'infermiera che lavora nel team interdisciplinare (IDT) di operatori sanitari, tra cui diversi specialisti, è assegnata la responsabilità di questo paziente in qualità di coordinatore sanitario.  Sofia avvia una chat di gruppo con un gruppo di medici e altri infermieri che si occupano del paziente per coordinare le attività di assistenza e avviare una valutazione di emergenza.  Infermieri e medici comunicano e collaborano al piano di assistenza del paziente durante il processo di coordinamento sanitario.  I messaggi importanti e urgenti vengono inviati tramite l'1:1 e le conversazioni nella chat di gruppo. Sofia usa la funzionalità di conferme di lettura per determinare se i messaggi inviati per richiedere assistenza vengono recapitati e letti da medici o infermieri scelti come destinatari. I risultati del paziente Giorgio sono quasi ottimali ed egli può tornare a casa prima grazie al fatto che il team sanitario responsabile comunica senza problemi.

## <a name="send-urgent-messages-using-priority-notifications"></a>Invio di messaggi urgenti con notifiche priorità

Un utente può contrassegnare un messaggio come *urgente* quando invia messaggi di chat ad altri utenti. Questa caratteristica consente al personale ospedaliero di avvisare l'un l'altro quando un evento critico richiede la loro attenzione. A differenza dei normali *messaggi* importanti, [le notifiche di priorità](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) avvisano gli utenti ogni due minuti per un massimo di 20 minuti o finché il messaggio non viene prelevato e letto dal destinatario, massimizzando la probabilità che il messaggio sia inviato tempestivamente.

Un amministratore può abilitare o disabilitare la possibilità per gli utenti a cui è assegnato questo criterio di inviare notifiche con priorità. Questa funzionalità è attivata per impostazione predefinita. Il destinatario del messaggio con priorità potrebbe non avere lo stesso criterio di messaggistica e non avrà un'opzione per disabilitare la ricezione di messaggi con priorità. Per le applicazioni dell'assistenza sanitaria è consigliabile abilitare la caratteristica almeno per alcuni utenti, ma è necessario determinare quali.

*Esempio di utilizzo:* Sofia Verdi sta ricoverando nuovamente un paziente ad alto rischio, Giorgio Righi. Il medico Martina Pollastri è il medico di assistenza primaria di questo paziente.  Sofia invia un messaggio a Martina usando una notifica di priorità che chiede assistenza immediata per la valutazione di Giorgio.  Il telefono di Martina riceve il messaggio, ma Martina non vi fa caso e non risponde. Teams ri-invia una nuova notifica a Martina e continuerà a inviarla finché Martina non legge il messaggio. Se sono abilitate anche le conferme di lettura, Sofia sa che il messaggio è stato letto da Martina, anche prima che Martina decida come rispondere.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di messaggistica in Teams](../../messaging-policies-in-teams.md)
- [Guida introduttiva a Teams per le organizzazioni del settore sanitario](teams-in-hc.md)
