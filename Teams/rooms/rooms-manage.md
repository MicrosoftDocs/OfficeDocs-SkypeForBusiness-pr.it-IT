---
title: Gestire Microsoft Teams Rooms.
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Informazioni su come sviluppare ed eseguire operazioni e manutenzione continuativa per garantire che i sistemi Room di Microsoft Teams siano disponibili per gli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 830caffbbb0256e64198e84876a4067337e90266
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848838"
---
# <a name="manage-microsoft-teams-rooms"></a>Gestire Microsoft Teams Rooms.

Se l'organizzazione dispone di dispositivi certificati Microsoft Teams Room, sono disponibili opzioni di gestione flessibili.  È possibile gestire i dispositivi manualmente nella stessa posizione centrale in cui si gestiscono tutte le soluzioni Teams, l'interfaccia di amministrazione di Microsoft Teams oppure è possibile trasferire la responsabilità di gestione a esperti dedicati utilizzando i servizi gestiti di [Microsoft Teams Room.](https://portal.rooms.microsoft.com)  È anche possibile delegare l'accesso alla gestione a un partner di propria scelta per una delle opzioni.

Con l'interfaccia di amministrazione di Microsoft Teams è possibile:

- Eseguire la gestione dei dispositivi, ad esempio il riavvio o il blocco dei dispositivi e il download dei log dei dispositivi
- Applicare le impostazioni specifiche di Teams
- Controllare lo stato di integrità dei dispositivi della sala di Microsoft Teams e delle relative periferiche, tra cui videocamere, schermi, microfoni e così via
- Esaminare l'attività corrente e quella passata della riunione (ad esempio dettagli sulla qualità delle chiamate, l'integrità e la connettività della rete e il numero di partecipanti)
- Vedere le periferiche (ad esempio fotocamere e proiettori) connesse a un dispositivo Microsoft Teams Room

Per gestire i dispositivi di Teams Rooms, aprire l'interfaccia di amministrazione di [Microsoft Teams](https://admin.teams.microsoft.com) e passare a Sale di Teams **per dispositivi.**  >  

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Pagine di riepilogo sale di Teams nell'interfaccia di amministrazione di Teams":::

> [!IMPORTANT]
> Per gestire i dispositivi tramite l'interfaccia di amministrazione di Teams, è necessario disporre dei ruoli di amministratore globale, amministratore del servizio Teams o amministratore dei dispositivi di Teams.

## <a name="make-changes-to-teams-rooms-devices"></a>Modificare i dispositivi di Teams Rooms

Se si dispone di più di un dispositivo Sale di Teams, è possibile eseguire la maggior parte delle azioni su più dispositivi contemporaneamente. Ad esempio, è possibile configurare le impostazioni dell'app Teams in tutti i dispositivi contemporaneamente.

### <a name="device-settings"></a>Impostazioni del dispositivo

È possibile modificare le impostazioni in uno o più dispositivi dell'organizzazione. Per modificare le impostazioni, selezionare il dispositivo o i dispositivi da gestire e quindi **selezionare Modifica impostazioni.** Si aprirà un nuovo riquadro con tutte le impostazioni che è possibile modificare nei dispositivi. La tabella seguente elenca le impostazioni che è possibile modificare usando l'interfaccia di amministrazione di Teams. Alcune impostazioni sono disponibili solo quando si seleziona un singolo dispositivo.

Se si selezionano più dispositivi, le impostazioni che supportano la modifica in blocco visualizzano le due opzioni seguenti.

