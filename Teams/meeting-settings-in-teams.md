---
title: Gestire le impostazioni delle riunioni
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: Informazioni su come gestire le impostazioni per le riunioni di team che gli utenti pianificano nell'organizzazione.
ms.openlocfilehash: 6d5e4d4235eceda3821a34a039625730d11d9fff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707301"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gestire le impostazioni delle riunioni in Microsoft Teams

Come amministratore, puoi usare le impostazioni riunioni teams per controllare se gli utenti anonimi possono partecipare a riunioni di Team, personalizzare gli inviti alle riunioni e se vuoi abilitare la qualità del servizio (QoS), impostare gli intervalli di porta per il traffico in tempo reale. Queste impostazioni si applicano a tutte le riunioni di team che gli utenti pianificano nell'organizzazione. Queste impostazioni vengono gestite dalle **** > **impostazioni delle** riunioni delle riunioni nell'interfaccia di amministrazione di Microsoft teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Consentire agli utenti anonimi di partecipare alle riunioni

Con l'aggiunta anonima, chiunque può partecipare alla riunione come utente anonimo facendo clic sul collegamento nell'invito alla riunione. Per altre informazioni, vedere [partecipare a una riunione senza un account teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).


![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra, vai a**Impostazioni riunione** **riunioni** > .
2. In **partecipanti**, attivare **gli utenti anonimi possono partecipare a una riunione**.

    ![Screenshot delle impostazioni dei partecipanti per le riunioni nell'interfaccia di amministrazione](media/meeting-settings-participants.png "Screenshot delle impostazioni dei partecipanti per le riunioni di team nell'interfaccia di amministrazione di Microsoft Teams")

Se non si vuole che gli utenti anonimi partecipino alle riunioni pianificate dagli utenti dell'organizzazione, disattivare questa impostazione.

## <a name="customize-meeting-invitations"></a>Personalizzare gli inviti alle riunioni

È possibile personalizzare gli inviti alle riunioni dei team per soddisfare le esigenze dell'organizzazione. È possibile aggiungere il logo dell'organizzazione e includere informazioni utili, ad esempio collegamenti al sito Web del supporto tecnico e Disclaimer legale, e un piè di pagina di solo testo.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Suggerimenti per la creazione di un logo per gli inviti alle riunioni  

1. Creare un'immagine che non supera i 188 pixel di larghezza per 30 pixel di altezza (è abbastanza piccola).
2. Salvare l'immagine in formato JPG o PNG.
3. Archiviare l'immagine in una posizione a cui possono accedere tutti gli utenti che ricevono l'invito, ad esempio un sito Web pubblico.

    A questo punto è possibile aggiungerlo agli inviti alle riunioni. Vedere i passaggi successivi.

### <a name="customize-your-meeting-invitations"></a>Personalizzare gli inviti alle riunioni

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra, vai a**Impostazioni riunione** **riunioni** > .
2. In **invito tramite posta elettronica**eseguire le operazioni seguenti:

    ![Screenshot delle impostazioni dell'invito alla riunione che è possibile personalizzare](media/meeting-settings-invitation.png "Screenshot delle impostazioni dell'invito alla riunione che è possibile personalizzare per le riunioni di Teams")

    - **URL del logo** Immettere l'URL in cui è archiviato il logo.
    - **URL legale** Se l'organizzazione ha un sito Web legale in cui si vuole che gli utenti possano rivolgersi per eventuali problemi legali, immettere l'URL qui.
    - **URL della Guida** Se l'organizzazione dispone di un sito Web di supporto a cui si vuole che gli utenti possano accedere in caso di problemi, immettere l'URL qui.
    - **Piè** di pagina Immettere il testo che si vuole includere come piè di pagina.
3. Attendere un'ora o giù di lì per la propagazione delle modifiche. Pianificare quindi una riunione di teams per vedere l'aspetto dell'invito alla riunione.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Impostare il modo in cui si vuole gestire il traffico multimediale in tempo reale per le riunioni di Teams

<a name="bknetwork"> </a>

Se si usa la qualità del servizio [(QoS)](qos-in-teams.md) per definire la priorità del traffico di rete, è possibile abilitare gli indicatori QoS e impostare gli intervalli di porta per ogni tipo di traffico multimediale. L'impostazione di intervalli di porte per tipi di traffico diversi è un solo passaggio nella gestione di elementi multimediali in tempo reale. vedere la [qualità del servizio (QoS) in teams](qos-in-teams.md) per un maggior dettaglio.

> [!IMPORTANT]
> Se si Abilita la QoS o si modificano le impostazioni nell'interfaccia di amministrazione di Microsoft teams per il servizio Microsoft teams, sarà necessario [applicare anche le impostazioni di corrispondenza a tutti i dispositivi utente](QoS-in-Teams-clients.md) e a tutti i dispositivi di rete interni per implementare completamente le modifiche apportate al QoS in teams.

 ![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra, vai a**Impostazioni riunione** **riunioni** > .
2. In **rete**eseguire le operazioni seguenti:

    ![Screenshot delle impostazioni di rete per le riunioni nell'interfaccia di amministrazione](media/meeting-settings-network.png "Screenshot delle impostazioni di rete per le riunioni di team nell'interfaccia di amministrazione di Microsoft Teams")

    - Per consentire l'uso dei contrassegni di DSCP per QoS, attivare l'opzione **Inserisci indicatori di qualità del servizio (QoS) per il traffico multimediale in tempo reale**. Hai solo l'opzione di usare i marcatori o meno; non è possibile impostare indicatori personalizzati per ogni tipo di traffico. Per altre informazioni sugli indicatori DSCP, vedere [selezionare un metodo di implementazione QoS](QoS-in-Teams.md#select-a-qos-implementation-method) .
    > [!NOTE] 
    > L'attivazione degli **indicatori di qualità del servizio (QoS) per il traffico multimediale in tempo reale** consentirà anche di comunicare con il relay di trasporto con le porte UDP 3479 (audio), 3480 (video) e 3481 (condivisione).
    - Per specificare gli intervalli di porte, accanto a **selezionare un intervallo di porte per ogni tipo di traffico multimediale in tempo reale**, selezionare **Specifica intervalli di porte**e quindi immettere le porte di inizio e fine per la condivisione di audio, video e dello schermo. Per implementare QoS è necessario selezionare questa opzione.
    > [!IMPORTANT]
    > Se si seleziona **Usa automaticamente le porte disponibili**, vengono usate le porte disponibili tra 1024 e 65535. Usare questa opzione solo quando non si implementa QoS.
    >
    > La selezione di un intervallo di porte troppo stretto consentirà di ricevere chiamate cadute e una qualità di chiamata scadente. Le raccomandazioni riportate di seguito devono essere minime.

Se non si è certi degli intervalli di porte da usare nell'ambiente, le impostazioni seguenti rappresentano un buon punto di partenza. Per altre informazioni, vedere [implementare la qualità del servizio (QoS) in Microsoft teams](QoS-in-Teams.md). Questi sono i contrassegni di DSCP necessari e gli intervalli di porte multimediali suggeriti usati da teams e ExpressRoute.

_Intervalli di porte e contrassegni DSCP_

Tipo di traffico multimediale| Intervallo di porte di origine client\* |Protocollo|Valore DSCP|Classe DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50000-50019               |TCP/UDP |46        |Inoltro accelerato (EF)|
|Video            | 50020-50039               |TCP/UDP |34        |Inoltro assicurato (AF41)|
|Condivisione di applicazioni/schermi| 50040-50059      |TCP/UDP |18        |Inoltro assicurato (AF21)|
| | | | |

\*Gli intervalli di porte assegnati non possono essere sovrapposti e devono essere adiacenti.

Dopo che il QoS è stato usato per un po' di tempo, si avranno informazioni sull'utilizzo della domanda per ognuno di questi tre carichi di lavoro e si potranno scegliere le modifiche da apportare in base alle proprie esigenze. Il [dashboard qualità chiamata](turning-on-and-using-call-quality-dashboard.md) sarà utile.
