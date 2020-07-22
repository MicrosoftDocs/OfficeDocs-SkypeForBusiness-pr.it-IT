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
description: Informazioni su come sviluppare ed eseguire la manutenzione e le operazioni in corso per verificare che i sistemi Microsoft teams Rooms siano disponibili per gli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2339967d6d7705266c13dbc65fb689c49c8e8279
ms.sourcegitcommit: a5276a713697e089d0eb0d80bba83a7af8d48251
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45202922"
---
# <a name="manage-microsoft-teams-rooms"></a>Gestire Microsoft Teams Rooms.

Se nella propria organizzazione sono presenti dispositivi certificati Microsoft teams rooms, è possibile gestirli da una posizione centrale tramite l'interfaccia di amministrazione di Microsoft teams. Si può:

- Eseguire la gestione di dispositivi come riavviare o bloccare i dispositivi e scaricare i log dei dispositivi
- Applicare impostazioni specifiche per i team
- Verificare lo stato di integrità dei dispositivi della sala Microsoft teams e delle relative periferiche, tra cui videocamere, schermi, microfoni e così via
- Rivedere le attività di riunione correnti e passate, ad esempio informazioni dettagliate sulla qualità delle chiamate, l'integrità della rete e la connettività e il numero di partecipanti
- Vedere periferiche (ad esempio videocamere e proiettori) connesse a un dispositivo della sala Microsoft Teams

Per gestire i dispositivi delle sale di teams, aprire l'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com) e andare a **dispositivi**  >  **Teams Rooms**.

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Pagine di riepilogo di teams rooms nell'interfaccia di amministrazione di Teams":::

> [!IMPORTANT]
> Per gestire i dispositivi con l'interfaccia di amministrazione di teams, è necessario assegnare l'amministratore del servizio Team o i ruoli di amministratore globale.

## <a name="make-changes-to-teams-rooms-devices"></a>Apportare modifiche ai dispositivi di teams rooms

Se si ha più di un dispositivo di teams rooms, è possibile eseguire la maggior parte delle azioni su più dispositivi contemporaneamente. Ad esempio, puoi impostare le impostazioni dell'app teams su tutti i tuoi dispositivi contemporaneamente.

### <a name="device-settings"></a>Impostazioni del dispositivo

È possibile modificare le impostazioni in uno o più dispositivi dell'organizzazione. Per modificare le impostazioni, selezionare il dispositivo o i dispositivi da gestire e quindi selezionare **Modifica impostazioni**. Verrà aperto un nuovo riquadro con tutte le impostazioni che è possibile modificare nei dispositivi. La tabella seguente elenca le impostazioni che è possibile modificare con l'interfaccia di amministrazione di teams. Alcune impostazioni sono disponibili solo quando si seleziona un singolo dispositivo.

Se si selezionano più dispositivi, le impostazioni che supportano la modifica in blocco mostrano le due opzioni seguenti.

- **Mantieni il valore esistente** Se si sceglie questa opzione, non verrà apportata alcuna modifica all'impostazione dei dispositivi selezionati.
- **Sostituire il valore esistente con** Se si sceglie questa opzione, è possibile aggiornare l'impostazione nei dispositivi selezionati con il valore fornito.
    > [!CAUTION]
    > I valori esistenti nelle impostazioni che scegli di aggiornare verranno sostituiti con il valore che fornisci. Se si vuole aggiungere un elenco di valori esistenti, è necessario includere i valori esistenti con il valore che si vuole aggiungere. Ad esempio, se un'impostazione contiene un elenco di domini esistente `contoso.com, fabrikam.com` e si vuole aggiungere `northwindtraders.com` , il valore che deve essere fornito sarà `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Se si selezionano più dispositivi, l'impostazione di tutti i dispositivi selezionati verrà modificata in base al valore fornito. Se i dispositivi hanno valori diversi per un'impostazione, verranno tutti aggiornati allo stesso valore.