- **Mantieni valore esistente** Se si sceglie questa opzione, non verranno apportate modifiche all'impostazione nei dispositivi selezionati.
- **Sostituisci il valore esistente con** Se si sceglie questa opzione, è possibile aggiornare l'impostazione nei dispositivi selezionati con il valore specificato.
    > [!CAUTION]
    > I valori esistenti nelle impostazioni che si sceglie di aggiornare verranno sostituiti con il valore specificato. Se si vuole aggiungere un valore a un elenco di valori esistenti, è necessario includere i valori esistenti con il valore da aggiungere. Ad esempio, se un'impostazione ha già un elenco di domini e si vuole aggiungerlo, il valore da specificare `contoso.com, fabrikam.com` `northwindtraders.com` sarà `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Se si selezionano più dispositivi, l'impostazione in tutti i dispositivi selezionati verrà impostata sul valore specificato. Se i dispositivi hanno valori diversi per un'impostazione, verranno tutti aggiornati allo stesso valore.

| Impostazione                                                      | Valori accettati                                        | Supporta la modifica in blocco |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Account*                                                    |                                                        |                    |
| **Posta elettronica**                                                    | Indirizzo e-mail                                          | No                 |
| **Modalità riunione supportata**                                   | Skype for Business (impostazione predefinita) e Microsoft Teams<br>Skype for Business e Microsoft Teams (impostazione predefinita)<br>Solo Skype for Business|Sì|
| **Autenticazione moderna**                                    | Attivato<br>Disattivato                                              | Sì                |
| **Indirizzo di Exchange**                                         | Indirizzo e-mail                                          | No                 |
| **Dominio#D0 omeutente (facoltativo)**                               | Dominio dell'account e nome utente                           | No                 |
| **Configurare il dominio**                                         | Elenco con valori delimitati da virgole                                   | Sì                |
| *Riunioni*                                                   |                                                        |                    |
| **Condivisione automatica dello schermo**                                 | Attivato<br>Disattivato                                              | Sì                |
| **Visualizzare i nomi delle riunioni**                                       | Attivato<br>Disattivato                                              | Sì                |
| **Lascia automaticamente se tutti gli altri hanno lasciato la riunione**                 | Attivato<br>Disattivato                                              | Sì                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modalità a doppio monitor**                                        | Attivato<br>Disattivato                                              | Sì                |
| **Bluetooth beaconing**                                      | Attivato<br>Disattivato                                              | Sì                |
| **Accettare automaticamente inviti alle riunioni basati sulla prossimità** | Selezionato<br>Non selezionato                                 | Sì                |
| **Inviare log con commenti e suggerimenti**                                  | Attivato<br>Disattivato                                              | Sì                |
| **Indirizzo di posta elettronica per i log e il feedback**                      | Indirizzo e-mail                                          | Sì                |
| *Periferiche*                                                |                                                        |                    |
| **Microfono di conferenza**                                  | Elenco dei microfoni disponibili                          | No                 |
| **Altoparlante conferenza**                                     | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Altoparlante predefinito**                                          | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Fotocamera del contenuto**                                           | Elenco delle fotocamere disponibili                              | No                 |
| **Miglioramenti apportati alla fotocamera del contenuto**                              | Attivato<br>Disattivato                                              | No                 |
| **Ruotare di 180 gradi la fotocamera del contenuto**                        | Attivato<br>Disattivato                                              | No                 |
| *Personalizzazione dei dati*                                                    |                                                        |                    |
|                                                              | Impostazione predefinita<br>Nessun tema<br>Personalizzato<br>Elenco dei temi predefiniti   | Sì                |

### <a name="device-restart-options"></a>Opzioni di riavvio del dispositivo

Le modifiche alle impostazioni del dispositivo verranno applicate solo dopo il riavvio dei dispositivi. Quando si apportano modifiche che devono essere riavviate, è possibile scegliere se riavviare immediatamente i dispositivi o pianificare un riavvio. Ecco le opzioni di riavvio disponibili:

