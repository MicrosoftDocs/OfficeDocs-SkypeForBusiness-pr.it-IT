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
description: Informazioni su come sviluppare ed eseguire operazioni e manutenzione continuativa per assicurarsi che i Microsoft Teams Rooms di lavoro siano disponibili per gli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b95e1191201e3b5a8f234cc47c1a886cb7f0cf9a
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469598"
---
# <a name="manage-microsoft-teams-rooms"></a>Gestire Microsoft Teams Rooms.

Se nell'organizzazione Microsoft Teams Rooms dispositivi certificati, sono disponibili opzioni di gestione flessibili.  È possibile gestire i dispositivi manualmente nella stessa posizione centrale in cui si gestiscono tutte le soluzioni Teams, l'interfaccia di amministrazione di Microsoft Teams oppure trasferire la responsabilità di gestione a esperti dedicati usando [Microsoft Teams Rooms Managed Services.](https://portal.rooms.microsoft.com)  È anche possibile delegare l'accesso di gestione a un partner di propria scelta per una delle opzioni.

Con Microsoft Teams di amministrazione è possibile:

- Eseguire la gestione dei dispositivi, ad esempio il riavvio dei dispositivi e il download dei log dei dispositivi
- Applicare Teams specifiche
- Controllare lo stato di integrità dei Microsoft Teams room e delle relative periferiche, tra cui fotocamere, schermi, microfoni e così via
- Esaminare le attività della riunione correnti e passate (ad esempio dettagli sulla qualità delle chiamate, sull'integrità e la connettività di rete e sul numero di partecipanti)
- Visualizzare le periferiche (ad esempio videocamere e proiettori) collegate a un dispositivo Microsoft Teams Room

Per gestire Teams Rooms dispositivi, aprire [l'Microsoft Teams di amministrazione](https://admin.teams.microsoft.com) e passare a **Dispositivi**  >  **Teams Rooms**.

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Teams Rooms di riepilogo nell'Teams di amministrazione":::

> [!IMPORTANT]
> Per gestire i dispositivi usando Teams di amministrazione, è necessario avere i ruoli amministratore globale, amministratore Teams o amministratore Teams dispositivo.

## <a name="make-changes-to-teams-rooms-devices"></a>Apportare modifiche ai Teams Rooms dispositivi

Se si hanno più dispositivi Teams Rooms, è possibile eseguire la maggior parte delle azioni su più dispositivi contemporaneamente. Ad esempio, puoi impostare Teams'app su tutti i tuoi dispositivi contemporaneamente.

### <a name="device-settings"></a>Impostazioni del dispositivo

È possibile modificare le impostazioni in uno o più dispositivi dell'organizzazione. Per modificare le impostazioni, selezionare il dispositivo o i dispositivi da gestire e quindi selezionare **Modifica Impostazioni**. Si aprirà un nuovo riquadro con tutte le impostazioni che è possibile modificare nei dispositivi. La tabella seguente elenca le impostazioni che è possibile modificare usando l'Teams di amministrazione. Alcune impostazioni sono disponibili solo quando si seleziona un singolo dispositivo.

Se si selezionano più dispositivi, le impostazioni che supportano la modifica in blocco mostrano le due opzioni seguenti.

- **Mantieni valore esistente** Se si sceglie questa opzione, non verranno apportate modifiche all'impostazione nei dispositivi selezionati.
- **Sostituire il valore esistente con** Se si sceglie questa opzione, è possibile aggiornare l'impostazione nei dispositivi selezionati con il valore specificato.
    > [!CAUTION]
    > I valori esistenti nelle impostazioni che si sceglie di aggiornare verranno sostituiti con il valore specificato. Se si vuole aggiungere valori a un elenco di valori esistenti, è necessario includere i valori esistenti con il valore da aggiungere. Ad esempio, se un'impostazione ha un elenco di domini esistente di , e si vuole aggiungere , il valore da `contoso.com, fabrikam.com` `northwindtraders.com` fornire sarà `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Se si selezionano più dispositivi, l'impostazione in tutti i dispositivi selezionati verrà modificata nel valore specificato. Se i dispositivi hanno valori diversi per un'impostazione, verranno tutti aggiornati allo stesso valore.

| Impostazione                                                      | Valori accettati                                        | Supporta la modifica in blocco |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Account*                                                    |                                                        |                    |
| **Posta elettronica**                                                    | Indirizzo di posta elettronica                                          | No                 |
| **Modalità riunione supportata**                                   | Skype for Business (impostazione predefinita) e Microsoft Teams<br>Skype for Business e Microsoft Teams (impostazione predefinita)<br>Skype for Business Solo|Sì|
| **Autenticazione moderna**                                    | Attivato<br>Disattivato                                              | Sì                |
| **Exchange indirizzo**                                         | Indirizzo di posta elettronica                                          | No                 |
| **Dominio\nomeutente (facoltativo)**                               | Dominio dell'account e nome utente                           | No                 |
| **Configurare il dominio**                                         | Elenco delimitato da virgole                                   | Sì                |
| *Riunioni*                                                   |                                                        |                    |
| **Condivisione automatica dello schermo**                                 | Attivato<br>Disattivato                                              | Sì                |
| **Visualizzare i nomi delle riunioni**                                       | Attivato<br>Disattivato                                              | Sì                |
| **Uscire automaticamente se tutti gli altri hanno lasciato la riunione**                 | Attivato<br>Disattivato                                              | Sì                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modalità a doppio monitor**                                        | Attivato<br>Disattivato                                              | Sì                |
| **Bluetooth beaconing**                                      | Attivato<br>Disattivato                                              | Sì                |
| **Accettare automaticamente inviti a riunioni basate sulla prossimità** | Selezionato<br>Non selezionato                                 | Sì                |
| **Inviare log con feedback**                                  | Attivato<br>Disattivato                                              | Sì                |
| **Indirizzo di posta elettronica per i log e il feedback**                      | Indirizzo di posta elettronica                                          | Sì                |
| *Periferiche*                                                |                                                        |                    |
| **Microfono per conferenze**                                  | Elenco dei microfoni disponibili                          | No                 |
| **Altoparlante per conferenze**                                     | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Altoparlante predefinito**                                          | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Fotocamera del contenuto**                                           | Elenco delle fotocamere disponibili                              | No                 |
| **Miglioramenti della fotocamera del contenuto**                              | Attivato<br>Disattivato                                              | No                 |
| **Ruotare la fotocamera del contenuto di 180 gradi**                        | Attivato<br>Disattivato                                              | No                 |
| *Ting*                                                    |                                                        |                    |
|                                                              | Impostazione predefinita<br>Nessun tema<br>Personalizzato<br>Elenco dei temi predefiniti   | Sì                |

### <a name="device-restart-options"></a>Opzioni di riavvio del dispositivo

Le modifiche alle impostazioni dei dispositivi avranno effetto solo dopo il riavvio dei dispositivi. Quando si apportano modifiche che necessitano di un riavvio, è possibile scegliere se riavviare immediatamente i dispositivi o pianificare un riavvio. Ecco le opzioni di riavvio disponibili:

- **Riavvio immediato** Se si sceglie questa opzione, tutti i dispositivi a cui si stanno apportando modifiche verranno riavviati non appena si seleziona questa opzione.
- **Riavvio pianificato** Se si sceglie questa opzione, è possibile riavviare i dispositivi a cui si apportano modifiche in un momento meno dannoso per l'organizzazione.
  - **Selezionare data e ora:** scegliere la data e l'ora specifiche per riavviare il dispositivo. La data e l'ora selezionate sono locali per il dispositivo da riavviare. 
  - **Lascia l'aggiornamento per il riavvio notturno** I dispositivi vengono riavviati ogni notte per eseguire la manutenzione. Le modifiche apportate ai dispositivi verranno applicate durante questo riavvio.

> [!CAUTION]
> I dispositivi in uso al momento del riavvio non saranno più disponibili per la durata del processo di riavvio. Verranno disconnessi dalle riunioni in corso e non saranno disponibili per partecipare a nuove riunioni.

### <a name="remove-device"></a>Rimuovi dispositivo

Quando si rimuove un dispositivo, il dispositivo viene rimosso dall'organizzazione e non viene più visualizzato nell'elenco dei dispositivi di Teams Rooms nell'interfaccia Teams di amministrazione.

Se rimuovi un dispositivo ed è ancora configurato con un nome utente e una password validi, verrà automaticamente aggiunto di nuovo all'elenco dei dispositivi Teams Rooms se si connette di nuovo a Microsoft 365.

Per rimuovere uno o più dispositivi, eseguire le operazioni seguenti:

1. Passare **a Dispositivi**  >  **Teams Rooms** e selezionare i dispositivi da rimuovere.
1. Selezionare **Rimuovi**.

## <a name="download-device-logs"></a>Scaricare i log dei dispositivi

Se richiesto dal supporto Microsoft, è possibile scaricare una copia dei file di log di diagnostica di un dispositivo. I file di log vengono compressi in un file ZIP che può essere scaricato dall'Teams di amministrazione.

Per scaricare i log da un Teams Rooms nel computer, eseguire le operazioni seguenti:

1. Passare a **Dispositivi** Teams Rooms e selezionare il nome del dispositivo da  >   cui si vogliono scaricare i log.
1. Selezionare **Scarica i log dei dispositivi**. La disponibilità dei log dei dispositivi può richiedere alcuni minuti.
1. Selezionare la **scheda Cronologia** e quindi selezionare il collegamento file di log in File **di diagnostica.** Un file ZIP contenente i file di log di diagnostica del dispositivo verrà scaricato nella cartella download predefinita del browser.

## <a name="view-device-information"></a>Visualizzare le informazioni sul dispositivo

Nell'Teams di amministrazione è possibile visualizzare lo stato generale di tutti i dispositivi dell'organizzazione e visualizzare i dettagli di ogni dispositivo singolarmente.

### <a name="teams-rooms-system-dashboard"></a>Teams Rooms di sistema

Il Teams Rooms di sistema mostra a colpo d'occhio lo stato e l'integrità di tutti i dispositivi.

### <a name="device-details-view"></a>Visualizzazione dettagli dispositivo

Per visualizzare informazioni dettagliate su un dispositivo, selezionarne il nome nell'elenco dei dispositivi. Nella visualizzazione dettagli è possibile visualizzare le informazioni seguenti sul dispositivo:

- **Stato integrità** Mostra l'integrità generale del dispositivo Teams room. Lo stato di integrità può **essere Integro** **o Non integro.**
- **Offline da** Mostra l'ultima Microsoft 365 stato in grado di comunicare con il dispositivo.
- **Stato del dispositivo** Mostra lo stato corrente del **dispositivo:** Inattivo, **Teams riunione,** **Skype riunione** o **Ingest**.
- **Periferiche** Mostra le periferiche connesse al dispositivo Teams room e il relativo stato di integrità. Lo stato di integrità può essere **Connesso** **o Disconnesso.**
- **Integrità** Mostra informazioni dettagliate sulle periferiche connesse al dispositivo room Teams, sulla connettività di rete, sullo stato di accesso ai servizi necessari e sulle informazioni sulla versione del software.
- **Dettagli** Mostra le informazioni sul produttore, l'indirizzo IP di rete e Teams dispositivo room seriale/MAC.
- **Attività** Mostra i dettagli della riunione precedenti, tra cui la data e l'ora della riunione, il numero di partecipanti, la durata e la qualità audio. Per altre informazioni sui dettagli della riunione, vedere la sezione Dettagli [attività riunione](#meeting-activity-details) più avanti in questo articolo.
- **Cronologia** Mostra una cronologia delle attività di gestione nel dispositivo Teams room, inclusi gli aggiornamenti di configurazione, i riavvii dei dispositivi e i collegamenti per il download del log dei dispositivi.

#### <a name="meeting-activity-details"></a>Dettagli attività riunione

La **scheda Attività** in Teams dettagli del dispositivo room mostra informazioni di alto livello e dettagliate su tutte le riunioni a cui il dispositivo ha partecipato nel corso del tempo. Nella scheda **Attività** è possibile vedere quando è stata tenuta una riunione, quanti partecipanti hanno partecipato alla riunione e la qualità dell'audio durante la riunione.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams Elenco di riepilogo delle attività dei dispositivi della sala":::

Per visualizzare le informazioni dettagliate su una riunione specifica, selezionare la data e l'ora della riunione su cui si vogliono ottenere altre informazioni. Se una riunione ha solo due partecipanti, verrà visualizzata la pagina dei dettagli del partecipante, altrimenti verrà visualizzata una pagina di riepilogo dei partecipanti.

##### <a name="participant-summary"></a>Riepilogo dei partecipanti

La pagina di riepilogo dei partecipanti mostra tutti i partecipanti che hanno partecipato alla riunione. È possibile vedere quando ogni partecipante ha partecipato alla riunione, il nome, la qualità audio e le caratteristiche usate durante la sessione. Per visualizzare i dettagli della sessione di un partecipante, selezionare l'ora di inizio della sessione per il partecipante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams Dettagli conferenza del dispositivo sala":::

##### <a name="participant-details"></a>Dettagli del partecipante

La pagina dei dettagli del partecipante mostra informazioni di diagnostica end-to-end per la sessione del partecipante. Come illustrato nell'immagine seguente, le  informazioni su **Dispositivo,** **Sistema** e Connettività vengono fornite per il partecipante e per il Teams Rooms dispositivo. **Vengono fornite** anche le informazioni di diagnostica di rete tra il partecipante e Teams Rooms dispositivo. Selezionare l'icona relativa al contesto su cui si vogliono ottenere altre informazioni. Per altre informazioni di diagnostica, selezionare la **scheda** Avanzate.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams Dettagli chiamata dispositivo sala":::