| Impostazione                                                      | Valori accettati                                        | Supporta la modifica in blocco |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Account*                                                    |                                                        |                    |
| **Posta elettronica**                                                    | Indirizzo di posta elettronica                                          | No                 |
| **Modalità riunione supportata**                                   | Skype for business (impostazione predefinita) e Microsoft Teams<br>Skype for business e Microsoft Teams (impostazione predefinita)<br>Solo Skype for business|Sì|
| **Autenticazione moderna**                                    | Nella<br>Disattivare                                              | Sì                |
| **Indirizzo di Exchange**                                         | Indirizzo di posta elettronica                                          | No                 |
| **Dominio\nomeutente (facoltativo)**                               | Dominio account e nome utente                           | No                 |
| **Configurare il dominio**                                         | Elenco delimitato da virgole                                   | Sì                |
| *Riunioni*                                                   |                                                        |                    |
| **Condivisione automatica dello schermo**                                 | Nella<br>Disattivare                                              | Sì                |
| **Visualizzare i nomi delle riunioni**                                       | Nella<br>Disattivare                                              | Sì                |
| **Uscita automatica se tutti gli altri hanno lasciato la riunione**                 | Nella<br>Disattivare                                              | Sì                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modalità dual monitor**                                        | Nella<br>Disattivare                                              | Sì                |
| **Beaconing Bluetooth**                                      | Nella<br>Disattivare                                              | Sì                |
| **Accettare automaticamente gli inviti alle riunioni basati sulla prossimità** | Selezionato<br>Non selezionata                                 | Sì                |
| **Inviare log con feedback**                                  | Nella<br>Disattivare                                              | Sì                |
| **Indirizzo di posta elettronica per log e feedback**                      | Indirizzo di posta elettronica                                          | Sì                |
| *Periferiche*                                                |                                                        |                    |
| **Microfono per conferenze**                                  | Elenco dei microfoni disponibili                          | No                 |
| **Relatore conferenze**                                     | Elenco degli oratori disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Altoparlante predefinito**                                          | Elenco degli oratori disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Fotocamera del contenuto**                                           | Elenco delle fotocamere disponibili                              | No                 |
| **Miglioramenti apportati alla fotocamera**                              | Nella<br>Disattivare                                              | No                 |
| **Ruotare il contenuto della videocamera 180 gradi**                        | Nella<br>Disattivare                                              | No                 |
| *Temi*                                                    |                                                        |                    |
|                                                              | Predefinita<br>Nessun tema<br>Personalizzato<br>Elenco dei temi predefiniti   | Sì                |

### <a name="device-restart-options"></a>Opzioni di riavvio del dispositivo

Le modifiche apportate alle impostazioni del dispositivo avranno effetto solo dopo che i dispositivi sono stati riavviati. Quando si apportano modifiche che richiedono un riavvio, è possibile scegliere se riavviare immediatamente i dispositivi o pianificare un riavvio. Ecco le opzioni di riavvio disponibili:

- **Riavvio immediato** Se si sceglie questa opzione, tutti i dispositivi da apportare alle modifiche verranno riavviati non appena si seleziona questa opzione.
- **Riavvio programmato** Se si sceglie questa opzione, è possibile riavviare i dispositivi in cui si stanno apportando modifiche in un momento meno distruttivo per l'organizzazione.
  - **Selezionare data e ora** : scegliere la data e l'ora specifiche per riavviare il dispositivo. La data e l'ora in cui si sceglie è locale per il dispositivo da riavviare. 
  - **Uscire dall'aggiornamento per il riavvio notturno** I dispositivi vengono riavviati tutte le sere per eseguire la manutenzione. Le modifiche apportate ai dispositivi verranno applicate durante il riavvio.

> [!CAUTION]
> I dispositivi in uso al momento di un riavvio non saranno disponibili per la durata del processo di riavvio. Verranno disconnesse dalle riunioni in corso e non saranno disponibili per partecipare a nuove riunioni.

### <a name="remove-or-block-a-device"></a>Rimuovere o bloccare un dispositivo

Quando si **rimuove** un dispositivo, il dispositivo viene rimosso dall'organizzazione e non viene più visualizzato nell'elenco dei dispositivi teams rooms nell'interfaccia di amministrazione di teams. 

Quando si **blocca** un dispositivo, i team non comunicano più con il dispositivo. I dispositivi bloccati non vengono inviati comandi anche se sono inclusi in un gruppo di dispositivi che vengono modificati in blocco. È ancora elencato nell'elenco dei dispositivi teams Rooms con uno stato **bloccato**.

Indipendentemente dal fatto che un dispositivo sia bloccato o rimosso, se è ancora configurato con un nome utente e una password validi, verrà aggiunto di nuovo automaticamente all'elenco dei dispositivi di teams rooms, se si connette a Microsoft 365.

Per rimuovere uno o più dispositivi, eseguire le operazioni seguenti:

1. Passa a **dispositivi**  >  **Teams Rooms** e seleziona i dispositivi che vuoi rimuovere.
1. Selezionare **Rimuovi**.

Per bloccare un dispositivo, eseguire le operazioni seguenti:

1. Accedere a **dispositivi**  >  **Teams Rooms** e selezionare il nome del dispositivo che si vuole bloccare.
1. Nella pagina Dettagli dispositivo selezionare **azioni** nell'angolo in alto a destra della pagina.
1. Selezionare **blocca**.

Per sbloccare un dispositivo, eseguire le operazioni seguenti:

1. Accedere a **dispositivi**  >  **Teams Rooms** e selezionare il nome del dispositivo che si vuole bloccare.
1. Nella pagina Dettagli dispositivo selezionare **azioni** nell'angolo in alto a destra della pagina.
1. Selezionare **Sblocca**.

## <a name="download-device-logs"></a>Scaricare i log dei dispositivi

È possibile scaricare una copia dei file di log di diagnostica di un dispositivo se richiesto dal supporto Microsoft. I file di log vengono compressi in un file zip che può essere scaricato dall'interfaccia di amministrazione di teams.