- **Riavvio immediato** Se si sceglie questa opzione, tutti i dispositivi a cui si stanno apportando modifiche verranno riavviati non appena si seleziona questa opzione.
- **Riavvio pianificato** Se si sceglie questa opzione, è possibile riavviare i dispositivi a cui si stanno apportando modifiche in un momento meno disturbare per l'organizzazione.
  - **Selezionare data e ora:** scegliere la data e l'ora specifiche per riavviare il dispositivo. La data e l'ora selezionate sono locali per il dispositivo da riavviare. 
  - **Lascia l'aggiornamento per il riavvio sereno** I dispositivi vengono riavviati ogni notte per eseguire operazioni di manutenzione. Le modifiche apportate ai dispositivi verranno applicate durante il riavvio.

> [!CAUTION]
> I dispositivi in uso al momento di un riavvio diventeranno non disponibili per la durata del processo di riavvio. Saranno disconnessi dalle riunioni in corso e non saranno disponibili per partecipare a nuove riunioni.

### <a name="remove-or-block-a-device"></a>Rimuovere o bloccare un dispositivo

Quando si **rimuove** un dispositivo, il dispositivo viene rimosso dall'organizzazione e non viene più visualizzato nell'elenco di dispositivi Sale di Teams nell'interfaccia di amministrazione di Teams. 

Quando si **blocca** un dispositivo, Teams non comunica più con il dispositivo. I dispositivi bloccati non verranno inviati comandi, anche se sono inclusi in un gruppo di dispositivi che vengono modificati in blocco. È ancora elencato nell'elenco dei dispositivi di Teams Room con lo stato **Bloccato.**

Indipendentemente dal fatto che un dispositivo sia bloccato o rimosso, se è ancora configurato con un nome utente e una password validi, verrà automaticamente aggiunto di nuovo all'elenco di dispositivi Sale di Teams se si connette a Microsoft 365.

Per rimuovere uno o più dispositivi, eseguire le operazioni seguenti:

1. Passare a **Sale di**  >  **Teams per** dispositivi e selezionare i dispositivi da rimuovere.
1. Selezionare **Rimuovi.**

Per bloccare un dispositivo, eseguire le operazioni seguenti:

1. Passare a **Sale**  >  **di Teams** per dispositivi e selezionare il nome del dispositivo da bloccare.
1. Nella pagina dei dettagli del dispositivo selezionare **Azioni** nell'angolo in alto a destra della pagina.
1. Selezionare **Blocca.**

Per sbloccare un dispositivo, eseguire le operazioni seguenti:

1. Passare a **Sale**  >  **di Teams** per dispositivi e selezionare il nome del dispositivo da bloccare.
1. Nella pagina dei dettagli del dispositivo selezionare **Azioni** nell'angolo in alto a destra della pagina.
1. Selezionare **Sblocca.**

## <a name="download-device-logs"></a>Scaricare i log dei dispositivi

Se richiesto dal supporto Microsoft, è possibile scaricare una copia dei file di log diagnostici di un dispositivo. I file di log vengono compressi in un file ZIP che può essere scaricato dall'interfaccia di amministrazione di Teams.

Per scaricare i log da un dispositivo Teams Rooms nel computer, eseguire le operazioni seguenti:

1. Passare a **Sale di** Teams per dispositivi e selezionare il nome del dispositivo da cui scaricare i  >   log.
1. Selezionare **Scarica registri dispositivi.** La disponibilità dei log dei dispositivi può richiedere alcuni minuti.
1. Selezionare la **scheda Cronologia** e quindi selezionare il collegamento al file di log in File **di diagnostica.** Nella cartella download predefinita del browser verrà scaricato un file ZIP contenente i file di log diagnostici del dispositivo.

## <a name="view-device-information"></a>Visualizzare le informazioni sul dispositivo

Dall'interfaccia di amministrazione di Teams è possibile visualizzare lo stato generale di tutti i dispositivi dell'organizzazione e visualizzare i dettagli di ogni dispositivo singolarmente.

### <a name="teams-rooms-system-dashboard"></a>Dashboard di sistema sale di Teams

Il dashboard di sistema Sale di Teams mostra lo stato e l'integrità di tutti i dispositivi a colpo d'occhio.

