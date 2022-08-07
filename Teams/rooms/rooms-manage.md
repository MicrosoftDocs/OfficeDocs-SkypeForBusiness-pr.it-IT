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
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Informazioni su come sviluppare ed eseguire interventi di manutenzione e operazioni continuativi per garantire che i sistemi Microsoft Teams Rooms siano disponibili per gli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85bb58005159b18a426aed0851ac7a80b11183eb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271093"
---
# <a name="manage-microsoft-teams-rooms"></a>Gestire Microsoft Teams Rooms.

Se nell'organizzazione sono presenti Microsoft Teams Rooms, sono disponibili opzioni di gestione flessibili.  È possibile gestire i dispositivi autonomamente nella stessa posizione centrale in cui si gestiscono tutte le soluzioni Teams, l'interfaccia di amministrazione di Microsoft Teams. In alternativa, è possibile trasferire la responsabilità di gestione a esperti dedicati usando [Microsoft Teams Rooms Servizi gestiti](https://portal.rooms.microsoft.com).  È anche possibile delegare l'accesso di gestione a un partner di propria scelta per una delle opzioni.

Con l'interfaccia di amministrazione di Microsoft Teams è possibile:

- Eseguire la gestione dei dispositivi, ad esempio riavviare i dispositivi e scaricare i log dei dispositivi
- Applicare impostazioni specifiche di Teams
- Controllare lo stato di integrità di Microsoft Teams Rooms e delle relative periferiche, incluse fotocamere, schermi, microfoni e così via
- Esaminare le attività delle riunioni attuali e passate, ad esempio i dettagli sulla qualità delle chiamate, l'integrità e la connettività di rete e il numero di partecipanti.
- Vedi le periferiche (ad esempio fotocamere e proiettori) collegate a Microsoft Teams Rooms

Per gestire Teams Rooms dispositivi, aprire [l'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com) e passare a **Dispositivi** >  di Teams **Teams Rooms in Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams Rooms pagina di riepilogo nell'interfaccia di amministrazione di Teams.":::


> [!IMPORTANT]
> Per gestire i dispositivi usando l'interfaccia di amministrazione di Teams, è necessario avere il ruolo amministratore globale, amministratore di Teams o amministratore dei dispositivi di Teams.

## <a name="make-changes-to-teams-rooms-devices"></a>Apportare modifiche ai dispositivi Teams Rooms

Se hai più di un Teams Rooms, puoi eseguire la maggior parte delle azioni su più dispositivi contemporaneamente. Ad esempio, è possibile impostare contemporaneamente le impostazioni dell'app Teams in tutti i Teams Rooms.

### <a name="device-settings"></a>Impostazioni dispositivo

È possibile modificare le impostazioni in uno o più Teams Rooms dell'organizzazione. Per modificare le impostazioni, seleziona il dispositivo o i dispositivi che vuoi gestire, quindi seleziona **Modifica impostazioni**. Verrà aperto un nuovo riquadro con tutte le impostazioni modificabili. La tabella seguente elenca le impostazioni che è possibile modificare usando l'interfaccia di amministrazione di Teams. Alcune impostazioni sono disponibili solo quando si seleziona una singola Teams Rooms.

Se si selezionano più impostazioni, le impostazioni che supportano la modifica in blocco mostrano le due opzioni seguenti.

- **Mantenere un valore esistente** Se si sceglie questa opzione, non verrà apportata alcuna modifica all'impostazione nella Teams Rooms selezionata.
- **Sostituisci il valore esistente con** Se si sceglie questa opzione, è possibile aggiornare l'impostazione nel Teams Rooms selezionato con il valore specificato.
    > [!CAUTION]
    > I valori esistenti nelle impostazioni che si sceglie di aggiornare verranno sostituiti con il valore specificato. Se si vuole aggiungere un valore a un elenco di valori esistenti, è necessario includere i valori esistenti con il valore da sommare. Ad esempio, se un'impostazione ha un elenco di domini esistente di `contoso.com, fabrikam.com`e si vuole aggiungere `northwindtraders.com`, il valore da fornire sarà `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Se selezioni più Teams Rooms, l'impostazione in tutti i dispositivi selezionati verrà impostata sul valore specificato. Se Teams Rooms hanno valori diversi per un'impostazione, verranno tutti aggiornati allo stesso valore.

| Impostazione                                                      | Valori accettati                                        | Supporta la modifica in blocco |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Account*                                                    |                                                        |                    |
| **Email**                                                    | indirizzo Email                                          | No                 |
| **Modalità riunione supportata**                                   | Solo Microsoft Teams<br>Skype for Business (impostazione predefinita) e Microsoft Teams<br>Skype for Business e Microsoft Teams (impostazione predefinita)<br>solo Skype for Business|Sì|
| **Autenticazione moderna**                                    | Attivato<br>Disattivato                                              | Sì                |
| **Indirizzo di Exchange**                                         | indirizzo Email                                          | No                 |
| **Dominio\nomeutente (facoltativo)**                               | Dominio account e nome utente                           | No                 |
| **Configurare il dominio**                                         | Elenco separato da virgole                                   | Sì                |
| *Riunioni*                                                   |                                                        |                    |
| **Condivisione automatica dello schermo**                                 | Attivato<br>Disattivato                                              | Sì                |
| **Condivisione audio in ingresso HDMI**                                 | Attivato<br>Disattivato                                              | Sì                |
| **Visualizzare i nomi delle riunioni**                                       | Attivato<br>Disattivato                                              | Sì                |
| **Uscita automatica se tutti gli altri hanno lasciato la riunione**                 | Attivato<br>Disattivato                                              | Sì                |
| **Partecipare a riunioni di terze parti**                 | Cisco Webex<br>Zoom                                              | Sì                |
| **Partecipare con le informazioni sulla sala**                 | Selezionato<br>Deselezionata                                              | Sì                |
| **Partecipa con info personalizzate**                 | Selezionato<br>Deselezionata                                              | Sì                |
| **Nome (obbligatorio)**                 | Nome della stanza o dello spazio                                              | Sì                |
| **Email (obbligatorio)**                 | indirizzo Email                                              | Sì                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modalità doppio monitor**                                        | Attivato<br>Disattivato                                              | Sì                |
| **Consentire la duplicazione del contenuto** | Selezionato<br>Deselezionata                                 | Sì                |
| **Beaconing Bluetooth**                                      | Attivato<br>Disattivato                                              | Sì                |
| **Accettare automaticamente inviti alle riunioni in base alla prossimità** | Selezionato<br>Deselezionata                                 | Sì                |
| **Inviare log con feedback**                                  | Attivato<br>Disattivato                                              | Sì                |
| **indirizzo Email per i log e il feedback**                      | indirizzo Email                                          | Sì                |
| *Coordinare riunioni*                                                     |                                                        |                    |
| **Riunioni coordinate** | Attivato<br>Disattivato                                 | No                |
| **Attivare il microfono del dispositivo** | Attivato<br>Disattivato                                 | No                |
| **Consentire agli utenti di abilitare l'accesso a una riunione** | Selezionato<br>Deselezionata                                 | No                |
| **Attivare la fotocamera del dispositivo** | Attivato<br>Disattivato                                 | No                |
| **Consentire agli utenti di abilitare l'accesso a una riunione** | Selezionato<br>Deselezionata                                 | No                |
| **Attivare la lavagna per questo dispositivo** | Attivato<br>Disattivato                                 | No                |
| **Account di dispositivo attendibili (separati da virgole)** | Elenco dei dispositivi                              | No                |
| *Periferiche*                                                |                                                        |                    |
| **Microfono per conferenze**                                  | Elenco dei microfoni disponibili                          | No                 |
| **Altoparlante conferenza**                                     | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Altoparlante predefinito**                                          | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Fotocamera contenuto**                                           | Elenco delle fotocamere disponibili                              | No                 |
| **Miglioramenti apportati alla fotocamera contenuto**                              | Attivato<br>Disattivato                                              | No                 |
| **Ruotare la fotocamera del contenuto di 180 gradi**                        | Attivato<br>Disattivato                                              | No                 |
| *Temi*                                                    |                                                        |                    |
|                                                              | Predefinito<br>Nessun tema<br>Personalizzato<br>Elenco di temi predefiniti   | Sì                |

### <a name="cortana-settings"></a>Impostazioni di Cortana

Puoi abilitare Cortana per _l'attivazione vocale_ o _il push per parlare_ con PowerShell per tutti i dispositivi dell'organizzazione o per ogni dispositivo separatamente.

Vedi [Microsoft Teams Rooms su Windows](../cortana-in-teams.md) nell'articolo "Assistenza vocale di Cortana in Teams".

### <a name="front-row-layout-settings"></a>Impostazioni del layout Prima riga

La prima riga è l'opzione di layout della visualizzazione riunione per Teams Rooms in Windows.

| Dispositivo di Teams | Versione dell'app | Davanti al display della sala |
|--------------|-------------|-----------------------|
|Microsoft Teams Rooms in Windows | 4.11.12.0 o versione successiva (è consigliata la versione più recente) | Supporta display singoli e doppi; Dimensioni minime: 46 pollici; Proporzioni 16:9 con risoluzione 1920x1080 o 21:9 con risoluzione 2560x1080; Tutti gli schermi devono essere impostati con ridimensionamento al 100% nelle impostazioni di Windows |

Vedere [Microsoft Teams Rooms manutenzione e le operazioni](rooms-operations.md#scale-and-resolution), per modificare le impostazioni dello schermo in modo da soddisfare i requisiti di Front row.

Per informazioni su come impostare Front row come layout predefinito per una chat room o su come disattivarlo, vedere [Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md#set-front-row-as-the-default-layout).

Per altre informazioni sulla gestione di Front Row, vedere [Problemi noti](known-issues.md#Limits) .

## <a name="device-restart-options"></a>Opzioni di riavvio del dispositivo

Le modifiche alle impostazioni del dispositivo avranno effetto solo dopo il riavvio di Teams Rooms. Quando apporti modifiche che richiedono un riavvio, puoi scegliere se riavviarlo immediatamente o pianificare un riavvio. Ecco le opzioni di riavvio disponibili:

- **Riavvio immediato** Se scegli questa opzione, tutti i dispositivi a cui stai apportando modifiche verranno riavviate non appena selezioni questa opzione.
- **Riavvio pianificato** Se scegli questa opzione, puoi riavviare i dispositivi a cui stai apportando modifiche in un momento meno fastidioso per l'organizzazione.
  - **Seleziona data e ora** : scegli la data e l'ora specifiche per riavviare il dispositivo. La data e l'ora scelte sono locali per il dispositivo da riavviare. 
  - **Lascia l'aggiornamento per il riavvio notturno** I dispositivi vengono riavviati ogni notte per eseguire la manutenzione. Le modifiche apportate ai dispositivi verranno applicate durante questo riavvio.

> [!CAUTION]
> Teams Rooms in uso al momento del riavvio non saranno disponibili per la durata del processo di riavvio. Verranno disconnessi dalle riunioni in corso e non saranno disponibili per partecipare a nuove riunioni.

## <a name="remove-device"></a>Rimuovi dispositivo

Quando si rimuove un dispositivo, il dispositivo viene rimosso dall'organizzazione e non viene più visualizzato nell'elenco di Teams Rooms in Windows nell'interfaccia di amministrazione di Teams.

Se rimuovi un dispositivo che è ancora configurato con un nome utente e una password validi, verrà aggiunto di nuovo all'elenco di Teams Rooms se si connette di nuovo a Microsoft 365.

Per rimuovere uno o più dispositivi, eseguire le operazioni seguenti:

1. Passare a **Dispositivi** >  di Teams **Teams Rooms in Windows** e selezionare i dispositivi da rimuovere.
2. Seleziona **Rimuovi**.

## <a name="download-device-logs"></a>Scaricare i log dei dispositivi

Se richiesto dal supporto tecnico Microsoft, è possibile scaricare una copia dei file di log diagnostici di un dispositivo. I file di log vengono compressi in un file ZIP che può essere scaricato dall'interfaccia di amministrazione di Teams.

Per scaricare i log da un dispositivo Teams Rooms nel computer, eseguire le operazioni seguenti:

1. Vai a **Dispositivi** >  di Teams **Teams Rooms in Windows** e seleziona il nome del dispositivo da cui vuoi scaricare i log.
1. Selezionare **Scarica registri dispositivi**. La disponibilità dei log dei dispositivi può richiedere alcuni minuti.
1. Selezionare la scheda **Cronologia** e quindi selezionare il collegamento al file di log in **File di diagnostica**. Nella cartella Download predefinita del browser verrà scaricato un file ZIP contenente i file di log diagnostici del dispositivo.

## <a name="view-device-information"></a>Visualizzare le informazioni sul dispositivo

Dall'interfaccia di amministrazione di Teams è possibile visualizzare lo stato generale di tutti i dispositivi dell'organizzazione e visualizzare i dettagli di ogni dispositivo singolarmente.

### <a name="teams-rooms-system-dashboard"></a>dashboard di sistema Teams Rooms

Il dashboard di sistema Teams Rooms mostra a colpo d'occhio lo stato e l'integrità di tutti i dispositivi.

### <a name="device-details-view"></a>Visualizzazione dettagli dispositivo

Per visualizzare informazioni dettagliate su un dispositivo, selezionane il nome nell'elenco dei dispositivi. Nella visualizzazione dettagli, è possibile visualizzare le informazioni seguenti sul dispositivo:

- **Stato di integrità** Mostra l'integrità generale del dispositivo Teams Room. Lo stato di integrità può essere **Sano** o **Non sano**.
- **Offline da** Mostra l'ultima volta che Microsoft 365 è riuscito a comunicare con il dispositivo.
- **Stato dispositivo** Mostra lo stato corrente del dispositivo: **Inattivo**, **Riunione di Teams**, **Riunione Skype** o **Ingest**.
- **Periferiche** Mostra le periferiche connesse al dispositivo Teams Room e il loro stato di integrità. Lo stato di integrità può essere **Connesso** o **Disconnesso**.
- **Salute** Mostra informazioni dettagliate sulle periferiche connesse al dispositivo Teams Room, alla connettività di rete, allo stato di accesso ai servizi necessari e alle informazioni sulla versione del software.
- **Dettagli** Mostra le informazioni sul produttore, l'indirizzo IP di rete e l'indirizzo seriale/MAC del dispositivo Teams Room.
- **Attività** Mostra i dettagli della riunione passati, tra cui data e ora della riunione, numero di partecipanti, durata e qualità audio. Per altre informazioni sui dettagli delle riunioni, vedere la sezione [Dettagli attività riunione](#meeting-activity-details) più avanti in questo articolo.
- **Storia** Mostra una cronologia delle attività di gestione sul dispositivo Teams Room, inclusi gli aggiornamenti di configurazione, i riavvii dei dispositivi e i collegamenti per il download dei log dei dispositivi.

#### <a name="meeting-activity-details"></a>Dettagli attività riunione

La scheda **Attività** nei dettagli del dispositivo sala di Teams mostra informazioni dettagliate e di alto livello su tutte le riunioni a cui il dispositivo ha partecipato nel tempo. Nella scheda **Attività** è possibile vedere quando si è tenuta una riunione, quanti partecipanti hanno partecipato alla riunione e la qualità dell'audio durante la riunione.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Elenco di riepilogo delle attività dei dispositivi sala riunioni di Teams.":::

Per visualizzare le informazioni dettagliate su una riunione specifica, selezionare la data e l'ora della riunione per cui si vogliono ottenere altre informazioni. Se una riunione include solo due partecipanti, verrà visualizzata la pagina dei dettagli del partecipante, altrimenti verrà visualizzata una pagina di riepilogo dei partecipanti.

##### <a name="participant-summary"></a>Riepilogo dei partecipanti

La pagina di riepilogo dei partecipanti mostra tutti i partecipanti che hanno partecipato alla riunione. È possibile vedere quando ogni partecipante ha eseguito l'accesso alla riunione, il nome, la qualità dell'audio e le funzionalità usate durante la sessione. Per visualizzare i dettagli della sessione di un partecipante, selezionare l'ora di inizio della sessione per tale partecipante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Dettagli sulla conferenza del dispositivo Room di Teams.":::

##### <a name="participant-details"></a>Dettagli partecipante

La pagina dei dettagli del partecipante mostra le informazioni diagnostiche end-to-end per la sessione del partecipante. Come illustrato nell'immagine seguente, le informazioni **su dispositivo**, **sistema** e **connettività** vengono fornite per il partecipante e per il dispositivo Teams Rooms. **Vengono** fornite anche informazioni diagnostiche di rete tra il partecipante e il dispositivo Teams Rooms. Selezionare l'icona per il contesto su cui si vogliono altre informazioni. Per altre informazioni di diagnostica, seleziona la scheda **Avanzate** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Dettagli delle chiamate del dispositivo sala di Teams.":::