Per scaricare i log da un dispositivo teams Rooms nel computer, eseguire le operazioni seguenti:

1. Passa a **dispositivi**  >  **Teams Rooms** e seleziona il nome del dispositivo da cui vuoi scaricare i log.
1. Selezionare **Scarica log dei dispositivi**. I log dei dispositivi possono richiedere diversi minuti per renderlo disponibile.
1. Selezionare la scheda **cronologia** e quindi selezionare log file link in **file di diagnostica**. Un file zip contenente i file di log di diagnostica del dispositivo verrà scaricato nella cartella dei download predefiniti del browser.

## <a name="view-device-information"></a>Visualizzare le informazioni sui dispositivi

Dall'interfaccia di amministrazione di teams è possibile visualizzare lo stato complessivo di tutti i dispositivi dell'organizzazione e visualizzare i dettagli di ogni dispositivo singolarmente.

### <a name="teams-rooms-system-dashboard"></a>Dashboard di sistema di teams rooms

Il dashboard del sistema teams Rooms Mostra lo stato e l'integrità di tutti i dispositivi in sintesi.

### <a name="device-details-view"></a>Visualizzazione dettagli dispositivo

Per visualizzare informazioni dettagliate su un dispositivo, selezionarne il nome nell'elenco dei dispositivi. In visualizzazione dettagli è possibile visualizzare le informazioni seguenti sul dispositivo:

- **Stato integrità** Mostra l'integrità complessiva del dispositivo room teams. Lo stato di integrità può **Healthy** essere sano **o non integro**.
- **Offline dato che** Mostra l'ultima volta che Microsoft 365 è stato in grado di comunicare con il dispositivo.
- **Stato del dispositivo** Mostra lo stato corrente del dispositivo: **Idle**, **meeting teams**, **riunione Skype**o **ingerire**.
- **Periferiche** Mostra le periferiche connesse al dispositivo della sala teams e il relativo stato di integrità. Lo stato di integrità può essere **connesso** o **disconnesso**.
- **Integrità** Mostra informazioni dettagliate sulle periferiche connesse al dispositivo room teams, la connettività di rete, lo stato di accesso ai servizi necessari e le informazioni sulla versione del software.
- **Informazioni dettagliate** Mostra le informazioni del produttore, l'indirizzo IP di rete e l'indirizzo seriale/MAC del dispositivo room teams.
- **Attività** Mostra i dettagli della riunione precedenti, tra cui la data e l'ora della riunione, il numero di partecipanti, la durata e la qualità audio. Per altre informazioni sui dettagli delle riunioni, vedere la sezione [Dettagli attività riunione](#meeting-activity-details) più avanti in questo articolo.
- **Cronologia** Mostra una cronologia delle attività di gestione nel dispositivo room teams, inclusi gli aggiornamenti della configurazione, i riavvii dei dispositivi e i collegamenti per il download del log dei dispositivi.

#### <a name="meeting-activity-details"></a>Dettagli attività riunione

La scheda **attività** nei dettagli del dispositivo sala teams Mostra informazioni di alto livello e dettagliate su tutte le riunioni a cui il dispositivo ha partecipato nel tempo. Nella scheda **attività** è possibile vedere quando si è tenuta una riunione, quanti partecipanti hanno partecipato alla riunione e la qualità dell'audio durante la riunione.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Elenco Riepilogo attività del dispositivo sala Teams":::

Per visualizzare le informazioni dettagliate su una riunione specifica, selezionare la data e l'ora della riunione per cui si vogliono altre informazioni. Se una riunione ha solo due partecipanti, verrà visualizzata la pagina Dettagli partecipante, altrimenti verrà visualizzata una pagina di riepilogo dei partecipanti.

##### <a name="participant-summary"></a>Riepilogo dei partecipanti

La pagina di riepilogo dei partecipanti Mostra tutti i partecipanti che hanno partecipato alla riunione. È possibile vedere quando ogni partecipante ha partecipato alla riunione, il nome, la qualità audio e le caratteristiche usate durante la sessione. Per visualizzare i dettagli della sessione di un partecipante, selezionare l'ora di inizio della sessione per il partecipante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Dettagli conferenza di team room Device":::

##### <a name="participant-details"></a>Dettagli partecipanti

La pagina dei dettagli del partecipante Mostra le informazioni di diagnostica end-to-end per la sessione del partecipante. Come illustrato nella figura seguente, per il partecipante e per il dispositivo teams Rooms è disponibile l'elemento grafico, il **dispositivo**, il **sistema**e le informazioni di **connettività** . Vengono fornite anche informazioni di diagnostica di **rete** tra il partecipante e il dispositivo sale teams. Selezionare l'icona per il contesto per cui si vogliono altre informazioni. Per altre informazioni di diagnostica, selezionare la scheda **Avanzate** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Dettagli della chiamata del dispositivo sala Teams":::