### <a name="device-details-view"></a>Visualizzazione dettagli dispositivo

Per visualizzare informazioni dettagliate su un dispositivo, selezionarne il nome nell'elenco di dispositivi. Nella visualizzazione dettagli sono disponibili le informazioni seguenti sul dispositivo:

- **Stato integrità** Mostra l'integrità generale del dispositivo Sala teams. Lo stato di integrità può essere **Integro** **o Non integro.**
- **Offline da** Mostra l'ultima volta in cui Microsoft 365 è riuscito a comunicare con il dispositivo.
- **Stato del dispositivo** Mostra lo stato corrente del dispositivo: **Inattivo,** **Riunione Teams,** **Riunione Skype** o **Ingest.**
- **Periferiche** Mostra le periferiche connesse al tuo dispositivo Teams Room e il loro stato di integrità. Lo stato di integrità può essere **Connesso** **o Disconnesso.**
- **Integrità** Mostra informazioni dettagliate sulle periferiche connesse al dispositivo Teams Room, sulla connettività di rete, sullo stato di accesso ai servizi necessari e sulle informazioni sulla versione del software.
- **Dettagli** Mostra le informazioni sul produttore, l'indirizzo IP di rete e l'indirizzo MAC del dispositivo Room di Teams.
- **Attività** Mostra i dettagli passati della riunione, tra cui la data e l'ora della riunione, il numero di partecipanti, la durata e la qualità audio. Per altre informazioni sui dettagli della riunione, vedere la [sezione Dettagli attività](#meeting-activity-details) riunione più avanti in questo articolo.
- **Cronologia** Mostra una cronologia delle attività di gestione nel dispositivo Teams Room, inclusi gli aggiornamenti di configurazione, i riavvii del dispositivo e i collegamenti per il download del log dei dispositivi.

#### <a name="meeting-activity-details"></a>Dettagli dell'attività della riunione

La **scheda** Attività nei dettagli dei dispositivi della sala di Teams mostra informazioni di alto livello e dettagliate su tutte le riunioni a cui il dispositivo ha partecipato nel corso del tempo. Nella scheda **Attività** è possibile vedere quando è stata tenuta una riunione, quanti partecipanti hanno partecipato alla riunione e la qualità dell'audio durante la riunione.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Elenco di riepilogo dell'attività dei dispositivi in sala teams":::

Per visualizzare le informazioni dettagliate su una riunione specifica, selezionare la data e l'ora della riunione di cui si vogliono ottenere altre informazioni. Se una riunione ha solo due partecipanti, verrà visualizzata la pagina dei dettagli del partecipante, altrimenti verrà visualizzata una pagina di riepilogo dei partecipanti.

##### <a name="participant-summary"></a>Riepilogo partecipanti

La pagina di riepilogo dei partecipanti mostra tutti i partecipanti che hanno partecipato alla riunione. È possibile vedere quando ogni partecipante ha partecipato alla riunione, il suo nome, la qualità audio e quali funzionalità sono state usate durante la sessione. Per visualizzare i dettagli della sessione di un partecipante, selezionare l'ora di inizio della sessione per tale partecipante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Dettagli conferenza sul dispositivo Teams Room":::

##### <a name="participant-details"></a>Dettagli partecipante

La pagina dei dettagli del partecipante mostra informazioni di diagnostica end-to-end per la sessione del partecipante. Come illustrato nella figura seguente, le  informazioni su **dispositivo,** sistema e connettività vengono fornite per il partecipante e per il dispositivo Sale di Teams.  **Vengono fornite** anche informazioni di diagnostica di rete tra il partecipante e il dispositivo Teams Rooms. Selezionare l'icona per il contesto di cui si vogliono ottenere altre informazioni. Per altre informazioni diagnostiche, selezionare **la scheda** Avanzate.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Dettagli delle chiamate sul dispositivo Teams Room":::
