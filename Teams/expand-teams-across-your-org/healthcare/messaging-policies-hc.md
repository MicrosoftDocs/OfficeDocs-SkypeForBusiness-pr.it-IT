---
title: Messaggistica sicura per le organizzazioni sanitarie con Microsoft Teams
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
description: Informazioni su come personalizzare un criterio di messaggistica sicura per Microsoft Teams che può includere conferme di lettura e notifiche di priorità.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790628"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Messaggistica sicura per le organizzazioni sanitarie

I criteri di messaggistica vengono usati per controllare quali funzionalità di messaggistica di chat e canali sono disponibili per gli utenti in Microsoft Teams e fanno parte della distribuzione globale della messaggistica sicura per organizzazioni sanitarie come ospedaliere, cliniche o medici, in cui la risposta e l'intervento di un messaggio in modo appropriato è fondamentale, come sapere quando vengono letti i messaggi cruciali.

È possibile usare i criteri globali (impostazione predefinita a livello di organizzazione) o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Dopo aver creato criteri personalizzati, assegnarli a uno o più gruppi di utenti dell'organizzazione. Ad esempio, è possibile scegliere di consentire solo a determinati ruoli di lavoro di usare queste caratteristiche (ad esempio solo medici e infermieri) e altri lavoratori (come il personale di scuola o cucina) per ottenere un set di caratteristiche più limitato. Per decidere di cosa ha bisogno l'organizzazione, al massimo le indicazioni fornite sono un suggerimento.

I criteri possono essere facilmente gestiti nell'interfaccia di amministrazione di [Microsoft Teams](https://admin.teams.microsoft.com) accedendo con credenziali di amministratore e scegliendo Criteri di **messaggistica** nel riquadro di spostamento sinistro.

 ![Screenshot della pagina Criteri di messaggistica](../../media/hc-messaging-policy-admin-center.png)

Per modificare i criteri di messaggistica predefiniti esistenti per l'organizzazione, fare clic su Globale (impostazione predefinita a livello di **organizzazione)** e quindi apportare le modifiche desiderate. Per creare un nuovo criterio di messaggistica personalizzato, fare clic **su Aggiungi** e quindi selezionare le impostazioni. Al **termine,** scegliere Salva.

![Screenshot delle impostazioni dei criteri di messaggistica](../../media/hc-messaging-policy.png)

Le impostazioni seguenti sono di particolare interesse per le applicazioni sanitarie e devono essere considerate quando si progettano criteri personalizzati usati nel campo Sanitario:

## <a name="read-receipts"></a>Conferme di lettura

Le conferme di lettura consentono al mittente di un messaggio di chat di sapere quando il messaggio è stato letto dal destinatario in 1:1 e le chat di gruppo 20 persone o meno. Usare questa impostazione per specificare se le conferme di lettura sono controllate dall'utente, attivate per tutti o disattivate per tutti. Le conferme di lettura dei messaggi sono importanti nelle organizzazioni sanitarie perché determinano in modo incerto se un messaggio è stato letto.

Per le applicazioni sanitarie, scegliere **Utente controllato** o Sì **per tutti.** Tenere presente che  quando si usa l'impostazione Attivata per tutti gli utenti, l'unico modo per impostare le ricevute per l'intero tenant è impostare un solo criterio di messaggistica per l'intero tenant (il criterio predefinito denominato "Globale (impostazione predefinita a livello di organizzazione)") o fare in modo che tutti i criteri di messaggistica nel tenant usino le stesse impostazioni per le ricevute. La funzionalità conferme di lettura è più efficace se è abilitata per **tutti gli utenti.**

*Esempio di utilizzo senza conferme di lettura:* Jakob Roth, un paziente ad alto rischio, è ammesso all'ospedale.  Sofia Krause è un'infermiera che lavora nell'ambito del team inter-disciplinare (IDT) di personale medico, inclusi diversi specialisti, è assegnata come coordinatore dell'assistenza primaria responsabile del paziente.  Sofia invia messaggi di posta elettronica e altri messaggi istantanei a un gruppo di infermieri e medici che usano diverse app e client di messaggistica e spesso non riceve alcuna risposta o indica se un messaggio è stato letto dai membri del team. A causa dei processi di comunicazione affollati, i farmaci di Jakob non sono stati riapplicati e il suo ricovero in ospedale è stato prolungato.

*Esempio di utilizzo con conferme di lettura:* Jakob Roth, un paziente ad alto rischio, è ammesso all'ospedale.  Sofia Krause è un'infermiera che lavora nell'ambito del team inter-disciplinare (IDT) di personale medico, inclusi diversi specialisti, è assegnata come coordinatore dell'assistenza primaria responsabile del paziente.  Sofia avvia una chat di gruppo con un gruppo di medici e altre infermiere che collaborano con il paziente per coordinare le cure e avviare una triage di emergenza.  Le infermiere e i medici comunicano e collaborano sul piano di assistenza del paziente durante tutto il processo di coordinamento delle cure.  I messaggi importanti e urgenti vengono inviati attraverso le conversazioni 1:1 e di chat di gruppo. Sofia usa la funzionalità delle conferme di lettura per determinare se i messaggi inviati per richiedere supporto vengono recapitati e letti dai medici o dagli infermieri mirati. I risultati dei pazienti di Jakob sono quasi ottimali e torna a casa prima perché il team sanitario comunica senza problemi.

## <a name="send-urgent-messages-using-priority-notifications"></a>Inviare messaggi urgenti usando le notifiche di priorità

Un utente può contrassegnare un messaggio come *urgente quando* invia messaggi di chat ad altri utenti. Questa funzionalità consente al personale ospedaliero di avvisarsi gli uni gli altri quando un incidente critico richiede la loro attenzione. A  differenza dei normali messaggi [importanti,](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) le notifiche di priorità informano gli utenti ogni due minuti per un massimo di 20 minuti o finché il messaggio non viene ritirato e letto dal destinatario, massimizzando la probabilità che il messaggio sia inviato in modo efficace.

Un amministratore può abilitare o disabilitare la possibilità per gli utenti a cui è assegnato questo criterio di inviare notifiche di priorità. Questa funzionalità è attivata per impostazione predefinita. Il destinatario del messaggio con priorità potrebbe non avere lo stesso criterio di messaggistica e non avrà un'opzione per disabilitare la ricezione dei messaggi con priorità. Per le applicazioni sanitarie, è consigliabile abilitare la funzionalità per almeno alcuni utenti, ma è necessario determinare quali.

*Esempio di utilizzo:* Sofia Krause sta lettando un paziente ad alto rischio, Jakob Roth. Caroa Carstens, medico, è il medico di assistenza primaria per questo paziente.  Sofia invia un messaggio a Sofia usando una notifica di priorità che chiede assistenza immediata per la triage di Jakob.  Il telefono di Martina riceve il messaggio, ma Non sente la sensazione di vibrazione del telefono e non risponde. Teams riceve nuovamente la notifica a Martina e continuerà a inviare nuovamente la notifica finché non legge il messaggio. Se sono abilitate anche le conferme di lettura, Sofia è consapevole del fatto che il messaggio è stato letto daOndaa, anche prima che questa decida come rispondere.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di messaggistica in Teams](../../messaging-policies-in-teams.md)
- [Guida introduttiva a Teams per le organizzazioni del settore sanitario](teams-in-hc.md)
